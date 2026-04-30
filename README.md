# 🎵 Modern HTML5 Music Player

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Made with HTML5](https://img.shields.io/badge/Made%20with-HTML5-orange?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/Styled%20with-CSS3-blue?logo=css3)
![JavaScript](https://img.shields.io/badge/Powered%20by-JavaScript-yellow?logo=javascript)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Demo](https://img.shields.io/badge/Demo-Live-blue?logo=githubpages)
![Stars](https://img.shields.io/github/stars/Pekly/modern-html5-music-player?style=social)
![Last Commit](https://img.shields.io/github/last-commit/Pekly/modern-html5-music-player)
![Repo Size](https://img.shields.io/github/repo-size/Pekly/modern-html5-music-player)
![Version](https://img.shields.io/badge/Version-A26.5.1-blue)

---

A self-contained, open-source HTML5 music player designed to be embedded anywhere.

It includes a clean responsive UI, real-time visualizer, playlist search, theme switching, favorites, keyboard shortcuts, playback speed control, and support for both audio and video files.

🎧 [Live Demo →](https://pekly.github.io/modern-html5-music-player/)

---

## 🖼️ Preview

![Music Player Preview](https://raw.githubusercontent.com/Pekly/modern-html5-music-player/main/assets/preview_banner.jpg)

---

## ✨ Features

- 🎨 Fully Responsive, works from mobile to desktop
- 🔊 Audio Visualizer, real-time frequency bars using the Web Audio API
- 🎵 Audio + Video Support, supports `.mp3` and `.mp4` playlist items
- 🎚️ Full Playback Controls, play, pause, previous, next, volume, and draggable timeline
- ⚡ Speed Control, switch between `1x`, `1.25x`, `1.5x`, and `2x`
- 🔀 Shuffle + Repeat, available from the playlist modal
- ❤️ Favorites System, like songs and filter favorites
- 🔍 Searchable Playlist, find songs by title or artist
- 📌 Play Next Queue, send any playlist item to play next
- 🔥 Play Count Badge, highlights songs played multiple times
- 🎬 Video Badges, marks playlist items that use video files
- 🧩 Settings Modal, theme switching moved into a cleaner settings panel
- 🌈 Multiple Themes, Spotify Dark, Arctic Light, Cyberpunk, Sunset, Hacker Terminal, and Vaporwave
- 💤 Sleep Timer, cycle between 15, 30, and 60 minutes
- ⌨️ Keyboard Shortcuts, quick control without using the mouse
- 💾 Persistent State, remembers theme, volume, shuffle, repeat, favorites, and last track
- 🪄 Collapsible Interface, minimize into a small floating music button
- ♿ Accessible Controls, includes ARIA labels and media session support
- 🧩 Single-File Design, HTML, CSS, and JavaScript in one file
- 🎨 Easy Customization, edit CSS variables and `playerConfig`

---

## 🚀 Installation

### Method 1, Using an `<iframe>` Recommended

This is the easiest and safest option. It keeps the player code isolated from your website.

1. Place `music_player.html` somewhere in your project.

Example:

```txt
/components/music_player.html
````

2. Add this before your closing `</body>` tag:

```html
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

Make sure the `src` path points to your real player file.

---

### Method 2, Direct Embedding Advanced

Use this if you want deeper control over the player.

1. Copy the external `<link>` tags from `music_player.html` into your site’s `<head>`.
2. Copy the `<style>` block into your CSS file or inside your site’s `<head>`.
3. Place the player HTML before your closing `</body>` tag.
4. Place the `<script>` code after the player HTML.

The player uses this main structure:

```html
<div id="music-player" class="player-hidden">
  ...
</div>
```

The new version uses a hidden `<video>` element as the playback source, so it can play both audio files and video files.

```html
<video id="audio-player" crossorigin="anonymous" playsinline></video>
```

---

## 🎧 Playlist Setup

Edit the `playlistData` array inside the `<script>` section.

Each item needs:

* `title`
* `artist`
* `url`
* `albumArtUrl`

Example:

```js
const playlistData = [
  {
    title: 'Song Title',
    artist: 'Artist Name',
    url: 'https://example.com/song.mp3',
    albumArtUrl: 'https://example.com/cover.jpg'
  },
  {
    title: 'Video Track',
    artist: 'Artist Name',
    url: 'https://example.com/video.mp4',
    albumArtUrl: 'https://example.com/video-cover.jpg'
  }
];
```

Supported file types:

* `.mp3`
* `.mp4`

Host your media files somewhere public, then paste the direct URL into `url`.

---

## ⚙️ Player Config

Most options live inside the `playerConfig` object.

```js
const playerConfig = {
  githubUsername: 'Pekly',
  promotionEnabled: true,
  enableVisualizer: true,
  enableSpeedControl: true,
  enableSleepTimer: true,
  enableThemeSwitcher: true,
  enableLikeSystem: true,
  defaultTheme: 'spotify',
  themes: {
    // theme objects here
  }
};
```

### Options

| Option                |    Type | Description                              |
| --------------------- | ------: | ---------------------------------------- |
| `githubUsername`      |  string | Used for the GitHub promotion link       |
| `promotionEnabled`    | boolean | Shows or hides the GitHub promo banner   |
| `enableVisualizer`    | boolean | Enables the real-time visualizer         |
| `enableSpeedControl`  | boolean | Shows or hides the speed button          |
| `enableSleepTimer`    | boolean | Shows or hides the sleep timer           |
| `enableThemeSwitcher` | boolean | Enables the settings theme list          |
| `enableLikeSystem`    | boolean | Enables favorites and favorite filtering |
| `defaultTheme`        |  string | Sets the default theme key               |

---

## 🎨 Customization

You can customize the player using CSS variables.

```css
:root {
  --background-color: #121212;
  --primary-text: #ffffff;
  --secondary-text: #b3b3b3;
  --highlight-color: #1DB954;
  --border-color: #282828;
  --panel-bg: rgba(25, 20, 20, 0.85);
  --scrollbar-track-color: rgba(0,0,0,0.1);
  --scrollbar-thumb-color: #535353;
  --font-stack: 'Poppins', sans-serif;
}
```

You can also add more themes inside `playerConfig.themes`.

Example:

```js
myTheme: {
  name: 'My Theme',
  '--background-color': '#111111',
  '--primary-text': '#ffffff',
  '--secondary-text': '#aaaaaa',
  '--highlight-color': '#ff4fd8',
  '--border-color': '#333333',
  '--panel-bg': 'rgba(20, 20, 20, 0.9)',
  '--scrollbar-track-color': 'rgba(255,255,255,0.1)',
  '--scrollbar-thumb-color': '#ff4fd8',
  '--font-stack': "'Poppins', sans-serif"
}
```

---

## ⌨️ Keyboard Shortcuts

| Key           | Action         |
| ------------- | -------------- |
| `Space`       | Play or pause  |
| `Arrow Right` | Next track     |
| `Arrow Left`  | Previous track |
| `M`           | Mute or unmute |

The shortcuts are ignored while typing in search fields.

---

## 🧠 Saved Data

The player uses `localStorage` to remember user settings.

Saved values include:

* Current track
* Volume
* Theme
* Shuffle state
* Repeat mode
* Favorite songs
* Play counts
* GitHub promo dismissal

Main storage keys:

```txt
oss_music_player_currentTrack
oss_music_player_volume
oss_music_player_theme
oss_music_player_isShuffle
oss_music_player_repeatMode
oss_music_player_favorites
oss_play_counts
oss_music_player_promo_seen
```

---

## 📱 Mobile Behavior

The player is built for small screens first.

On mobile:

* The player stretches near the bottom of the screen
* The playlist opens above the player
* Controls stay touch-friendly
* Volume and timeline sliders remain easy to use

On desktop:

* The player sits at the bottom-left
* The playlist and settings panels open above it
* Hover effects reveal extra controls

---

## 🧪 Browser Support

The player works best in modern browsers.

Recommended:

* Chrome
* Edge
* Firefox
* Safari

Some features depend on browser support:

* Web Audio API for the visualizer
* Media Session API for system media controls
* HTML5 video playback for `.mp4` tracks
* `localStorage` for saved preferences

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Make your changes
3. Test the player in a browser
4. Commit with a clear message
5. Open a Pull Request

Found a bug or have an idea?

Open an issue here:

[GitHub Issues](https://github.com/Pekly/modern-html5-music-player/issues)

---

## 📜 License

This project is licensed under the MIT License.

You are free to:

* Use it
* Modify it
* Share it
* Embed it in your own projects

Do not claim the original project as your own.

Attribution is appreciated, but not required.

---

## 🧠 Credits

Created by Pekly.

Built with:

* HTML5
* CSS3
* Vanilla JavaScript
* Font Awesome
* Google Fonts

---

## 🌟 Support the Project

If this project helps you, star the repo.

⭐ [Star this project on GitHub](https://github.com/Pekly/modern-html5-music-player)
