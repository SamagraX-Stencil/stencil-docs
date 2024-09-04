---
title: Feedback
sidebar_label: Feedback
---

<head>
  <title> Feedback page </title>
  <meta name="description" content="your meta content goes here" />
</head>

The `Feedback` component is a React component that provides a customizable interface for collecting user feedback. It includes options for both star ratings and text reviews.

<!-- <img src="/img/pages/feedbackReviewAndRatingPage.png" alt="Feedback Page" /> -->

## Usage

```tsx
import Feedback from './Feedback';

const App = () => {
  const [rating, setRating] = useState<number | null>(0);
  const [review, setReview] = useState('');

  const handleFeedbackSubmission = async () => {
    // Handle feedback submission logic
  };

  return (
    <Feedback
      showRatingBox={true}
      showReviewBox={true}
      star={rating}
      review={review}
      onChangeRating={setRating}
      onChangeReview={setReview}
      handleFeedback={handleFeedbackSubmission}
    />
  );
};

export default App;
```

## Description

The `Feedback` component consists of:

- A title section
- An optional star rating section
- An optional text review section
- Submit buttons for each section

## Functionality

- Displays rating and/or review inputs based on props
- Allows users to provide star ratings (1-5 stars)
- Enables users to write text reviews
- Triggers a callback function when feedback is submitted
- Shows success or error toast notifications on submission

## Dependencies

- React: JavaScript library for building user interfaces
- Material-UI (MUI): React components for faster and easier web development
- react-hot-toast: Library for toast notifications

## Props

The `Feedback` component accepts the following props:

- `showReviewBox`: Boolean to show/hide the review text box (default: false)
- `showRatingBox`: Boolean to show/hide the star rating box (default: false)
- `star`: Number or null representing the current rating value
- `review`: String containing the current review text
- `onChangeReview`: Function called when the review text changes
- `onChangeRating`: Function called when the rating changes
- `handleFeedback`: Function called when feedback is submitted
- `customStyles`: Object for custom styling of various elements

## Styling

- The component uses Material-UI components and styling system
- Custom styles can be passed via the `customStyles` prop for fine-grained control

## Customization

This component provides several options for customization:

### Style Customization

You can customize the appearance of different parts of the component:

```tsx
<Feedback
  // ... other props
  customStyles={{
    heading: { color: '#ff0000' },
    rating: { fontSize: '4vh' },
    review: { border: '1px solid #000000' },
    submitButton: { backgroundColor: '#00ff00' },
  }}
/>
```

### Feature Toggle

Control which feedback features are displayed:

```tsx
<Feedback
  showRatingBox={true}
  showReviewBox={false}
  // ... other props
/>
```

## Notes

- The component is designed to be centered within its parent container.
- It uses Material-UI components for consistent styling and responsiveness.
- The submission process includes error handling and toast notifications.
- The component is set up for potential loading state management (commented out in the current version).
- For accessibility, the component includes data-testid attributes on key elements.
- The primary color used is '#1976d2', which can be customized through the `customStyles` prop.
- For further customization, you can modify the JSX structure, styles, and functionality according to your application's needs.
