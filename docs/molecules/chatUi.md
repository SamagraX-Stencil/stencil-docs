---
title: Chat UI
sidebar_label: Chat Ui
---

<head>
  <title> Chat Ui </title>
  <meta name="description" content="your meta content goes here" />
</head>

The `ChatUI` component provides a user interface for chatting, incorporating various features and configurations to enhance the user experience.

<img src= "/img/molecules/chatui.png" alt="Home Page Molecule" />

## Usage

```
import { ChatUI } from './ChatUi';

const App = () => {
  return (
    <ChatUI />
  );
}

export default App;



```

## Description

 The `ChatUI` component offers a messaging interface with support for sending and receiving messages. It integrates additional features such as sharing, downloading chats, providing feedback, and text-to-speech functionality.

## Functionality

- **Sending Messages:** Users can type messages in the text input field and send them by clicking the send button.
- **Feedback:** Users can provide feedback on messages, indicating whether they found them helpful or not.
- **Text-to-Speech:** Enables users to listen to messages using the text-to-speech feature.
- **Share Chat:** Allows users to share the chat conversation.
- **Download Chat:** Enables users to download the chat conversation.
- **Transliteration:** Supports typing in different languages using transliteration.

## Dependencies

- `@samagra-x/chatui`: Chat UI component library for React.
- `react-hot-toast`: Library for displaying toast notifications.
- `@mui/material`: Material-UI library for React components.


## Configuration

The `ChatUI` component offers flexibility for customization through its configuration options in `config.json`. Key configurations include:

 
```json
 
  "component": {
      "allowOverride": false,
      "placeholder": "Ask Your Question",
      "allowFeedback": true,
      "positiveFeedbackText": "Helpful",
      "negativeFeedbackText": "Not Helpful",
      "allowTextToSpeech": true,
      "textToSpeechLabel": "Click to hear",
      "allowShareChat": true,
      "shareChatText": "Share",
      "allowDownloadChat": true,
      "downloadChatText": "Download",
      "allowTransliteration": true,
      "transliterationApi": "",
      "transliterationInputLanguage": "",
      "transliterationOutputLanguage": "",
      "transliterationProvider": "",
      "transliterationSuggestions": 3,
      "rightAction": null,
      "leftAction": null
  }
```

## Styling

The component utilizes CSS modules for styling. Theme colors can be configured through the `theme` object in `config.json`.
```json
  "theme": 
    "primaryColor": {
      "allowOverride": true,
      "value": "#fff"
    },
    "secondaryColor": {
      "allowOverride": true,
      "value": "#219653"
    }
  ```

## Additional Actions

Users can perform additional actions like sharing or downloading the chat conversation through the icons provided on the UI.

## Notes

For further customization and integration, developers can modify the JSX structure, styles, and functionality according to specific project requirements.