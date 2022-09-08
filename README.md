<h1 align="center">
  <a href="https://vite-ruby.netlify.app/">
    <img src="https://raw.githubusercontent.com/ElMassimo/vite_ruby/main/logo.svg" width="200px"/>
  </a>

  <br>

  <a href="https://github.com/excid3/jumpstart">Jumpstart Rails</a>
  with
  <a href="https://vite-ruby.netlify.app/">Vite</a>

  <p align="center">
    <a href="https://github.com/ElMassimo/vite_ruby/blob/master/LICENSE.txt">
      <img alt="License" src="https://img.shields.io/badge/license-MIT-428F7E.svg"/>
    </a>
  </p>
</h1>

[jumpstart]: https://github.com/excid3/jumpstart
[pro]: https://jumpstartrails.com
[vite_rails]: https://github.com/ElMassimo/vite_rails/tree/main/vite_rails
[esbuild]: https://github.com/evanw/esbuild
[significantly faster]: https://github.com/evanw/esbuild#why
[no bundling]: https://vitejs.dev/guide/why.html#the-problems
[bundling]: https://vitejs.dev/guide/why.html#why-bundle-for-production
[JS From Routes]: https://github.com/ElMassimo/js_from_routes
[vite-plugin-stimulus-hmr]: https://github.com/ElMassimo/vite-plugin-stimulus-hmr
[vite-plugin-full-reload]: https://github.com/ElMassimo/vite-plugin-full-reload

This repo is a fork of the [__Jumpstart Rails__][jumpstart] template, which is
like Laravel Spark, for Rails.

This fork replaces webpacker with [__Vite Rails__][vite_rails], and extends the
basic setup to include a working Stimulus example and Hotwire integration.

## Features ⚡️

- 💡 Instant server start
- ⚡️ Blazing fast hot reload
- 🚀 Stimulus + Turbo Hotwire
- 🛤 Path and API Helpers: [JS From Routes]
- [And more!][jumpstart]

It adds <kbd>[vite-plugin-stimulus-hmr]</kbd> for instant feedback on changes to
your Stimulus controllers, <kbd>[vite-plugin-full-reload]</kbd> to automatically
refresh the page when editing the Rails layout or templates, and __[JS From Routes]__
to automatically generate path and API helpers from the routes.

## Demo 🎥

Changes to Stimulus controllers don't require a full page refresh.

<a href="https://user-images.githubusercontent.com/1158253/107971586-6deb2480-6f91-11eb-8919-100ca36f3683.mp4" rel="noreferrer" target="_blank">
  <img width="836" alt="Screen Shot 2021-02-15 at 13 27 22" src="https://user-images.githubusercontent.com/1158253/107971695-8e1ae380-6f91-11eb-9ef7-9fed47d4d3be.png">
</a>

This feature is powered by <kbd>[vite-plugin-stimulus-hmr](https://github.com/ElMassimo/vite-plugin-stimulus-hmr)</kbd>.

## Installation 💿

```bash
rails new myapp -d postgresql -m https://raw.githubusercontent.com/ElMassimo/jumpstart-vite/master/template.rb
```

For the rest of the instructions, head to [Jumpstart Rails][jumpstart].

<br/>

## Video Comparison 🎥

Webpacker on the left, Vite on the right. I run `foreman start`, wait until the page loads, then kill the process and run it a second time.

<a href="https://user-images.githubusercontent.com/1158253/107697132-98876580-6c91-11eb-9bda-567b1b9f6cf5.mp4" target="_blank" rel="noreferrer">
  <img width="832" alt="Screen Shot 2021-02-12 at 10 03 51" src="https://user-images.githubusercontent.com/1158253/107771581-b7c9d580-6d19-11eb-9184-48f97b47f2cf.png">
</a>

### Webpacker

Installing the vanilla Jumpstart template takes 5 minutes, be prepared to watch
`node-sass` spin for a while, along with all the webpack dependencies.

<img width="350" alt="jumpstart-webpacker-node-sass" src="https://user-images.githubusercontent.com/1158253/107692177-2e6bc200-6c8b-11eb-8943-c03a2f3a5023.png"><img width="480" alt="jumpstart-webpacker-installation" src="https://user-images.githubusercontent.com/1158253/107692176-2e6bc200-6c8b-11eb-9511-69124f6bf844.png">

Once it's installed, and we have run `bin/rake db:create db:migrate`, we'll start it twice:

<a href="https://user-images.githubusercontent.com/1158253/107692172-2ca1fe80-6c8b-11eb-9e2b-d44c069a45b0.mp4" target="_blank" rel="noreferrer">
  <img width="828" alt="Screen Shot 2021-02-11 at 17 21 03" src="https://user-images.githubusercontent.com/1158253/107694027-a1763800-6c8d-11eb-935a-76facdaba764.png">
</a>

Cold start is particularly slow, and it locks Rails rendering.

<br/>

### Vite ⚡️

Installing the Jumpstart template with Vite takes 1 minute.

<img width="359" alt="jumpstart-vite-installation" src="https://user-images.githubusercontent.com/1158253/107692180-2f045880-6c8b-11eb-9fbe-8289100d22b8.png">

Once it's installed, and we have run `bin/rake db:create db:migrate`, we'll start it twice:

<a href="https://user-images.githubusercontent.com/1158253/107692148-2744b400-6c8b-11eb-833a-7a7d4e46e6be.mp4" target="_blank" rel="noreferrer">
  <img width="828" alt="Screen Shot 2021-02-11 at 17 21 25" src="https://user-images.githubusercontent.com/1158253/107694019-9e7b4780-6c8d-11eb-96da-d1e65f3471a1.png">
</a>

Loads only 9 seconds after `foreman start`, and is also running a Stimulus example.

Subsequent loads are significantly faster.

<br/>

## How does it work? 🤔

Vite is powered by [esbuild], which can process files [significantly faster] than Webpack.

Vite [does not bundle your code during development][no bundling], which means
as your app grows, the dev server will still start fast, and your changes will
continue be __updated instantly__.

In production, Vite [bundles your code][bundling] with tree-shaking, lazy-loading,
and common chunk splitting out of the box, to achieve optimal loading performance.

<br/>

## Special Thanks 🙌

- [Jumpstart Rails][jumpstart]: 👉 Have in mind they have also built [Jumpstart Pro][pro] which also includes payments with Stripe & Braintree, team accounts, TailwindCSS, and much more.
