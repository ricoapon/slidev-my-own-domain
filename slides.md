---
theme: '@ricoapon/slidev-theme-narrative'
colorSchema: dark
themeConfig:
  accent: '#0070F3'
title: The Story Of How I Bought My Domain
transition: slide-left
layout: cover
background: /cover.jpg
---

# The Story Of How I Bought My <u>Domain</u>

<!--
Hi everybody, I am going to tell you a story today. I am going to talk about how it came to be that I bought my own 
domain. And I hope that after this presentation, you will be inspired to do the same! 
Let's start with the most obvious thing.
-->

---
layout: cover
background: /retro.jpg
---

# I love programming

<!--
I love programming. I think that is something we all have in common here. I started already when I was very young 
with programming in Visual Basic. I changed languages along the way, but I still program quite a bit.
-->

---
layout: cover
background: /code.jpg
---

# Bigger, more complex projects

<!--
It started as a hobby when I was younger, and now it is my job as a software engineer. Since then, my skills have
improved a lot. And that meant that my hobby projects also got bigger and more complex.
-->

---
layout: cover
background: /friends.jpg
---

# I love to share what I build

<!--
The projects I was building became more interesting and that meant I also wanted to share them with other people. I 
even started making projects for other people to help them with a specific problem.
-->

---
layout: image-right
image: /phone.jpg
---

# Just open the link

<!--
I didn't want people to download a JAR and run it on their computer. I have learned that many friends don't really
take the effort to do that. A website that they can open on their phone really is the best way if you want to share it.
-->

---
layout: statement
---

# FREE

Host it on GitHub Pages.

<!--
I wanted to host my apps for free. I decided on using GitHub Pages. You all know GitHub. You might not know that
you can also host static websites for free as part of GitHub, which is called GitHub Pages.
-->

---
layout: image-left
image: /deploy.jpg
---

# JavaScript

The necessary evil.

<!--
Static websites means you can only host HTML/JS/CSS stuff. And yeah, that means you have to do JavaScript. I used
Angular, so TypeScript. I am still not a fan of it, but yeah I can host it for free. You do what the job requires.
-->

---
layout: cover
background: /matrix.jpg
---

# One small catch

<div class="text-xl opacity-80 mt-2">You don't pick the name. You get <code>&lt;username&gt;.github.io/&lt;project&gt;</code>.</div>

<!--
When you create your site, it uses a default structure for your URL: `<username>.github.io/<projectname>`.
It is a predictable name, but maybe not the nicest name. Especially when you have a weird username or when you send
it to people that have no clue what GitHub is.
-->

---
layout: center
---

<div style="max-width:460px; margin:0 auto; display:flex; flex-direction:column; gap:10px; text-align:left;">
<div style="align-self:flex-end; max-width:80%; background:var(--accent); color:#fff; padding:10px 14px; 
border-radius:18px 18px 5px 18px; font-size:1rem; line-height:1.45;">yo Alain, try my new game 🎮<div 
style="font-size:.72rem; opacity:.85; margin-top:5px; word-break:break-all;">greent13.github.io/spacepoints</div></div>
<div style="align-self:flex-start; max-width:80%; background:var(--bg-alt); color:var(--text); border:1px solid var(--hairline); padding:10px 14px; border-radius:18px 18px 18px 5px; font-size:1rem; line-height:1.45;">cool game 👍</div>
<div style="align-self:flex-start; max-width:80%; background:var(--bg-alt); color:var(--text); border:1px solid var(--hairline); padding:10px 14px; border-radius:18px 18px 18px 5px; font-size:1rem; line-height:1.45;">terrible link though. why don't you just buy <b>ricoapon.nl</b>? 🤔</div>
</div>

<!--
A few years ago I sent my friend Alain a link to test a game I was making called Space Points. He wanted to be my
tester. He liked the game, but he had some interesting feedback: why don't you just buy ricoapon.nl?
-->

---
layout: cover
background: /burning.jpg
---

# "That's a waste of money"

<div class="text-xl opacity-80 mt-2">— me, being Dutch</div>

<!--
Like I said, I am Dutch, so I thought this would be a waste of money. The current URL just worked fine, right?
Why should I put in effort to change something that already worked?
-->

---
layout: image-right
image: /unfinished.jpg
---

# They're just hobby projects

* Not finished
* Not polished
* Abandoned after a weekend

<!--
They are also just hobby projects. Most of them aren't polished, they are often not even finished. A lot of them
are just an idea I played with for a weekend and then abandoned. They aren't worth their own domain.
-->

---
layout: statement
---

<div style="max-width: 780px; text-align:center;">
<div style="font-size:1.9rem; line-height:1.35; font-weight:600;">
"This is your biggest hobby. You spend so much time on it. <span class="accent">How can money ever be the argument?</span> Besides, it looks <span class="accent">way more professional</span>."
</div>
<div style="margin-top:1.2rem; opacity:.6;">— Alain</div>
</div>

