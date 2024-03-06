---
title: Login Mobile Aadhar Page
sidebar_label: Login Mobile Aadhar Page
---



<head>
  <title> Login Mobile Aadhar Page </title>
  <meta
    name="description"
    content="your meta content goes here"
  />
</head>

The `LoginMobileAadharPage` molecule is a React component designed for user authentication using either mobile phone numbers or Aadhar numbers. It provides a user-friendly interface for users to input their credentials and login.

<img src="/img/molecules/loginMobileAadharPage.png" alt="Login Mobile Aadhar Page Molecule" />

## Usage
```
import LoginMobileAadharPage from './LoginMobileAadharPage';

const App = () => {
  return (
    <LoginMobileAadharPage />
  );
}

export default App;
```

## Description
The `LoginMobileAadharPage` molecule consists of the following elements:

- Input field for either mobile phone number or Aadhar number.
- Toggle button to switch between mobile phone number and Aadhar number inputs.
- Login button to initiate the login process.
- Registration link for users who do not have an account yet.

## State
- `isAadharClicked`: Boolean state to track whether the user has selected Aadhar number input.
- `input`: String state to store the input value (mobile phone number or Aadhar number).
- `valid`: Boolean state to track the validity of the input.
- `errorMessage`: String state to store error messages related to invalid input.
- `loading`: Boolean state to track the loading state of the login process.

## Functionality
- Users can input either their mobile phone number or Aadhar number.
- The input field validates the input based on the selected input type and displays appropriate error messages.
- Users can toggle between mobile phone number and Aadhar number inputs.
- Upon clicking the login button, the component checks if the input is valid and initiates the login process.
- If the input is valid, a success message is displayed, and if not, an error message is displayed.

## Dependencies
- React: JavaScript library for building user interfaces.
- Material-UI (Mui): React components for faster and easier web development.
- React Hot Toast: Toast notification library for React applications.

## Configuration
- The default theme colors can be configured in the config.json file.
- The component title can be configured in the config.json file.

## Styling
- CSS modules are used for styling the component.
- Styles are defined in the index.module.css file.

## Notes
- This molecule does not handle actual authentication. It simulates the login process by displaying a success message upon clicking the login button.
- The registration functionality is not implemented in this molecule.





