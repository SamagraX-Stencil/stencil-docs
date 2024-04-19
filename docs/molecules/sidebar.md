---
title: Sidebar
sidebar_label: Sidebar
---


<head>
  <title> Sidebar </title>
  <meta
   
    content=" Sidebar Component"
  />
</head>

The Navbar molecule is a React component designed for  all purpose Navigation. It allows users to  navigate across the webpage through it's multipurpose navigation options.

<img src="/img/molecules/sidebar.png" alt=" Sidebar Molecule" />



## Usage
```
import Sidebar from './sidebar';

const App = () => {
  return (
    <Sidebar />
  );
}

export default App;
```

 

## Description

- *Dynamic Configuration*: The sidebar's content and behavior are driven by a configuration object loaded asynchronously from a JSON file.
- *Language Switcher*: If enabled in the configuration, the sidebar displays a language switcher allowing users to switch between different languages. Each language option is represented by a button with a label.
- *Profile Icon and Text*: Optionally, the sidebar can display a profile icon along with custom text, providing users with personalized information.
- *Menu Links*: The main navigation links are listed within the sidebar. Each link consists of an icon, label, and an optional chevron icon indicating a sub-menu.
- *Logout Button*: If specified in the configuration, a logout button is displayed at the bottom of the sidebar for user session management.


 
 

## Functionality

- The component is structured using Material-UI components such as Drawer, List, and ListItem etc for styling and functionality.

- Configuration for the component is provided via a JSON file imported as config.

- State management is handled using React's useState hook, toggling the visibility of the active language.

- The appearance and behavior of the component can be customized by modifying the values in the config file.



 

## Dependencies
- React: JavaScript library for building user interfaces.
- Material-UI (Mui): React components for faster and easier web development.
- ThemePicker Component: T A custom component for selecting different themes for the application.  
 

## Configuration
-  All the configuration can be done from the config.json file for the navbar component. Here are some of the common configuration types:-

 ###   Language :
The Language can be changed from the config.json file with the available language code and also the label can be changed from the same

```json

"languages": [
        {
          "code": "en",
          "label": "ENG"
        },
        {
          "code": "or",
          "label": "ଓଡ଼ିଆ"
        }
      ],
```


 ###   Links(Routing) :
The Routing of the other pages can be configured from the links array which store the label name, icons and route all can be configured from there.

```json

 "links": [
        {
          "label": "FAQ Page",
          "icon": "HelpIcon",
          "route": ""
        },
        {
          "label": "Chat Page",
          "icon": "HistoryIcon",
          "route": ""
        },
        {
          "label": "Feedback",
          "icon": "FeedbackIcon",
          "route": ""
        }
      ],
```
 
 
 
 

 


## Notes
 - This molecule is not properly routed for the project. Route it according to your project and customize the icons to your brand theme and work on it. 
 - The internal routing also needs to be done for easy navigation.