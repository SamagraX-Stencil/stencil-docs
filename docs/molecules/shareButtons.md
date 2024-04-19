---
title: Share and Download buttons 
sidebar_label: Share & Download buttons
---

<head>
    <title> Share and Download buttons </title>
    <meta name="description" content="your meta content goes here" />
</head>

The `share-buttons` molecule is a React component designed for users actions to share and download chat.

<img src="/img/molecules/shareButtons.png" alt="Share button molecule" />

## Usage 

```tsx
import ShareButtons from './share-buttons';

const App = () => {
    return (
        <ShareButtons />
    );
}

export default App
```

## Description

The `ShareButtons` molecule consists of the following elements:

- Share button for sharing selected chat.
- Download button for downloading selected chat.

## State

- `shareLoader`: It is used to make share state active is share button is clicked
- `downloadLoader`: State active when download button is clicked

## Functionality

- Upon clicking the download button, the component initiates the download process.
- If share button is clicked it check if system provides share functionality then, a success message is displayed, and if not, an error message is displayed.

## Dependencies

- React: JavaScript library for building user interfaces.
- Material-UI (Mui): React components for faster and easier web development.
- React Hot Toast: Toast notification library for React applications.

## Configuration

- The default theme colors can be configured in the config.json file.
- The components can be configured in the config.json file.

## Styling

- CSS modules are used for styling the component.
 

## Customization

This molecule provides flexibility for customization to suit your application's requirements. Here are some customization options:

### Theme Customization

You can customize the theme colors by modifying the values in the `config.json` file. The theme object contains `primaryColor` and `secondaryColor` properties, allowing you to specify the colors according to your brand or design preferences.

```json
"theme": {
  "primaryColor": {
    "value": "#1e6231",
    "allowOverride": true
  },
  "secondaryColor": {
    "value": "#34a755",
    "allowOverride": true
  }
}
```

### Adding Custom Actions

To add custom actions such as downloading or sharing steps:

- **Download Chat Functionality**: Implement the download logic within the `downloadChat` function. You can trigger a download process with your backend service.

```tsx
const downloadChat = async (type: string) => {
    // perform your download chat logic here
  };
```

### Accessing share and download button
You can select weather which functionality you want by simply modifying `allowDownloadChat` and `allowShareChat` value in the `config.json` file.

```json
"component": {
      "allowOverride": false,
      "allowDownloadChat": true,
      "allowShareChat": true
    }

```

## Notes

- This molecule does not handle actual download chat feature. It simulates the process by displaying a downloading message upon clicking the download button and share successful message upon clicking share button.
- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.