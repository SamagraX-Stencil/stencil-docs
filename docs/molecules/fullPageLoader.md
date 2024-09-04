---
title: FullPage Loader
sidebar_label: FullPage Loader
---

<head>
  <title> FullPage Loader </title>
  <meta content="FullPage Loader" />
</head>

The `FullPageLoader` is a React component that creates a full-screen loading overlay. It displays a customizable spinning loader and an optional label, providing a clear visual indication of loading or processing states across the entire application view.

## Usage

```tsx
import { FullPageLoader } from './FullPageLoader';

const App = () => {
  const [isLoading, setIsLoading] = React.useState(true);

  return (
    <div>
      <FullPageLoader loading={isLoading} color="#007bff" label="Loading..." />
      {/* Your app content */}
    </div>
  );
};

export default App;
```

## Description

The `FullPageLoader` component consists of:

- A full-screen Backdrop from Material-UI
- A custom spinning loader animation
- An optional label

## Functionality

- Displays a full-screen overlay when `loading` is true
- Shows a spinning loader animation
- Allows customization of loader color, background, and label
- Supports custom styling for the label

## Props

The `FullPageLoader` component accepts the following props:

- `loading`: Boolean to control the visibility of the loader
- `color`: Optional string for the loader color (default: '#25b09b')
- `background`: Optional string for the backdrop background color (default: 'rgba(0, 0, 0, 0.5)')
- `label`: Optional string for the loading label
- `labelStyle`: Optional object of type `React.CSSProperties` for custom label styling

## Styling

- The component uses inline styles for the loader animation
- The spinning animation is defined using a CSS `@keyframes` rule
- Material-UI's Backdrop component is used for the full-screen overlay

## Customization

This component provides several options for customization:

### Color and Background

You can customize the loader color and backdrop background:

```tsx
<FullPageLoader loading={true} color="#ff0000" background="rgba(255, 255, 255, 0.8)" />
```

### Label Customization

Add and style a label:

```tsx
<FullPageLoader loading={true} label="Please wait..." labelStyle={{ color: '#007bff', fontSize: '24px' }} />
```

## Animation

The loader uses a custom CSS animation for its spinning effect. The animation is defined in the component:

```css
@keyframes rotate {
  100% {
    transform: rotate(1turn);
  }
}
```

## Notes

- The component uses Material-UI's Backdrop for the full-screen overlay, ensuring consistent behavior with other Material-UI components.
- The loader animation is created using CSS box-shadow properties and a rotation animation.
- The z-index is set very high (99999) to ensure the loader appears above all other elements.
- For further customization, you can modify the JSX structure, styles, and animation according to your application's needs.
