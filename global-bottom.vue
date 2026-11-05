<script setup lang="ts">
import { ref, computed, watch, onMounted, onUnmounted } from 'vue'
import { useNav } from '@slidev/client'

// Seconds allotted per slide before auto-advancing.
const DURATION = 15

const { next, currentPage, total } = useNav()

// Always start paused.
const running = ref(false)
const elapsed = ref(0)
const hidden = ref(false)
let hideTimeout = 0
let lastTs = 0
let raf = 0

// SVG ring geometry.
const R = 26
const CIRCUMFERENCE = 2 * Math.PI * R
const progress = computed(() => Math.min(elapsed.value / DURATION, 1))
const remaining = computed(() => Math.max(0, Math.ceil(DURATION - elapsed.value)))
const dashOffset = computed(() => CIRCUMFERENCE * (1 - progress.value))

function frame(ts: number) {
  if (lastTs === 0) lastTs = ts
  const dt = (ts - lastTs) / 1000
  lastTs = ts

  if (running.value) {
    elapsed.value += dt
    if (elapsed.value >= DURATION) {
      if (currentPage.value < total.value) {
        next()
        elapsed.value = 0
      } else {
        // Reached the final slide — hold and stop.
        running.value = false
        elapsed.value = DURATION
      }
    }
  }
  raf = requestAnimationFrame(frame)
}

function resetTimer() {
  elapsed.value = 0
  lastTs = 0
}

function toggle() {
  // Restart cleanly if we had stopped on the last slide.
  if (!running.value && elapsed.value >= DURATION) elapsed.value = 0
  running.value = !running.value
  if (running.value && !hideTimeout) {
    hideTimeout = window.setTimeout(() => { hidden.value = true }, 1000)
  }
}

function onKey(e: KeyboardEvent) {
  const t = e.target as HTMLElement
  if (t && (t.tagName === 'INPUT' || t.tagName === 'TEXTAREA' || t.isContentEditable)) return
  if (e.key === 'a' || e.key === 'A') { toggle(); e.preventDefault() }
  if (e.key === 'r' || e.key === 'R') { resetTimer() }
}

// Restart the countdown whenever the slide changes (manually or automatically).
watch(currentPage, resetTimer)

onMounted(() => {
  raf = requestAnimationFrame(frame)
  window.addEventListener('keydown', onKey)
})
onUnmounted(() => {
  window.clearTimeout(hideTimeout)
  cancelAnimationFrame(raf)
  window.removeEventListener('keydown', onKey)
})
</script>

<template>
  <div
    class="slide-timer print:hidden"
    :class="{ 'is-paused': !running, 'is-hidden': hidden }"
    :title="running ? 'Auto-advance ON · A: pause · R: reset' : 'Auto-advance PAUSED · A: resume · R: reset'"
    @click="toggle"
  >
    <svg width="72" height="72" viewBox="0 0 72 72">
      <circle cx="36" cy="36" :r="R" fill="none" stroke="rgba(255,255,255,0.14)" stroke-width="5" />
      <circle
        cx="36" cy="36" :r="R" fill="none"
        :stroke="running ? 'var(--accent, #0070F3)' : '#888'"
        stroke-width="5" stroke-linecap="round"
        :stroke-dasharray="CIRCUMFERENCE"
        :stroke-dashoffset="dashOffset"
        transform="rotate(-90 36 36)"
        style="transition: stroke-dashoffset 0.08s linear"
      />
    </svg>
    <div class="slide-timer__label">
      <span v-if="running">{{ remaining }}</span>
      <span v-else class="slide-timer__pause">❚❚</span>
    </div>
  </div>
</template>

<style scoped>
.slide-timer {
  position: fixed;
  right: 18px;
  bottom: 18px;
  width: 72px;
  height: 72px;
  z-index: 100;
  cursor: pointer;
  opacity: 0.9;
  transition: opacity 0.2s ease;
  user-select: none;
}
.slide-timer:hover { opacity: 1; }
.slide-timer.is-paused { opacity: 0.65; }
.slide-timer.is-hidden { opacity: 0; pointer-events: none; }
.slide-timer__label {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  font-weight: 700;
  color: #fff;
  font-variant-numeric: tabular-nums;
  text-shadow: 0 1px 3px rgba(0, 0, 0, 0.5);
}
.slide-timer__pause { font-size: 0.9rem; letter-spacing: -1px; }
</style>
