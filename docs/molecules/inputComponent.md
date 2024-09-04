---
title: Input Component
sidebar_label: Input Component
---

<head>
  <title>InputComponent</title>
  <meta name="description" content="A flexible component for handling various login input types and OTP verification" />
</head>

The `InputComponent` is a React component that provides a flexible interface for various login input types, including mobile numbers, passwords, emails, Aadhaar numbers, usernames, and OTP verification. It combines input fields, buttons, and OTP functionality into a single, customizable component.

## Usage

```tsx
import InputComponent from './InputComponent';

const LoginForm = () => {
  const [mobileNumber, setMobileNumber] = useState('');

  const handleNextTask = async () => {
    // Handle next task logic
  };

  return (
    <InputComponent
      title="Login"
      type="mobile"
      buttonProps={{
        handleNextTask: handleNextTask,
        buttonText: 'Next',
      }}
      inputProps={{
        value: mobileNumber,
        onChange: setMobileNumber,
        placeholder: 'Enter mobile number',
        errorMessage: 'Invalid mobile number',
      }}
    />
  );
};
```

## Description

The `InputComponent` is a versatile component that can handle different types of login inputs:

- Standard inputs (mobile, password, email, Aadhaar, username)
- Username and password combination
- OTP verification

It includes:

- A title section
- Input fields based on the specified type
- A submit button
- OTP functionality when the type is 'otp'

## Props

The `InputComponent` accepts the following props:

- `title`: string (optional) - The title of the component
- `type`: InputType ('mobile' | 'password' | 'email' | 'aadhaar' | 'otp' | 'username')
- `mainContainerStyle`: React.CSSProperties (optional) - Custom styles for the main container
- `titleStyle`: React.CSSProperties (optional) - Custom styles for the title
- `buttonProps`: ButtonProps - Properties for the submit button
- `inputProps`: InputProps (optional) - Properties for the input field
- `otpProps`: OtpProps (optional) - Properties for OTP functionality
- `passwordProp`: PasswordProps (optional) - Properties for password input and forgot password functionality

## Functionality

- Renders different input fields based on the `type` prop
- Handles username and password combination when `type` is 'username'
- Provides OTP verification interface when `type` is 'otp'
- Manages input validation and error display
- Triggers next task function on button click

## Customization

You can customize various aspects of the component:

```tsx
<InputComponent
  title="Custom Login"
  type="email"
  mainContainerStyle={{ backgroundColor: '#f0f0f0' }}
  titleStyle={{ color: '#333', fontSize: '24px' }}
  buttonProps={{
    handleNextTask: handleNextTask,
    buttonText: 'Submit',
    buttonStyle: { backgroundColor: '#007bff' },
  }}
  inputProps={{
    value: email,
    onChange: setEmail,
    placeholder: 'Enter email',
    inputStyle: { borderRadius: '8px' },
  }}
/>
```

## Subcomponents

### LoginInput

The component uses `LoginInput` for rendering standard input fields.

### OtpComponent

When `type` is 'otp', it renders the `OtpComponent` for OTP verification.

## Notes

- The component uses Material-UI components for consistent styling and responsiveness.
- It supports various input types and adapts its interface accordingly.
- The button is disabled based on input validity and type.
- For OTP functionality, additional props like countdown timer and resend OTP are supported.
- The component is designed to be flexible and can be easily integrated into larger login flows.
- Consider adding appropriate ARIA attributes for better accessibility if needed.
- The styling is primarily handled through Material-UI components and custom style props.
