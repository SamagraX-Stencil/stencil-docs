---
title: Language Picker
sidebar_label: Language Picker
---

## Usage

```tsx
import LanguagePicker from './packageName';

const App = () => {
  const languages = [
    { name: 'English', value: 'en' },
    { name: 'Spanish', value: 'es' },
    { name: 'French', value: 'fr' },
  ];
  const [activeLanguage, setActiveLanguage] = React.useState('en');

  const handleLanguageClick = (event: SelectChangeEvent<string>) => {
    setActiveLanguage(event.target.value as string);
  };

  return (
    <LanguagePicker languages={languages} activeLanguage={activeLanguage} handleLanguageClick={handleLanguageClick} />
  );
};

export default App;
```

## Description

The `LanguagePicker` component consists of the following elements:

- A FormControl wrapper from Material-UI
- A Select component for displaying the dropdown
- MenuItem components for each language option

## Functionality

- Displays a dropdown menu with language options
- Allows users to select a language
- Triggers a callback function when a language is selected

## Props

The `LanguagePicker` component accepts the following props:

- `languages`: An array of Language objects, each containing `name` and `value` properties
- `activeLanguage`: A string representing the currently selected language
- `handleLanguageClick`: A function to handle language selection events
- `style`: An optional object for custom styling

## Styling

- The component uses Material-UI's styling system
- Custom styles can be passed via the `style` prop

## Customization

This component provides flexibility for customization to suit your application's requirements. Here are some customization options:

### Style Customization

You can customize the appearance of the LanguagePicker by passing a `style` object:

```tsx
const customStyle = {
  formControlStyle: {
    /* custom styles for FormControl */
  },
  selectStyle: {
    /* custom styles for Select */
  },
  menuItemStyle: {
    /* custom styles for MenuItem */
  },
};

<LanguagePicker
  // ... other props
  style={customStyle}
/>;
```

### Adding Custom Languages

To add or modify language options, update the `languages` array passed to the component:

```tsx
const languages = [
  { name: 'English', value: 'en' },
  { name: 'Spanish', value: 'es' },
  { name: 'French', value: 'fr' },
  { name: 'German', value: 'de' }, // New language added
];
```

## Notes

- The component uses the `map` function from Lodash to iterate over the language options.
- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
