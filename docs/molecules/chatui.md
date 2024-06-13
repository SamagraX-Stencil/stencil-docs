---
title: Chat UI
sidebar_label: Chat Ui
---

<head>
  <title> Chat Ui </title>
  <meta name="description" content="your meta content goes here" />
</head>

The ChatUI component provides a user interface for chatting, incorporating various features and configurations to enhance the user experience.

<img src="/img/molecules/chatui.png" alt="Home Page Molecule" />

## Usage

```tsx
import { ChatUI } from './ChatUi';

const App = () => {
  return <ChatUI />;
};

export default App;
```

## Description

The ChatUI component offers a messaging interface with support for sending and receiving messages. It integrates additional features such as sharing, downloading chats, providing feedback, and text-to-speech functionality.

## Functionality

- _Sending Messages:_ Users can type messages in the text input field and send them by clicking the send button.
- _Feedback:_ Users can provide feedback on messages, indicating whether they found them helpful or not.
- _Text-to-Speech:_ Enables users to listen to messages using the text-to-speech feature.
- _Share Chat:_ Allows users to share the chat conversation.
- _Download Chat:_ Enables users to download the chat conversation.
- _Transliteration:_ Supports typing in different languages using transliteration.

## Dependencies

- @samagra-x/chatui: Chat UI component library for React.
- react-hot-toast: Library for displaying toast notifications.
- @mui/material: Material-UI library for React components.

## Configuration

The ChatUI component offers flexibility for customization through its configuration options in config.json. Key configurations include:

```json

  "component": {

      "allowFeedback": true,
      "allowTextToSpeech": true,
      "transliterationApi": "",
      "allowTransliteration": true,
      "transliterationProvider": "bhashini",
      "transliterationSuggestions": 3,
      "transliterationInputLanguage": "en",
      "transliterationOutputLanguage": "hi"

  }
```

## Styling

The component utilizes CSS modules for styling. Theme colors can be configured through the theme object in config.json.

```json
  "theme":
    "primaryColor": {
            "value": "#fff"
    },
    "secondaryColor": {
            "value": "#219653"
    }
```

## Additional Actions

Users can perform additional actions like sharing or downloading the chat conversation through the icons provided on the UI.

## Notes

For further customization and integration, developers can modify the JSX structure, styles, and functionality according to specific project requirements.
