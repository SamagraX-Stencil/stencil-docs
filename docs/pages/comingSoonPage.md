---
title: Coming Soon Page
sidebar_label: Coming Soon Page
---

<head>
  <title> Coming Soon Page </title>
  <meta name="description" content="your meta content goes here" />
</head>

The `Coming Soon` molecule is a React component designed to inform visitors about upcoming features, products, or events. It acts as a temporary placeholder until the anticipated content or functionality is ready for launch.

<img src="/img/molecules/comingSoonPage.png" alt="ComingSoon Page Molecule" />

## Usage

```tsx
import ComingSoonPage from './ComingSoonPage';

const App = () => {
  return <ComingSoonPage />;
};

export default App;
```

## Description

The `ComingSoonPage` molecule consists of the following elements:

- Back button to go on previous page.

## Functionality

- This molecule will be displayed until the upcoming functionality is ready for launch.
- Users can go to previous page by using Back button.

## Dependencies

- React: JavaScript library for building user interfaces.
- Material-UI (Mui): React components for faster and easier web development.

## Configuration

- The default theme colors can be configured in the config.json file.
- The component keys can be configured in the config.json file.

## Styling

- CSS modules are used for styling the component.
- Styles are defined in the index.module.css file.

## Customization

This molecule provides flexibility for customization to suit your application's requirements. Here are some customization options:

### Theme Customization

You can customize the theme colors by modifying the values in the `config.json` file. The theme object contains `primaryColor` and `secondaryColor` properties, allowing you to specify the colors according to your brand or design preferences.

```json
"theme": {
  "primaryColor": {
    "value": "#219653",
    "allowOverride": true
  },
  "secondaryColor": {
    "value": "#828282",
    "allowOverride": true
  }
}
```

### Adding Custom Actions

To add custom actions for previous page feature, follow below steps:

- **Previous Page Functionality**: Implement the previous page logic within the `handleBack` function. You can use back() method to go to the previous page.

```tsx
const handleBack = useCallback(() => {
  // window?.history?.back()
  console.log(component.backText ?? 'Back Button');
}, []);
```

### Updating Component

You can update the component keys by modifying the `key` value in the `config.json` file.

```json
"component": {
    "allowOverride": false,
  }
```

## Notes

- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
