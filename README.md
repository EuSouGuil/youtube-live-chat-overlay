# YouTube Live Chat Overlay CSS for OBS

This repository provides a **minimal, CSS-only solution** to turn the YouTube live chat popout into a **clean, transparent overlay** for use with **OBS (Open Broadcaster Software)**.

The goal of this project is **stability and simplicity**: remove all unnecessary YouTube UI elements and keep only the chat messages, optimized for OBS Browser Source.

---

## Features

* **Transparent background** for seamless overlay on any scene
* **Bottom-aligned messages**, ideal for live streams
* **Minimal layout**, no headers, input box, banners, or popups
* **OBS-friendly** (Browser Source compatible)
* **CSS-only** (no JavaScript)

### Default colors

* Regular users: **white**
* Moderators: **blue** (YouTube-style)
* Channel owner: **black** (configurable in CSS)
* Message text: **white**

---

## Installation

### 1. Open the YouTube chat popout

* Go to your YouTube live stream page
* Click the three dots in the chat panel
* Select **"Popout chat"**

Copy the URL from the new window.

---

### 2. Add the chat to OBS

1. In OBS, add a **Browser Source**
2. Paste the YouTube chat popout URL
3. Set the desired **width and height**
4. Paste the CSS from this repository into **Custom CSS**

Recommended OBS options:

* Enable **"Shutdown source when not visible"**
* Enable **"Refresh browser when scene becomes active"**

---

## Customization

This CSS is fully editable, but the most common adjustments are listed below.

### Message text color

```css
yt-live-chat-text-message-renderer {
    color: #ffffff !important;
}
```

Change `#ffffff` to any color you prefer.

---

### Regular user name styling

```css
#author-name {
    font-weight: 600 !important;
}
```

You can adjust font weight or spacing here.

---

### Channel owner name color

```css
yt-live-chat-text-message-renderer.yt-live-chat-author-is-owner #author-name {
    color: #000000 !important;
}
```

Change `#000000` to any color.

> Note: Due to YouTube internal styling, some color overrides may not apply consistently in all environments.

---

### Moderator name color

```css
yt-live-chat-text-message-renderer.yt-live-chat-author-is-moderator #author-name {
    color: #5da9ff !important;
}
```

---

## Limitations

* This project uses **CSS only**
* Some YouTube styles are controlled internally and may change over time
* Full control over certain colors (such as the channel owner name) is limited without JavaScript

The focus of this repository is **low maintenance and reliability**, not full visual customization.

---

## Contribution

Feel free to fork this repository and adapt it to your needs.

Pull requests are welcome if they:

* Keep the project CSS-only
* Improve stability or compatibility with OBS
* Avoid unnecessary complexity

---

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

A clean, simple, and stable YouTube live chat overlay — designed for
