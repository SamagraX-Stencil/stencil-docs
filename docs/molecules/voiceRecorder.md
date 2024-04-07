---
title: Voice Recorder
sidebar_label: Voice Recorder
---


<head>
  <title> Voice Recorder </title>
  <meta
    name="description"
    content="A customizable React component for recording audio. Users can start and stop recording, with visual feedback during the recording process."
  />
</head>

The `VoiceRecorder` molecule is a React component designed to facilitate voice recording functionality within your application. It allows users to record audio, which can then be used for various purposes such as voice input, messaging, or any other application that requires audio capture.

<img src="/img/molecules/voiceRecorder.png" alt="OTP Page Molecule" />

## Usage
```
import VoiceRecorder from './VoiceRecorder';

const App = () => {
  return (
    <VoiceRecorder setInputMsg={setInputMsg} tapToSpeak={true} />
  );
}

export default App;
```

## Description
The VoiceRecorder molecule comprises several elements:

- Input field for entering the OTP.
- Button to submit the OTP for verification.
- Visual indication of loading state during OTP verification.

## Props
- `setInputMsg`: Function to set the input message received from the user.
- `tapToSpeak`: Boolean flag to indicate whether tap-to-speak functionality should be enabled.
- `includeDiv`: Optional boolean flag to include a containing div element around the recorder control.

## State
- `mediaRecorder`: State to manage the MediaRecorder instance for audio recording
- `isErrorClicked`: State to track whether an error icon has been clicked.
- `recorderStatus`: State to manage the status of the voice recorder (e.g., idle, processing, error).

## Functionality
- Users can initiate voice recording by clicking on the recorder control.
- The component utilizes the MediaRecorder API to capture audio from the user's device.
- Recorded audio is analyzed for sound detection and duration.
- Upon completion of recording, the audio data is sent to a server for processing.
- Various states and visual indicators are provided to enhance user experience during recording and processing.

## Dependencies
- React: JavaScript library for building user interfaces.
- React Hot Toast: Toast notification library for React applications.

## Styling
- CSS modules are used for styling the component.
- Styles are defined in the index.module.css file.

### Adding Custom Actions
To add custom actions , you can extend the `makeComputeAPICall` function to define custom actions upon successful recording

```
  const makeComputeAPICall = async (blob: Blob) => {
    try {
      setRecorderStatus('processing')
      toast.success(`${config.component.waitMessage}`)
      // Define the API endpoint and make api call here 
      if(blob){
        //set api result in setInputMsg 
        setInputMsg('')
      }

    } catch (error) {
      console.error(error)
      setRecorderStatus('error')
      toast.error(`${config.component.recorderErrorMessage}`)
      // Set isErrorClicked to true when an error occurs
      setIsErrorClicked(false)
      setTimeout(() => {
        // Check if the user has not clicked the error icon again
        if (!isErrorClicked) {
          setRecorderStatus('idle')
        }
      }, 2500)
    
    }
  }
```

### Updating Component Details

You can update various aspects of the Voice Recorder component by modifying the configuration values in the `config.json` file.

#### Audio Analysis Parameters

You can adjust the following parameters used for audio analysis and recording:

- **Voice Min Decibels**: Minimum decibel level considered as valid voice input.
  - Default Value: -35

- **Delay Between Dialogs**: Time interval (in milliseconds) between detecting separate dialogs.
  - Default Value: 2500

- **Dialog Max Length**: Maximum duration (in milliseconds) for a single dialog.
  - Default Value: 60000 (1 minute)

- **Recording Status**: Initial state of the recording (true for recording, false for idle).
  - Default Value: false

#### Error and Processing Messages

You can customize the error and processing messages displayed during different states of the recorder:

- **Recorder Error Message**: Message displayed when the recorded audio is not recognized or an error occurs.
  - **Default Message**: "Your question was not recognized. Please try speaking more clearly."

- **Wait Message**: Message displayed while the recorder is processing the recorded audio.
  - **Default Message**: "Please wait while we process your request..."

These configuration values allow you to tailor the Voice Recorder component to suit your application's requirements, audio analysis parameters, and user feedback messages.


### Additional Customization
For further customization, you can modify the component's styling by editing the CSS rules defined in the `index.module.css` file. Adjust styles such as font size, padding, margins, and colors to match your application's design guidelines.


## Notes
- The molecule simulates the voice recording process for demonstration purposes and does not handle actual audio processing.
- Further customization can be done by modifying the JSX structure, styles, and functionality according to your application's requirements





