---
title: Add New Input
sidebar_label: Add New Input
---

<head>
  <title> Adding a New Element to the Dynamic Form System</title>
  <meta name="description" content="your meta content goes here" />
</head>

To add a new element type to the `renderFormElement` function within a dynamic form system that uses a hierarchical configuration syntax, follow these steps. This guide will illustrate adding a hypothetical `DatePickerInput` element.

## Step 1: Define the New Input Component

If the new element type (`DatePickerInput`) does not exist, create this component first. This component allows users to select dates.

```jsx
// DatePickerInput.js

import * as React from 'react';

const DatePickerInput = ({ source, label, defaultValue }) => {
  const [value, setValue] = React.useState(defaultValue);

  const handleChange = (event) => {
    setValue(event.target.value);
  };

  return (
    <div>
      <label htmlFor={source}>{label}</label>
      <input type="date" id={source} name={source} value={value} onChange={handleChange} />
    </div>
  );
};
```

## Step 2: Extend the renderFormElement Function

Modify the renderFormElement to accommodate the new input type. Add a case for handling the DatePickerInput in the function's logic.

```jsx
const renderSimpleElement = (config) => {
  switch (config.componentType) {
    // Existing cases...

    case 'datePicker':
      return <DatePickerInput source={config.key} label={config.key} defaultValue={config.defaultValue} />;

    // Other cases remain as is
  }
};
```

## Step 3: Update the Configuration

Adjust your configuration JSON to include the new DatePickerInput component by setting componentType to "datePicker".

```json
{
  "componentName": "Created Date",
  "componentType": "datePicker",
  "defaultValue": "28/02/2024",
  "isAvailable": true,
  "showInAdmin": true,
  "props": {
    "keyName": "createdAt"
  }
}
```
