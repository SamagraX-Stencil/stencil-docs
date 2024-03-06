---
title: OTP Page
sidebar_label: OTP Page
---


<head>
  <title> OTP Page </title>
  <meta
    name="description"
    content="your meta content goes here"
  />
</head>

The `OtpPage` molecule is a React component designed for OTP (One-Time Password) verification. It allows users to enter the OTP sent to their mobile number for authentication purposes.

<img src="/img/molecules/otpPage.png" alt="OTP Page Molecule" />

## Usage
```
import OtpPage from './OtpPage';

const App = () => {
  return (
    <OtpPage />
  );
}

export default App;
```

## Description
The `OtpPage` molecule consists of the following elements:

- Input field for entering the OTP.
- Button to submit the OTP for verification.
- Visual indication of loading state during OTP verification.

## State
- `otp`: String state to store the OTP entered by the user.
- `loading`: Boolean state to track the loading state of the OTP verification process.

## Functionality
- Users can input the OTP sent to their mobile number.
- Upon clicking the login button, the component checks if the OTP is of the correct length (4 digits).
- If the OTP is correct, a success message is displayed, and if not, an error message is displayed.

## Dependencies
- React: JavaScript library for building user interfaces.
- Material-UI (Mui): React components for faster and easier web development.
- React Hot Toast: Toast notification library for React applications.
- OTPInput: Atom for OTP input.

## Configuration
- The default theme colors can be configured in the config.json file.
- The component title can be configured in the config.json file.

## Styling
- CSS modules are used for styling the component.
- Styles are defined in the index.module.css file.

## Notes
- This molecule does not handle actual OTP verification. It simulates the verification process by displaying a success message upon entering the correct OTP.
- The OTP length is hardcoded to 4 digits.





