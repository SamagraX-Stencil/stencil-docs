---
title: Navbar
sidebar_label: Navbar
---

<head>
  <title> Navbar </title>
  <meta content=" Navbar Component" />
</head>

The `Navbar` is a React component that creates a customizable top navigation bar using Material-UI components. It supports various features such as a hamburger menu, home icon, brand name, and logo placements.

<!-- <img src="/img/molecules/navbar.png" alt=" Navbar Molecule" /> -->

## Usage

```tsx
import Navbar from './packageName';

const App = () => {
  const [isOpen, setIsOpen] = React.useState(false);

  const centerLogoIcons = [{ id: 'main-logo', src: '/path/to/logo.png' }];

  return (
    <Navbar
      brandName="My App"
      onToggle={() => setIsOpen(!isOpen)}
      isOpen={isOpen}
      showHamburgerMenu
      showHomeIcon
      centerLogoIcons={centerLogoIcons}
    />
  );
};

export default App;
```

## Description

The `Navbar` component consists of the following elements:

- An AppBar component from Material-UI for the container
- Optional hamburger menu button
- Optional home icon
- Center section for logos and brand name
- Right section for additional logos

## Functionality

- Displays a hamburger menu button that triggers a toggle function
- Shows a home icon if enabled
- Renders center logos and brand name
- Displays right-aligned logos
- Supports custom styling for various sections

## Props

The `Navbar` component accepts the following props:

- `brandName`: Optional string for the brand name
- `onToggle`: Function to toggle the sidebar state
- `isOpen`: Boolean representing the sidebar open state
- `showHamburgerMenu`: Boolean to show/hide the hamburger menu (default: true)
- `showHomeIcon`: Boolean to show/hide the home icon (default: false)
- `leftHomeIcon`: Array of Icon objects for icons next to the home icon
- `centerLogoIcons`: Array of Icon objects for center logos
- `rightLogoIcons`: Array of Icon objects for right-aligned logos
- `style`: Object for custom styling of various sections
- `children`: React nodes to render additional content

## Styling

- The component uses Material-UI's styling system
- Custom styles can be passed via the `style` prop for different sections of the navbar

## Customization

This component provides flexibility for customization to suit your application's requirements. Here are some customization options:

### Style Customization

You can customize the appearance of the Navbar by passing a `style` object:

```tsx
const customStyle = {
  appBar: {
    /* custom styles for AppBar */
  },
  toolbar: {
    /* custom styles for Toolbar */
  },
  leftSection: {
    /* custom styles for left section */
  },
  centerSection: {
    /* custom styles for center section */
  },
  rightSection: {
    /* custom styles for right section */
  },
};

<Navbar
  // ... other props
  style={customStyle}
/>;
```

### Adding Custom Logos

To add or modify logos, update the respective icon arrays passed to the component:

```tsx
const centerLogoIcons = [
  { id: 'main-logo', src: '/path/to/main-logo.png' },
  { id: 'secondary-logo', src: '/path/to/secondary-logo.png' },
];

const rightLogoIcons = [{ id: 'partner-logo', src: '/path/to/partner-logo.png' }];

<Navbar
  // ... other props
  centerLogoIcons={centerLogoIcons}
  rightLogoIcons={rightLogoIcons}
/>;
```

## Notes

- The component is designed to work with a sidebar component, but the sidebar implementation is commented out in the provided code.
- A `ThemePicker` component is also commented out, indicating potential for theme customization.
- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
