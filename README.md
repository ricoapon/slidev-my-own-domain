## The Story Of How I Bought My Domain

For years I published my side projects on free hosting and just lived with the clunky `greent13.github.io/elitefour`
links it generated for me. Buying a domain felt like a waste of money for what were, after all, just unfinished 
hobby projects that never felt professional enough to deserve one. Then a friend convinced me otherwise, and I've 
been hooked ever since: today dozens of my projects each have a proper name. Even the slides for this Ignite session 
use the domain. In this fast-paced talk I'll tell you how that one conversation changed my mind, and why setting it 
up was far easier than I ever expected. And the costs? It's one of the lowest bills I pay all year.

## Info

This is the slide deck, made using [Slidev](https://sli.dev/), for my presentation that takes 5 minutes (exactly 15
seconds per slide).

## Present

Either go to https://myowndomain.ricoapon.nl/ or run `npm run dev`.

## Present offline

This repository has been created with the possibility to run offline. To do so, first execute the following commands
while you have internet:

1. `npm install`
2. `npm run build`

You should now have a `dist` directory with the files for the presentation. Run this command when having no internet:

```
python -m http.server --directory dist
```

The presentation is now available at http://localhost:8000.
