# I Didn't Know the Browser Could Do That!
## Speech API
* `window.speechSynthesis`
* `SpeechSynthesisUtterance(...)`
* `synth.speak(utterance)`
* `synth.getVoices(...)`

## Speech Recognition API
* `SpeechRecognition` instance
  * `interimResults` keeps updating
* callbacks
* Chrome only

## Geolocation API
* `navigator.geolocation.getCurrentPosition(...)`

## Notifications API
* Native notifications where possible
* `Notification.requestPermission(cb)`
* `not = new Notification(...)`
* `not.onclick` handler

## Push Notification API
* Uses a service worker
* add listener for `'push'` and do stuff

## Battery Manager API
* Detects charge amount, charging
* callbacks

## Media Recorder API
* `getUserMedia({ video: boolean, audio: boolean }): Stream`
* `new MediaRecorder(stream)`
  * `ondataavailable`, `onend`, `.start()`

## Web Audio API
* Create sounds by pitch, tone, etc.
* `new AudioContext()`
* `ctx.createOscillator()`
* `osc.connect(ctx.destination)`

## Vibration API
* `navigator.vibrate(ms|ms[])`

## Device Orientation API
* `window` event `deviceorientation`

## Others
* Payment API
* Bluetooth API
* Web USB API
