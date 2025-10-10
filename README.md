# 🎵 Modern HTML5 Music Player  

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)  ![Made with HTML5](https://img.shields.io/badge/Made%20with-HTML5-orange?logo=html5&logoColor=white)  ![CSS3](https://img.shields.io/badge/Styled%20with-CSS3-blue?logo=css3)  ![JavaScript](https://img.shields.io/badge/Powered%20by-JavaScript-yellow?logo=javascript)  ![Status](https://img.shields.io/badge/Status-Active-brightgreen)  ![Demo](https://img.shields.io/badge/Demo-Live-blue?logo=githubpages)  ![Stars](https://img.shields.io/github/stars/Pekly/modern-html5-music-player?style=social)  ![Last Commit](https://img.shields.io/github/last-commit/Pekly/modern-html5-music-player)  ![Repo Size](https://img.shields.io/github/repo-size/Pekly/modern-html5-music-player)  

---

A self-contained, open-source music player designed to be embedded anywhere.  
It features a clean, modern UI, real-time visualizer, and full playback controls — all without ads or external dependencies.

🎧 **[Live Demo →](https://pekly.github.io/modern-html5-music-player/)**  

---

## 🖼️ Preview  
![Music Player Preview](https://raw.githubusercontent.com/Pekly/modern-html5-music-player/main/assets/preview_banner.jpg)

---
## ✨ Features

* 🎨 **Fully Responsive** — Works smoothly from mobile to desktop
* 🔊 **Audio Visualizer** — Real-time frequency bars (desktop)
* 🎚️ **Full Controls** — Play, pause, next, shuffle, repeat, volume, draggable timeline
* 👆 **Touch-Friendly** — Larger tap targets for mobile use
* 💾 **Persistent State** — Remembers volume, shuffle, last track
* 🪄 **Collapsible Interface** — Minimize into a floating icon
* 🔍 **Searchable Playlist** — Popup playlist with filter
* ♿ **Accessible** — ARIA support for screen readers
* 🧩 **Single-File Design** — Everything (HTML, CSS, JS) in one file
* 🎨 **Customizable** — Edit CSS variables to match your design

---

## 🚀 Installation

### Method 1 — Using an `<iframe>` (Recommended)

Easiest and safest option — keeps player code isolated.

1. Place `music_player.html` (or your built player file) somewhere in your project (e.g. `/components`).
2. Embed it just before `</body>`:

   ```html
   <!-- Responsive Music Player -->
   <iframe
     src="/components/music_player.html"
     style="
       border: none;
       position: fixed;
       bottom: 10px;
       right: 10px;
       left: 10px;
       width: auto;
       height: 75px;
       z-index: 1000;
     "
     title="Music Player"
   ></iframe>

   <style>
     @media (min-width: 900px) {
       iframe[title='Music Player'] {
         left: 20px;
         right: auto;
         width: 350px;
       }
     }
   </style>
   ```

✅ Ensure the `src` path correctly points to your `music_player.html`.

---

### Method 2 — Direct Embedding (Advanced)

For deeper control:

* Copy the `<link>` tags (fonts, icons) from `music_player.html` into your site’s `<head>`.
* Paste the `<style>` block into your CSS or within `<head>`.
* Insert the player markup:

  ```html
  <div id="music-player">…</div>
  <audio id="audio-player">…</audio>
  ```

  just before `</body>`.
* Append the `<script>` code right after those elements.

---

## 🎧 Playlist Setup

Configure your playlist via the `playlistData` array in the `<script>`:

```js
const playlistData = [
  {
    title: 'Song Title',
    artist: 'Artist Name',
    url: 'https://…/your-song.mp3',
    albumArtUrl: 'https://…/your-album-art.jpg'
  },
  // plus more songs...
];
```

Host your `.mp3` files somewhere accessible (GitHub Pages, your server, etc.), then reference them via URL.

---

## 🎨 Customization

At the top of your CSS (in the `<style>` block) you can tweak the look:

```css
:root {
  --primary-text: #ffffff;
  --secondary-text: #b3b3b3;
  --highlight-color: #1DB954;
  --panel-bg: rgba(25, 20, 20, 0.85);
  --font-stack: 'Poppins', sans-serif;
}
```

You can also extend or modify theme definitions in the `playerConfig.themes` object in the JS.

---

## 🤝 Contributing

Contributions are always welcome! 🙌

1. Fork the repository
2. Make your changes (code, design, docs)
3. Commit with a clear message
4. Open a Pull Request

Have a suggestion or bug?
👉 [Open an Issue](https://github.com/Pekly/modern-html5-music-player/issues) to discuss before coding.

---

## 📜 License

This project is licensed under the **MIT License**.

* ✅ Free to use, modify, and distribute
* ❌ Do not claim it as your own
* 💬 Attribution is appreciated (but not required)

---

## 🧠 Credits

Created with ❤️ by Pekly and
Built using **HTML5**, **CSS3**, and **Vanilla JS**

---

## 🌟 Support the Project

If this project helps you,
⭐ **Star this repo** — it’s a small gesture that goes a long way.
