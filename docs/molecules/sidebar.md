---
title: Sidebar
sidebar_label: Sidebar
---

<head>
  <title> Sidebar </title>
  <meta content=" Sidebar Component" />
</head>

The `Sidebar` is a React component that creates a customizable drawer-style sidebar using Material-UI components. It supports various features such as language switching, profile display, navigation links, and a logout option.

<!-- <img src="/img/molecules/sidebar.png" alt=" Sidebar Molecule" /> -->

## Usage

```tsx
import Sidebar from './packageName';
import { Home, Settings } from '@mui/icons-material';

const App = () => {
  const [isOpen, setIsOpen] = React.useState(false);
  const [activeLanguage, setActiveLanguage] = React.useState('en');

  const links = [
    { label: 'Home', icon: <Home />, route: '/' },
    { label: 'Settings', icon: <Settings />, route: '/settings' },
  ];

  const languages = [
    { name: 'English', value: 'en' },
    { name: 'Spanish', value: 'es' },
  ];

  const handleLanguageClick = (event: SelectChangeEvent<string>) => {
    setActiveLanguage(event.target.value as string);
  };

  const handleLogOut = () => {
    // Handle logout logic
  };

  return (
    <Sidebar
      isOpen={isOpen}
      onToggle={() => setIsOpen(!isOpen)}
      showProfileIcon
      showLangSwitcher
      profileText="John Doe"
      links={links}
      handleLogOutButton={handleLogOut}
      languages={languages}
      activeLanguage={activeLanguage}
      handleLanguageClick={handleLanguageClick}
    />
  );
};

export default App;
```

## Description

The `Sidebar` component consists of the following elements:

- A Drawer component from Material-UI for the sidebar container
- Optional language picker
- Optional profile display
- List of navigation links
- Logout button

## Functionality

- Opens and closes based on the `isOpen` prop
- Displays a language picker if `showLangSwitcher` is true
- Shows a profile section if `showProfileIcon` is true
- Renders a list of navigation links
- Provides a logout button
- Supports custom styling for various elements

## Dependencies

- React: JavaScript library for building user interfaces
- Material-UI (MUI): React components for faster and easier web development
- Next.js Router: For handling navigation

## Props

The `Sidebar` component accepts the following props:

- `isOpen`: Boolean to control the open/closed state of the sidebar
- `onToggle`: Function to toggle the sidebar state
- `showProfileIcon`: Boolean to show/hide the profile section
- `showLangSwitcher`: Boolean to show/hide the language picker
- `profileText`: String for the profile display text
- `links`: Array of Link objects for navigation items
- `handleLogOutButton`: Function to handle logout action
- `languages`: Array of Language objects (required if `showLangSwitcher` is true)
- `activeLanguage`: String representing the current language (required if `showLangSwitcher` is true)
- `handleLanguageClick`: Function to handle language selection (required if `showLangSwitcher` is true)
- `style`: Object for custom styling
- `langPickerStyle`: Object for custom styling of the language picker
- `children`: React nodes to render additional content

## Styling

- The component uses Material-UI's styling system
- Custom styles can be passed via the `style` and `langPickerStyle` props

## Customization

This component provides flexibility for customization to suit your application's requirements. Here are some customization options:

### Style Customization

You can customize the appearance of the Sidebar by passing a `style` object:

```tsx
const customStyle = {
  sidebar: {
    /* custom styles for sidebar container */
  },
  drawer: {
    /* custom styles for drawer */
  },
  list: {
    /* custom styles for list */
  },
  listItem: {
    /* custom styles for list items */
  },
  listItemButton: {
    /* custom styles for list item buttons */
  },
  profileText: {
    /* custom styles for profile text */
  },
  icon: {
    /* custom styles for icons */
  },
};

<Sidebar
  // ... other props
  style={customStyle}
/>;
```

### Adding Custom Links

To add or modify navigation links, update the `links` array passed to the component:

```tsx
const links = [
  { label: 'Home', icon: <Home />, route: '/' },
  { label: 'Settings', icon: <Settings />, route: '/settings' },
  { label: 'Profile', icon: <Person />, route: '/profile' }, // New link added
];
```

## Notes

- The component uses Next.js router for navigation.
- The language picker is implemented using a separate `NewLanguagePicker` component.
- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
