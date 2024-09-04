---
title: Blinking Spinner
sidebar_label: Blinking Spinner
---

<head>
  <title> Create New Molecule </title>
  <meta name="description" content="your meta content goes here" />
</head>

The `BlinkingSpinner` is a simple React component that creates a minimalistic, blinking spinner animation. It's designed to provide a visual indication of loading or processing states in a subtle and non-intrusive manner.

## Usage

```tsx
import BlinkingSpinner from 'packageName';

const App = () => {
  return (
    <div>
      Loading <BlinkingSpinner spinerStyle={{ height: '20px', backgroundColor: '#007bff' }} />
    </div>
  );
};

export default App;
```

## Description

The `BlinkingSpinner` component consists of a single element that blinks using CSS animations. It appears as a vertical line that fades in and out, creating a simple loading indicator.

## Functionality

- Displays a blinking vertical line
- Uses CSS animations for the blinking effect
- Allows customization of the spinner's appearance through props

## Props

The `BlinkingSpinner` component accepts the following prop:

- `spinerStyle`: An object of type `CSSProperties` to customize the appearance of the spinner

## Styling

- The component uses inline styles for basic styling
- Custom styles can be passed via the `spinerStyle` prop
- The blinking animation is defined using a CSS `@keyframes` rule

## Customization

This component provides flexibility for customization to suit your application's requirements. Here are some customization options:

### Style Customization

You can customize the appearance of the BlinkingSpinner by passing a `spinerStyle` object:

```tsx
const customStyle: CSSProperties = {
  height: '30px',
  width: '2px',
  backgroundColor: '#ff0000',
  marginLeft: '5px',
};

<BlinkingSpinner spinerStyle={customStyle} />;
```

### Animation Customization

To modify the blinking animation, you can adjust the `@keyframes` rule in the component:

```tsx
<style>
  {`
    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.2; }
    }
  `}
</style>
```

## Default Styles

The component comes with default styles:

```typescript
const styles = {
  spinner: {
    display: 'inline-block',
    height: '15px',
    width: '1px',
    animation: 'blink 0.5s infinite',
    backgroundColor: '#000',
  },
};
```

## Notes

- The component uses inline styles and a CSS animation for simplicity and ease of use.
- The blinking effect is achieved using opacity changes in the CSS animation.
- For further customization, you can modify the JSX structure, styles, and animation according to your application's needs.
