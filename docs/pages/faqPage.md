---
title: Faq Page
sidebar_label: Faq Page
---

<head>
  <title> Faq Page </title>
  <meta name="description" content="your meta content goes here" />
</head>

The `FAQ` molecule is a React component serves as a centralized repository of answers to common queries that users may have about a product, service, or topic. It's designed to address recurring concerns, provide clarification, and offer solutions to common issues, thereby enhancing user experience and reducing support inquiries.

<img src="/img/molecules/faqPage.png" alt="Faq Page Molecule" />

## Usage

```tsx
import FAQPage from './FAQPage';

const App = () => {
  return <FAQPage />;
};

export default App;
```

## Description

The `FAQPage` molecule consists of the following elements:

- User Manual button is used to download document designed to assist users in effectively using the product.
- Contact Us button to contact support during any query.

## Functionality

- This molecule will be used to solve product related queries and doubts.
- By clicking Contact Us button, user can contact the support team.

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
     },
  "secondaryColor": {
    "value": "#828282",
     }
}
```

### Adding Custom Actions

To add custom actions for contact us or download user manual, follow below steps:

- **Contact Functionality**: Implement the contact support logic within the `handleContactClick` function. You can use call or email options to connect with the required team.

```tsx
const handleContactClick = useCallback(() => {
  console.log(component.contactText ?? 'Contact User'); //Implement your contact user logic here
}, []);
```

- **User Manual Functionality**: Implement the download manual logic within the `downloadPDFHandler` function.

```tsx
const downloadPDFHandler = useCallback(() => {
  console.log(component.userManualText ?? 'User Manual'); //Implement your download logic here
}, []);
```

### Updating Component

You can update the component keys by modifying the `key` value in the `config.json` file.

```tsx
"component": {
     "showFaqPage": true,
      "faqManualPdfLink": "/src/pages/faq-page/assets/manual.pdf",
      "faqShowPdfButton": true
  }
```

## Notes

- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