<!--
Alain disagreed. He said: this is your biggest hobby. You spend so much time on it. And you have a job that
pays well. How can money ever be an argument? Besides, it looks way more professional when you do it.
-->

---
layout: cover
background: /space.jpg
---

# F*ck it

<div class="text-2xl opacity-80 mt-2">I bought ricoapon.nl the same day</div>

<!--
I didn't have a counterargument. So fuck it, let's buy a domain. I did it the same day that I talked to Alain. The domain
was still available and I bought ricoapon.nl.
-->

---
layout: center
---

# Ok, now what?

<div style="margin-top:18px; font-family:ui-monospace,monospace; background:#0d1117; border:1px solid #30363d; border-radius:10px; padding:16px 20px; display:inline-block; text-align:left; color:#8b949e;">
<div style="color:#c9d1d9;">$ how does DNS actually work?</div>
<div style="margin-top:8px;">→ read a tutorial</div>
<div>→ find the GitHub Pages manual</div>
<div>→ follow it step by step</div>
</div>

<!--
Ok, now what? I didn't know anything about DNS records or how it worked. So the first thing I did was lookup a
tutorial on that. I wanted to make it work specifically for GitHub Pages, for which there are plenty of good
manuals on what to exactly do.
-->

---
layout: center
---

# Technical configuration

<div style="max-width:740px; margin:24px auto 0; text-align:left; display:flex; flex-direction:column; gap:18px;">
  <div style="background:var(--bg-alt); border:1px solid var(--hairline); border-radius:10px; padding:16px 20px;">
    <div class="muted">Add CNAME record (= alias for another domain)</div>
    <div style="font-family:ui-monospace,monospace; margin-top:10px;">spacepoints.ricoapon.nl → &lt;username&gt;.github.io</div>
  </div>
  <div style="background:var(--bg-alt); border:1px solid var(--hairline); border-radius:10px; padding:16px 20px;">
    <div class="muted">In the repository: Settings → Pages → Custom domain</div>
    <div style="font-family:ui-monospace,monospace; margin-top:10px; color:var(--accent);">spacepoints.ricoapon.nl</div>
  </div>
</div>

<!--
At my domain provider, I add a CNAME record: an alias pointing my subdomain at my GitHub Pages hostname.
Then I enter that same subdomain in the repository's Pages settings, so GitHub knows which website to serve.
The DNS target is just the hostname, without a project path.
-->

---
layout: center
---

# Also HTTPS

<div style="max-width:740px; margin:24px auto 0; text-align:left; display:flex; flex-direction:column; gap:18px;">
  <div style="background:var(--bg-alt); border:1px solid var(--hairline); border-radius:10px; padding:16px 20px;">
    <div class="muted">GitHub requests a free certificate from Let's Encrypt</div>
        <div>☑ Enforce HTTPS</div>
  </div>
</div>

<!--
Once GitHub checks the DNS, it requests a free certificate from Let's Encrypt. That lets the browser verify
my domain and use HTTPS to encrypt the connection. I enable Enforce HTTPS so visitors use that secure connection.
I don't have to install the certificate myself.
-->

---
layout: center
---

# One domain, many apps

<div style="margin-top:18px; font-family:ui-monospace,monospace; font-size:1.15rem; line-height:1.9; display:inline-block; text-align:left;">
<div><b style="color:var(--accent);">ricoapon.nl</b> <span style="opacity:.6;">— my portfolio</span></div>
<div style="opacity:.85;">├─ spacepoints<span style="opacity:.6;">.ricoapon.nl</span></div>
<div style="opacity:.85;">├─ arismachine<span style="opacity:.6;">.ricoapon.nl</span></div>
<div style="opacity:.5;">└─ ...</div>
</div>

<!--
I wanted to use my domain for many websites. The main website `ricoapon.nl` would be my portfolio website.
Where would I host all my apps? I create subdomains like `spacepoints.ricoapon.nl` and `arismachine.ricoapon.nl`.
-->

---
layout: cover
background: /websites.jpg
---

# 26 websites and counting

<!--
Over the years I have created many more applications that I published under a different subdomain.
I counted last week and I have 26 already. Only a few are actually finished and still used. The rest
was just a fun small project.
NOTE FOR RICO: swap the four named favourites for whichever you'd rather show off; "…and 22 more" = 26 minus the four.
-->

---
layout: cover
background: /money.jpg
---

# And the bill?

<!--
And there is one final question that I will answer to finish the story. I was bothered by the cost.
How much did it actually cost me in the end?
-->

---
layout: cover
background: /end.jpg
---

# Thank you for listening!

<!--
Only 5 euros a year. Thank you for listening to my presentation!
-->
