# YouTube Live Chat Overlay CSS for OBS

This custom CSS is designed to transform the popup URL of a YouTube live chat into a simple, lightweight, and transparent overlay for [OBS (Open Broadcaster Software)](https://github.com/obsproject/obs-studio). The CSS removes all unnecessary elements from the HTML, creating a clean and minimalistic chat overlay perfect for live streaming.

## Features

- **Transparent Background**: Ensures the chat area blends seamlessly with your stream.
- **Full Width and Height**: The chat area takes up the entire popup window, providing maximum visibility.
- **Owner Highlight**: Messages from the owner are highlighted with a distinct color.
- **Removal of Unnecessary Elements**: Strips away headers, footers, input areas, and other non-essential components to keep the chat overlay clean and focused.

## Installation

1. **Open YouTube Live Chat in a Popup**:
    - Go to your YouTube live stream page.
    - Open the chat in a popup window by clicking on the three dots in the top right corner of the chat and selecting "Popout chat."

2. **Add Custom CSS in OBS**:
    - In OBS, add a new browser source.
    - Paste the URL of your YouTube live chat popup.
    - Under "Custom CSS," paste the following code:

    ```css
    /* Define styles for the chat area */
    body, yt-live-chat-renderer, yt-live-chat-item-list-renderer {
        background-color: transparent !important;
        margin: 0 !important;
        overflow: hidden !important;
        width: 100% !important;
        height: 100% !important;
    }

    /* Adjusts message area height and defines positioning */
    yt-live-chat-item-list-renderer {
        position: absolute;
        bottom: 20px;
        height: calc(100% - 40px) !important;
        padding: 0 10px !important;
        box-sizing: border-box !important;
    }

    /* Styles for messages and owner author color */
    yt-live-chat-text-message-renderer {
        background-color: transparent !important;
        width: calc(100% - 20px) !important;
        margin: 5px 0 !important;
        padding: 0 !important;
        font-size: 14px !important;
        color: #fff !important;
        white-space: pre-wrap !important;
    }

    /* Owner author color */
    yt-live-chat-text-message-renderer.yt-live-chat-text-message-author-is-owner #author-name {
        color: #000 !important;
    }

    /* Removes unnecessary elements and notices */
    #header, #primary-content, #secondary-content, #footer,
    yt-live-chat-header-renderer, yt-live-chat-message-input-renderer,
    yt-live-chat-action-panel-renderer, yt-live-chat-message-prompt-renderer,
    yt-live-chat-viewer-engagement-message-renderer,
    yt-live-chat-text-message-renderer #img, ::-webkit-scrollbar,
    yt-live-chat-membership-only-mode-message-renderer,
    yt-live-chat-mode-change-message-renderer,
    yt-live-chat-restricted-participation-renderer,
    yt-live-chat-author-chip-renderer,
    yt-live-chat-legacy-paid-message-renderer,
    yt-live-chat-legacy-paid-sticker-renderer,
    yt-live-chat-pinned-message-renderer,
    yt-live-chat-viewer-engagement-message-renderer,
    yt-live-chat-text-message-renderer yt-icon,
    yt-live-chat-renderer #input, yt-live-chat-text-message-renderer yt-live-chat-author-chip-renderer,
    yt-live-chat-subscription-message-renderer,
    yt-live-chat-paid-message-renderer,
    yt-live-chat-paid-sticker-renderer,
    yt-live-chat-restricted-participation-renderer {
        display: none !important;
    }
    ```

3. **Adjust Browser Source Settings**:
    - Set the width and height of the browser source to match your stream layout.
    - Ensure the "Shutdown source when not visible" option is unchecked to keep the chat connected even when switching scenes.

## Usage

With the custom CSS applied, your YouTube live chat will appear as a streamlined, transparent overlay in OBS, showing only the chat messages and highlighting messages from the owner. This setup is ideal for creating an engaging and visually appealing live stream.

## Contribution

Feel free to fork this repository and make your own adjustments. Pull requests are welcome if you have improvements or additional features you would like to add.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Enjoy your clean and simple YouTube live chat overlay in OBS!

## Customization

You can customize the colors used for the author names and the channel owner's name in the chat overlay. Here's how to do it:

### Changing the Color of Author Names

To change the color of the author names, find the following section in the `styles.css` file:

```css
yt-live-chat-text-message-renderer {
    color: #fff !important;
}
```

Replace #fff with the desired color code. For example, to change the color to blue, you would use:

```css
Copy code
yt-live-chat-text-message-renderer {
    color: #0000ff !important;
}
```

Changing the Color of the Channel Owner's Name
To change the color of the channel owner's name, find the following section in the styles.css file:

```css
Copy code
yt-live-chat-text-message-renderer.yt-live-chat-text-message-author-is-owner #author-name {
    color: #000 !important;
}

```
Replace #000 with the desired color code. For example, to change the color to red, you would use:

```css
Copy code
yt-live-chat-text-message-renderer.yt-live-chat-text-message-author-is-owner #author-name {
    color: #ff0000 !important;
}
```
