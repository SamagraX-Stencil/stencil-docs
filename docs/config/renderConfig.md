---
title: Rendering Inputs
sidebar_label: Rendering Inputs
---

<head>
  <title> Rendering Inputs</title>
  <meta name="description" content="your meta content goes here" />
</head>


## Rendering Logic

The component iterates over the keys of the initial values object, and for each key, it determines the appropriate input type to render based on the configuration specified in `renderProps.type`. The `renderFormElement` function supports rendering different types of inputs by switching on the type specified in the configuration.

```shell
{Object.keys(config).map(key => {
        const { renderProps, value } = initialValues[key];
        return (
          <React.Fragment key={key}>
            {renderFormElement(key, renderProps, value)}
          </React.Fragment>
        );
      })}
```

### renderFormElement

The renderFormElement function plays a crucial role in dynamically rendering form elements based on the configuration specified in a JSON file. This function is designed to interpret and convert configuration data into actual React components that form the UI elements of a form, allowing for a flexible and configurable form setup. Below is a detailed examination of its implementation and usage.

```ts
const renderFormElement = (key: string, renderProps: any, value: string) => {
  switch (renderProps.type) {
    case 'colorpicker':
      return <ColorPickerInput label={key} value={value} />;
    case 'select':
      return (
        <SelectInput
          source={key}
          required
          label={key}
          choices={renderProps.options.map((option: any) => ({
            id: option.value,
            name: option.label,
          }))}
        />
      );
    case 'fileUpload':
      return (
        <FileInput
          source={key + 'fileUpload'}
          label={key}
          accept={renderProps.fileType}
          sx={{ border: '1px dashed grey', padding: '15px' }}
        >
          <FileFieldWithIcon source="src" title="title" isPdf target="_blank" />
        </FileInput>
      );
    default:
      return <TextInput source={key} label={key} />;
  }
};
```

## Supported Input Types

- **Color Picker:** Custom input for selecting colors.
- **Select Input:** Dropdown input for selecting from predefined options.
- **File Upload:** Input for uploading files with specific file type restrictions.
- **Text Input:** Default input for text entry.

### ColorPickerInput

- **Props:** Receives `label` and `value`.
- **Functionality:** Allows users to pick a color. It maintains its own state for the selected color and updates it on change.

```shell
# Sample
<ColorPickerInput label={key} value={value} />
```

### Select

- **Props:** Receives key as `label` and options as `choices` ,where option should have a value and label property.

```js
# Sample
<SelectInput source={key} required label={key}
          choices={renderProps.options.map((option: any) => ({
          id: option.value,
          name: option.label
       }))}
/>
```

### FileInput

A file input which will return the url or the uploaded file,generally used for images like bot icon.

- **Props:** Receives key as `label` and fileType as `accept` ,

```js
# Sample
<FileInput source={key+"fileUpload"} label={key}
     accept={renderProps.fileType}
     sx={{ border: '1px dashed grey', padding: '15px' }}>
    <FileFieldWithIcon source="src" title="title" isPdf target="_blank"/>
</FileInput>
```

### Text Input

A textinput to capture string related values.For eg- botname.

- **Props:** Receives key as `label` ,

```js
# Sample
<TextInput source={key} label={key} />
```

