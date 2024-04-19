---
title: History Page
sidebar_label: History Page
---

<head>
  <title> History Page </title>
  <meta name="description" content="your meta content goes here" />
</head>

The ``HistoryPage`` component is a React page that displays a list of historical chat interactions. It allows users to view past conversations and delete them if needed.

<img src= "/img/molecules/historypage.png" alt="History Page Molecule" />

## Usage

```tsx
import HistoryPage from './historyPage';

const App = () => {
  return (
    <HistoryPage />
  );
}

export default App;
```

## Description

The `HistoryPage` molecule consists of the following elements:

- It provides a list of past chat interactions for users to review.
- Users can delete individual conversations from the history.

## Functionality

 - Users can click on a chat item to view details of the conversation.
- They can delete conversations by clicking the delete icon and confirming the action.

## Dependencies

- React: JavaScript library for building user interfaces.
- Material-UI (Mui): React components for faster and easier web development.
- Lodash: JavaScript utility library for common programming tasks.

 

## Styling

- CSS modules are utilized for styling the component.
- Styles are defined in the `style.module.css` file.

## Customization

 The **HistoryPage** component offers flexibility for customization to match your application's requirements. Here are some customization options:

### Theme Customization

Modify the colors and styles in the `style.module.css` file to match your application's design.


### Component Configuration 

 Update the component object in the config.json file to customize the title and other configurations

 ```json
{
  "component": {
    "allowOverride": false,
    "title": "History",
    "noItemsText": "No  Conversation History",
    "allowDelete": true, 
    "showTimestamp":true
    
   
    }
  }
 

 ```

 
 ### Functionality Customization

 The `HistoryPage` component offers various options for customizing its functionality to better suit your application's requirements. Here are some key areas where you can customize functionality:

**1. Handle Click Function**

The `handleClick` function is responsible for defining the behavior when a user clicks on a chat item in the history list.  You can customize this function to implement any desired action.

```tsx
const handleClick = useCallback((activeItem: HistoryItem) => {
    
    // Implement custom functionality here
}, []);

```

**2. Secondary Action Click**

The `onSecondaryActionClick` function is invoked when a user interacts with the secondary action associated with a chat item, such as deleting the conversation. It typically displays a confirmation prompt before performing the action. You can customize this function to handle secondary actions differently or add additional functionality.


```tsx
const onSecondaryActionClick = useCallback(
    (activeItem: ChatItem) => () => {
        if (window.confirm("Are you sure you want to delete this conversation?")) {
            // Perform deletion logic
            setList(prev => {
                return prev.filter((item: ChatItem) => item.conversationId !== activeItem.conversationId)
            })
        }
    },
    []
);

```
 

## Notes

- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
