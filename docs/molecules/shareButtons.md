---
title: Share and Download buttons
sidebar_label: Share & Download buttons
---

<head>
  <title> Share and Download buttons </title>
  <meta name="description" content="your meta content goes here" />
</head>

The `ShareButtons` is a React component that provides customizable share and download buttons. It's designed to be positioned absolutely within a parent container, typically used in chat or content sharing interfaces.

<!-- <img src="/img/molecules/shareButtons.png" alt="Share button molecule" /> -->

## Usage

```tsx
import ShareButtons from './package';

const App = () => {
  const handleButton = (event, type) => {
    if (type === 'share') {
      // Handle share action
    } else if (type === 'download') {
      // Handle download action
    }
  };

  return (
    <div style={{ position: 'relative' }}>
      <ShareButtons allowShareChat={true} allowDownloadChat={true} handleButton={handleButton} />
      {/* Your main content */}
    </div>
  );
};

export default App;
```

## Description

The `ShareButtons` component consists of:

- A container div positioned absolutely
- Optional share button with icon and text
- Optional download button with icon and text
- Loading indicators for both buttons

## Functionality

- Displays share and/or download buttons based on props
- Triggers a callback function when buttons are clicked
- Shows loading indicators when share or download actions are in progress
- Allows extensive customization of styles

## Dependencies

- React: JavaScript library for building user interfaces
- Material-UI (MUI): React components for faster and easier web development

## Props

The `ShareButtons` component accepts the following props:

- `allowShareChat`: Boolean to show/hide the share button (default: false)
- `allowDownloadChat`: Boolean to show/hide the download button (default: false)
- `handleButton`: Function called when a button is clicked, receives event and button type ('share' or 'download')
- `shareLoader`: Boolean to show/hide loading indicator for share button
- `downloadLoader`: Boolean to show/hide loading indicator for download button
- `style`: Object for custom styling of various elements

## Styling

- The component uses inline styles for positioning and basic appearance
- Custom styles can be passed via the `style` prop for fine-grained control

## Customization

This component provides several options for customization:

### Style Customization

You can customize the appearance of different parts of the component:

```tsx
<ShareButtons
  // ... other props
  style={{
    container: { background: 'rgba(0, 0, 0, 0.1)' },
    button: { padding: '10px' },
    icon: { color: '#007bff' },
    text: { fontSize: '12px' },
    divider: { margin: '5px 0' },
  }}
/>
```

### Button Visibility

Control which buttons are displayed:

```tsx
<ShareButtons
  allowShareChat={true}
  allowDownloadChat={false}
  // ... other props
/>
```

## Notes

- The component is designed to be positioned absolutely within a relative parent container.
- It uses Material-UI icons and components for consistency with Material Design.
- The buttons are rendered only if either `allowShareChat` or `allowDownloadChat` is true.
- A divider is shown between the buttons only if both are enabled.
- The component uses the 'Mulish-bold' font family for button text, ensure this font is available in your application.
- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
