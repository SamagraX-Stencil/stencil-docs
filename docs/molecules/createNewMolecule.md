---
title: How to Create a Molecule
sidebar_label: Create New Molecule
---

<head>
  <title> Create New Molecule </title>
  <meta name="description" content="your meta content goes here" />
</head>

Start by designing a molecule in the [molecule repository](https://github.com/SamagraX-Stencil/ui-templates/tree/dev/src/molecules). When doing so, create a new folder under `/src/molecules`. Consider the different configurations and customizations that could be applied to make the molecule versatile and visually appealing.
The process of creating a molecule involves several steps.

## Folder Structure

Ensure that the below files/folders are present in the newly created molecule folder:

### assets

The asset folder within the molecule serves as a centralized location for storing static files and resources that are essential for your molecule. These assets typically include images, fonts, and other static files.

### config.json

This file allows you to customize various aspects of your molecule without directly modifying the source code, making it easier to manage and maintain. The config.json file follows a structured format, typically in JSON (JavaScript Object Notation), where each configuration setting is defined as a key-value pair. Below is an example of the structure:

```json
{
  "component": {
    "title": "Coming Soon!",
    "description": "We are going to launch this feature very soon. Stay tuned!",
    "backText": "Back"
  }
}
```

### index.tsx

The index.tsx file is used as the entry point for a specific molecule within the application. This file serves as the main file that other parts of the molecule can import to use the functionality provided by the component.

```tsx
import React, { useCallback } from 'react';
import styles from './index.module.css';
import Box from '@mui/material/Box';
import Button from '@mui/material/Button';
import Typography from '@mui/material/Typography';
import { component } from './config.json';
import Hourglass from './hourglass';
import { useColorPalates } from '../../molecules/theme-provider/hooks';

const Component: React.FC = () => {
  const theme = useColorPalates();
  const handleBack = useCallback(() => {
    // window?.history?.back()
    console.log(component.backText ?? 'Back Button');
  }, []);

  return (
    <>
      <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0"></meta>
      <Box className={styles.container}>
        <Box>
          <Typography variant="h4" sx={{ color: theme?.primary?.main, fontWeight: '700' }}>
            {component.title ?? 'Coming Soon'}
          </Typography>
        </Box>
        <Box>
          <Hourglass fillColor={theme?.primary?.main} />
        </Box>
        <Box>
          <Typography variant="body1" sx={{ fontWeight: '600', textAlign: 'center' }}>
            {component.description ?? 'Coming Soon Description'}
          </Typography>
        </Box>
        <Box>
          <Button
            variant="contained"
            className={styles.backButton}
            size="large"
            style={{ backgroundColor: theme?.primary?.main }}
            onClick={handleBack}
          >
            {component.backText ?? 'Back Button'}
          </Button>
        </Box>
      </Box>
    </>
  );
};

export default Component;
```

### index.module.css

The index.module.css file is a CSS Module file commonly used to provide scoped styling for component. CSS Modules offer a way to encapsulate styles by generating unique class names for each component, preventing style conflicts and promoting modularity within your molecule.

```css
.container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  row-gap: 16px;
  font-family: sans-serif !important;
}
```

### index.stories.tsx

The index.stories.tsx file is a `TypeScript` file commonly used in conjunction with Storybook to create and document visual components. Storybook is an open-source tool for developing UI components in isolation, making it easier to build and document user interface elements.

### index.test.tsx

The index.test.tsx file is a TypeScript file used to define and execute unit tests that verify the behavior and functionality of the molecule. These tests ensure that component renders correctly, handle user interactions appropriately, and maintain expected behavior across different scenarios.
Below is an example of how index.test.tsx can be used to write unit tests:

```tsx
import React from 'react';
import { render } from '@testing-library/react';
import Component from './index';

test('renders component with default props', () => {
  // Arrange
  const { getByTestId } = render(<Component />);

  // Act
  const componentElement = getByTestId('component');

  // Assert
  expect(componentElement).toBeInTheDocument();
});
```

## Importing a Molecule

Importing molecules is a straightforward process that involves identifying the component, importing it into the appropriate file, and using it within your TSX code. By following the guidelines, you can effectively integrate components into your React application.

After designing the molecule, add the molecule in the `index.json` file inside the [molecules](https://github.com/SamagraX-Stencil/ui-templates/tree/dev/src/molecules/index.json) folder. How the molecule is designed, accordingly it should be added in the object:

- If the molecule is a separate page then it should be added in `pages`
- If the molecule is a sub-component then it should be added in `molecules`

```json
{
  "pages": [
    "otp-page",
    "downtime-page",
    "feedback-page",
    "history-page",
    "faq-page",
    "chat-ui",
    "login-mobile-aadhar-page",
    "coming-soon-page",
    "home-page",
    "launch-page"
  ],
  "molecules": ["otp-input", "chat-ui", "share-buttons", "voice-recorder", "json-to-table"]
}
```

### How and Where to Import a Molecule

- All the `page` molecules are imported within the `App.tsx` file. This allows you to associate the imported component with a particular route path.

```tsx
import { Navbar } from './components/navbar';
import { Route, Routes } from 'react-router-dom';
import LoginPage from './molecules/login-mobile-aadhar-page';
import { Toaster } from 'react-hot-toast';
import Components from './components';
import OtpPage from './molecules/otp-page';
import HistoryPage from './molecules/history-page';
import ComingSoonPage from './molecules/coming-soon-page';
import DowntimePage from './molecules/downtime-page';
import FAQPage from './molecules/faq-page';
import LaunchPage from './molecules/launch-page';
import HomePage from './molecules/home-page';
import FeedbackPage from './molecules/feedback';
import ShareButtons from './molecules/share-buttons';
import { ChatUI } from './molecules/chat-ui';

function App() {
  return (
    <>
      <Toaster />
      <Navbar />
      <>
        <Routes>
          <Route index element={<LoginPage />} />
          <Route path="/login-mobile-aadhar-page" element={<LoginPage />} />
          <Route path="/otp-page" element={<OtpPage />} />
          <Route path="/history-page" element={<HistoryPage />} />
          <Route path="/coming-soon-page" element={<ComingSoonPage />} />
          <Route path="/downtime-page" element={<DowntimePage />} />
          <Route path="/faq-page" element={<FAQPage />} />
          <Route path="/home-page" element={<HomePage />} />
          <Route path="/coming-soon-page" element={<ComingSoonPage />} />
          <Route path="/downtime-page" element={<DowntimePage />} />
          <Route path="/faq-page" element={<FAQPage />} />
          <Route path="/feedback-page" element={<FeedbackPage />} />
          <Route path="/launch-page" element={<LaunchPage />} />
          <Route path="/share-buttons" element={<ShareButtons />} />
          <Route path="/chat-ui" element={<ChatUI />} />
          <Route path="/molecules" element={<Components />} />
        </Routes>
      </>
    </>
  );
}
export default App;
```

- All the `component` molecules are imported in the `index.tsx` file within the [components](https://github.com/SamagraX-Stencil/ui-templates/tree/dev/src/components) folder. This allows you to associate the components with a `/molecules` route path.
