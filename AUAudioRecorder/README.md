# AudioRecorder

An audio recorder written in Javascript and HTML. The main audio recorder is in the file 'AUAudioRecorder.js' which contains the AUAudioRecorder object. To see a very simple example of the audio recorder at work, navigate to the 'RecorderTester.html' file in the Example folder.

# Methods
- **startRecording()**: <br>Starts the recording process. The method "requestPermission()" must be called first so that the program has permission to access the computer's microphone.
```javascript
audioRec.startRecording(callback);
```
- **stopRecording()**: <br>Stops recording and saves the recorded audio into a variable with a file type that can be specified by another method.
```javascript
audioRec.stopRecording(callback);
```
- **play()**: <br>Plays the recorded audio in the browser.
```javascript
audioRec.play(callback);
```
- **pause()**: <br>Pauses the audio that is playing. when the play button is clicked again the audio will resume from where it was.
```javascript
audioRec.pause(callback);
```
- **stop()**: <br>Stops the audio from playing and sends it back to the beginning.
```javascript
audioRec.stop(callback);
```
- **loop(bool)**: <br>Sets whether or not the audio should loop once it is played. Set the parameter "bool" to true or false for your desired option.
```javascript
audioRec.loop(true,callback);
```
- **stepBackward()**: <br>Starts the audio from the beginning but does not pause it.
```javascript
audioRec.stepBackward(callback);
```
- **stepForward()**: <br>Sends the audio to the end. Basically just stops it from playing by doing this.
```javascript
audioRec.stepForward(callback);
```
- **clear()**: <br>Deletes the currently recorded audio. This is the only callback that does not return an error message.
```javascript
audioRec.clear(callback);
```
- **isFinished()**: <br>Returns whether or not the audio is finished playing.
```javascript
audioRec.isFinished();
```
- **requestPermission()**: <br>Asks the user for permission to access the computer’s microphone. 
```javascript
audioRec.requestPermission();
```
- **hasPermission()**: <br>Returns true/false if the user has given permission to use the computer's microphone.
```javascript
audioRec.hasPermission();
```
- **getRecording()**: <br>Returns an audio object that contains the recorded audio.
```javascript
audioRec.getRecording();
```
- **getRecordingFile()**: <br>Returns a Blob object that contains the recorded audio. This can be used for operations where a file is needed.
```javascript
audioRec.getRecordingFile();
```
- **setOutputFileType(fileType)**: <br>Sets the type of file that the audio will be formatted to. The "fileType" parameter is the file extension that you would like to use (i.e. mp3, wav, ogg). The default file type is mp3.
```javascript
audioRec.setOutputFileType("mp3");
```
- **getStream()**: <br>Returns the stream used by the Web Audio API that handles the recording. This method would be useful if one would like to do other things with the Web Audio API such as drawing it on a canvas or adding sound effects.
```javascript
audioRec.getStream();
```


# How To
- Step 1: Add the AUAudioRecorder to your web application. This can be done by using the script tag like so:
```html
<script type="text/javascript" src="https://adeolauthman.squarespace.com/s/AUAudioRecorder.js"></script>
```
or by installing it with npm, as shown here:
```javascript
$npm install au-audio-recorder
```
then, in your JavaScript file typing:
```javascript
var audioRec = require('au-audio-recorder');
// Or
import audioRec from 'au-audio-recorder';
```
- Step 2: Assuming you have already created buttons in your HTML file and already have your own Javascript file for your webpage, you can create a new AUAudioRecorder object and call methods from it when buttons are clicked.
```javascript
var audioRec = new AUAudioRecorder();

audioRec.hasPermission( (err) => { console.log(err); } );
audioRec.requestPermission();
audioRec.startRecording( (err) => { console.log(err); } );
audioRec.stopRecording( (err) => { console.log(err); } );
audioRec.loop(true, (err) => { console.log(err); } );
audioRec.play( (err) => { console.log(err); } );
audioRec.pause( (err) => { console.log(err); } );
audioRec.stop( (err) => { console.log(err); } );
audioRec.stepBackward( (err) => { console.log(err); } );
audioRec.stepForward( (err) => { console.log(err); } );
audioRec.clear( () => { /* callback */ } );
audioRec.isFinished();
audioRec.getRecording();
audioRec.getRecordingFile();
audioRec.setOutputFileType("mp3");
audioRec.getStream();

```

# Author
- Year: 2016
- Languages: HTML, Javascript
- Programmer: Adeola Uthman
