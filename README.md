<!DOCTYPE html>

<html lang="pl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Radio Telescope v0.7.2</title>

<style>
*{box-sizing:border-box}

body{
    margin:0;
    min-height:100vh;
    background:radial-gradient(circle at top,#142033,#05070b 70%);
    color:white;
    font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
    text-align:center;
}

.app{
    width:100%;
    max-width:560px;
    margin:auto;
    padding:30px 20px 60px;
}

h1{
    margin:0;
    font-size:29px;
    letter-spacing:1px;
}

.subtitle{
    margin-top:8px;
    color:#8290a5;
    font-size:11px;
    letter-spacing:2px;
}

.receiver-panel{
    margin-top:30px;
    padding:25px;
    background:linear-gradient(145deg,#101827,#080b11);
    border:1px solid #273348;
    border-radius:25px;
    box-shadow:0 15px 45px #00000099;
}

.status{
    display:flex;
    justify-content:center;
    align-items:center;
    gap:10px;
    color:#7f8da2;
    font-weight:bold;
    letter-spacing:1px;
}

.status-dot{
    width:10px;
    height:10px;
    border-radius:50%;
    background:#596477;
}

.active{
    color:#42e6a4;
}

.active .status-dot{
    background:#42e6a4;
    box-shadow:0 0 15px #42e6a4;
}

.scan-status{
    margin-top:18px;
    min-height:24px;
    color:#8ea1bb;
    font-size:13px;
    letter-spacing:1px;
}

.scan-animation{
    margin:18px auto;
    width:100%;
    height:5px;
    background:#182131;
    border-radius:10px;
    overflow:hidden;
    display:none;
}

.scan-bar{
    height:100%;
    width:0%;
    background:#42e6a4;
    border-radius:10px;
    box-shadow:0 0 15px #42e6a4;
    transition:width .2s linear;
}

.data-grid{
    margin-top:28px;
    display:grid;
    gap:14px;
}

.data-box{
    padding:18px;
    background:#0b1018;
    border:1px solid #202b3c;
    border-radius:18px;
}

.data-title{
    color:#78879c;
    font-size:11px;
    letter-spacing:1px;
    margin-bottom:9px;
}

.data-value{
    font-size:21px;
    font-weight:bold;
}

.data-small{
    margin-top:6px;
    color:#8492a7;
    font-size:12px;
}

.sensor-ok{
    color:#42e6a4;
}

.compass-container{
    margin:25px auto;
    width:220px;
    height:220px;
    border-radius:50%;
    background:radial-gradient(circle,#151e2d,#080b11);
    border:3px solid #2b374b;
    display:flex;
    align-items:center;
    justify-content:center;
    box-shadow:inset 0 0 35px #000000aa,0 0 25px #00000066;
}

.compass{
    width:180px;
    height:180px;
    border-radius:50%;
    position:relative;
    transition:transform .12s linear;
}

.direction{
    position:absolute;
    font-weight:bold;
    font-size:18px;
}

.north{
    top:3px;
    left:50%;
    transform:translateX(-50%);
    color:#ff5252;
}

.east{
    right:3px;
    top:50%;
    transform:translateY(-50%);
}

.south{
    bottom:3px;
    left:50%;
    transform:translateX(-50%);
}

.west{
    left:3px;
    top:50%;
    transform:translateY(-50%);
}

.needle{
    position:absolute;
    width:4px;
    height:70px;
    left:50%;
    top:20px;
    transform:translateX(-50%);
    transform-origin:50% 70px;
    background:linear-gradient(to bottom,#ff3b3b 50%,white 50%);
    border-radius:5px;
}

.center{
    position:absolute;
    width:18px;
    height:18px;
    border-radius:50%;
    background:white;
    left:50%;
    top:50%;
    transform:translate(-50%,-50%);
    box-shadow:0 0 12px white;
}

.audio-status{
    margin-top:15px;
    color:#42e6a4;
    font-size:13px;
    font-weight:bold;
}

.source-status{
    margin-top:8px;
    color:#65748a;
    font-size:11px;
}

button{
    width:100%;
    padding:20px;
    margin-top:20px;
    border:none;
    border-radius:18px;
    font-size:18px;
    font-weight:bold;
    cursor:pointer;
}

#startButton{
    background:#42e6a4;
    color:#07101d;
}

#stopButton{
    background:#151c28;
    color:#cbd7e9;
    border:1px solid #293448;
}

.detection-panel{
    margin-top:25px;
    padding:25px 20px;
    background:linear-gradient(145deg,#101827,#080c13);
    border:1px solid #29364b;
    border-radius:22px;
    text-align:left;
}

.detection-title{
    text-align:center;
    color:#42e6a4;
    font-size:12px;
    letter-spacing:2px;
    margin-bottom:20px;
}

.target-name{
    text-align:center;
    font-size:27px;
    font-weight:bold;
    margin-bottom:10px;
}

.target-type{
    text-align:center;
    color:#8ea1bb;
    font-size:12px;
    margin-bottom:20px;
}

.detection-row{
    display:flex;
    justify-content:space-between;
    gap:15px;
    padding:10px 0;
    border-bottom:1px solid #1b2636;
    font-size:13px;
}

.detection-label{
    color:#78879c;
}

.detection-value{
    font-weight:bold;
    text-align:right;
}

.signal-bar{
    margin-top:18px;
    height:8px;
    background:#182131;
    border-radius:10px;
    overflow:hidden;
}

.signal-fill{
    width:0%;
    height:100%;
    background:#42e6a4;
    transition:width .3s ease;
}

.lock-status{
    margin-top:18px;
    padding:12px;
    border-radius:12px;
    text-align:center;
    background:#111a27;
    color:#8290a5;
    font-size:12px;
    font-weight:bold;
}

.locked{
    color:#42e6a4;
    background:#0d211b;
}

.info{
    margin-top:22px;
    color:#69788e;
    font-size:12px;
    line-height:1.6;
}

.version{
    margin-top:25px;
    color:#42e6a4;
    font-size:11px;
    letter-spacing:2px;
}
</style>

</head>

<body>

<div class="app">

<h1>📡 RADIO TELESCOPE</h1>

<div class="subtitle">
MOBILE SKY DETECTION SYSTEM
</div>

<div class="receiver-panel">

<div class="status" id="status">
<span class="status-dot"></span>
RECEIVER STANDBY
</div>

<div class="scan-status" id="scanStatus">
System ready
</div>

<div class="scan-animation" id="scanAnimation">
<div class="scan-bar" id="scanBar"></div>
</div>

<div class="data-grid">

<div class="data-box">
<div class="data-title">📍 USER POSITION</div>
<div class="data-value" id="location">---</div>
<div class="data-small" id="accuracy">GPS inactive</div>
</div>

<div class="data-box">
<div class="data-title">🕐 LOCAL TIME</div>
<div class="data-value" id="time">--:--:--</div>
</div>

<div class="data-box">
<div class="data-title">🧭 MAGNETOMETER / COMPASS</div>
<div class="data-value" id="heading">--°</div>
<div class="data-small" id="direction">Compass inactive</div>
</div>

<div class="data-box">
<div class="data-title">📐 DEVICE ORIENTATION</div>
<div class="data-value" id="altitude">--°</div>
<div class="data-small" id="altitudeStatus">Phone altitude unavailable</div>
</div>

</div>

<div class="compass-container">

<div class="compass" id="compass">

<div class="direction north">N</div>
<div class="direction east">E</div>
<div class="direction south">S</div>
<div class="direction west">W</div>

<div class="needle"></div>
<div class="center"></div>

</div>

</div>

<div class="audio-status" id="audioStatus">
🔇 RADIO RECEIVER OFFLINE
</div>

<div class="source-status" id="sourceStatus">
Source: None
</div>

<button id="startButton" onclick="startReceiver()">
▶ START RECEIVER
</button>

<button id="stopButton" onclick="stopReceiver()">
■ STOP RECEIVER
</button>

<div class="detection-panel">

<div class="detection-title">
🌌 SKY OBJECT DETECTION
</div>

<div class="target-name" id="targetName">
TARGET: NULL
</div>

<div class="target-type" id="targetType">
POINT RECEIVER AT THE SKY
</div>

<div class="detection-row">
<span class="detection-label">📡 Signal strength</span>
<span class="detection-value" id="signalStrength">000000</span>
</div>

<div class="detection-row">
<span class="detection-label">🧭 Direction</span>
<span class="detection-value" id="targetDirection">---</span>
</div>

<div class="detection-row">
<span class="detection-label">📐 Altitude</span>
<span class="detection-value" id="targetAltitude">---</span>
</div>

<div class="detection-row">
<span class="detection-label">📏 Distance</span>
<span class="detection-value" id="targetDistance">---</span>
</div>

<div class="detection-row">
<span class="detection-label">🔭 Detection difficulty</span>
<span class="detection-value" id="targetDifficulty">---</span>
</div>

<div class="detection-row">
<span class="detection-label">🎧 Audio source</span>
<span class="detection-value" id="targetAudioSource">Radio noise</span>
</div>

<div class="detection-row">
<span class="detection-label">🎯 Detection field</span>
<span class="detection-value">±10°</span>
</div>

<div class="signal-bar">
<div class="signal-fill" id="signalFill"></div>
</div>

<div class="lock-status" id="lockStatus">
🔴 NO TARGET LOCKED
</div>

</div>

<div class="version">
RADIO TELESCOPE v0.7.2
</div>

</div>

<div class="info">

📡 Radio Telescope v0.7.2 uruchamia
syntetyczny szum radiowy natychmiast
po kliknięciu START RECEIVER.

<br><br>

🧭 GPS, kompas i orientacja telefonu
służą do określania kierunku obserwacji.

<br><br>

🎧 Po wykryciu obiektu system może
przełączyć się na jego sonifikację.

</div>

</div>

<script>

/* ==================================================
   RADIO TELESCOPE v0.7.2
================================================== */

let receiverActive = false;

let watchID = null;

let scanTimer = null;

let detectionTimer = null;

let compassHeading = null;

let phoneAltitude = null;

let userLatitude = null;

let userLongitude = null;

let currentTarget = null;

let audioContext = null;

let noiseSource = null;

let noiseGain = null;

let currentAudio = null;


/* ==================================================
   ELEMENTS
================================================== */

const statusElement =
document.getElementById("status");

const scanStatus =
document.getElementById("scanStatus");

const scanAnimation =
document.getElementById("scanAnimation");

const scanBar =
document.getElementById("scanBar");

const locationElement =
document.getElementById("location");

const accuracyElement =
document.getElementById("accuracy");

const timeElement =
document.getElementById("time");

const headingElement =
document.getElementById("heading");

const directionElement =
document.getElementById("direction");

const altitudeElement =
document.getElementById("altitude");

const altitudeStatus =
document.getElementById("altitudeStatus");

const compassElement =
document.getElementById("compass");

const audioStatus =
document.getElementById("audioStatus");

const sourceStatus =
document.getElementById("sourceStatus");

const targetName =
document.getElementById("targetName");

const targetType =
document.getElementById("targetType");

const signalStrength =
document.getElementById("signalStrength");

const signalFill =
document.getElementById("signalFill");

const targetDirection =
document.getElementById("targetDirection");

const targetAltitude =
document.getElementById("targetAltitude");

const targetDistance =
document.getElementById("targetDistance");

const targetDifficulty =
document.getElementById("targetDifficulty");

const targetAudioSource =
document.getElementById("targetAudioSource");

const lockStatus =
document.getElementById("lockStatus");


/* ==================================================
   TIME
================================================== */

function updateTime(){

const now = new Date();

timeElement.innerText =
now.toLocaleTimeString("pl-PL");

}

setInterval(updateTime,1000);

updateTime();


/* ==================================================
   DIRECTION
================================================== */

function getDirection(degrees){

if(degrees >=337.5 || degrees <22.5)
return "N";

if(degrees <67.5)
return "NE";

if(degrees <112.5)
return "E";

if(degrees <157.5)
return "SE";

if(degrees <202.5)
return "S";

if(degrees <247.5)
return "SW";

if(degrees <292.5)
return "W";

return "NW";

}


/* ==================================================
   RADIO NOISE
   STARTS IMMEDIATELY AFTER BUTTON CLICK
================================================== */

function startRadioNoise(){

if(audioContext){

if(audioContext.state === "suspended"){
audioContext.resume();
}

return;

}

try{

const AudioContext =
window.AudioContext ||
window.webkitAudioContext;

audioContext =
new AudioContext();

const buffer =
audioContext.createBuffer(
1,
audioContext.sampleRate * 2,
audioContext.sampleRate
);

const data =
buffer.getChannelData(0);

for(let i=0;i<data.length;i++){

data[i] =
(Math.random()*2-1);

}

noiseSource =
audioContext.createBufferSource();

noiseSource.buffer =
buffer;

noiseSource.loop =
true;

noiseGain =
audioContext.createGain();

noiseGain.gain.value =
0.035;

noiseSource.connect(noiseGain);

noiseGain.connect(
audioContext.destination
);

noiseSource.start();

audioStatus.innerText =
"🔊 RADIO RECEIVER ACTIVE";

sourceStatus.innerText =
"Source: Generated radio noise";

}catch(error){

console.error(error);

audioStatus.innerText =
"⚠️ AUDIO ERROR";

}

}


/* ==================================================
   STOP RADIO NOISE
================================================== */

function stopRadioNoise(){

if(noiseSource){

try{
noiseSource.stop();
}catch(e){}

noiseSource.disconnect();

noiseSource =
null;

}

if(audioContext){

audioContext.close();

audioContext =
null;

}

}


/* ==================================================
   COMPASS
================================================== */

function handleOrientation(event){

let heading;

if(
event.webkitCompassHeading !== undefined
){

heading =
event.webkitCompassHeading;

}else if(
event.alpha !== null
){

heading =
360-event.alpha;

}

if(heading === undefined)
return;

compassHeading =
(heading+360)%360;

headingElement.innerText =
Math.round(compassHeading)+"°";

directionElement.innerText =
getDirection(compassHeading);

compassElement.style.transform =
"rotate("+(-compassHeading)+"deg)";

}


/* ==================================================
   DEVICE MOTION
================================================== */

function handleMotion(event){

if(!event.accelerationIncludingGravity)
return;

const y =
event.accelerationIncludingGravity.y;

const z =
event.accelerationIncludingGravity.z;

if(y===null || z===null)
return;

let angle =
Math.atan2(-y,z) *
180/Math.PI;

phoneAltitude =
Math.max(
0,
Math.min(90,angle)
);

altitudeElement.innerText =
Math.round(phoneAltitude)+"°";

altitudeStatus.innerText =
"Phone orientation active";

altitudeStatus.className =
"data-small sensor-ok";

}


/* ==================================================
   GPS
================================================== */

function startGPS(){

if(!navigator.geolocation){

locationElement.innerText =
"GPS unavailable";

return;

}

watchID =
navigator.geolocation.watchPosition(

function(position){

userLatitude =
position.coords.latitude;

userLongitude =
position.coords.longitude;

const accuracy =
position.coords.accuracy;

locationElement.innerText =
userLatitude.toFixed(6)+
"°, "+
userLongitude.toFixed(6)+
"°";

accuracyElement.innerText =
"Accuracy: ±"+
Math.round(accuracy)+
" m";

},

function(){

locationElement.innerText =
"GPS permission denied";

},

{
enableHighAccuracy:true,
maximumAge:1000,
timeout:10000
}

);

}


/* ==================================================
   SENSOR PERMISSIONS
================================================== */

async function enableSensors(){

if(
typeof DeviceOrientationEvent !==
"undefined" &&
typeof DeviceOrientationEvent.requestPermission ===
"function"
){

try{

const permission =
await DeviceOrientationEvent.requestPermission();

if(permission === "granted"){

window.addEventListener(
"deviceorientation",
handleOrientation,
true
);

}

}catch(error){

console.error(error);

}

}else{

window.addEventListener(
"deviceorientationabsolute",
handleOrientation,
true
);

window.addEventListener(
"deviceorientation",
handleOrientation,
true
);

}


if(
typeof DeviceMotionEvent !==
"undefined" &&
typeof DeviceMotionEvent.requestPermission ===
"function"
){

try{

const permission =
await DeviceMotionEvent.requestPermission();

if(permission === "granted"){

window.addEventListener(
"devicemotion",
handleMotion,
true
);

}

}catch(error){

console.error(error);

}

}else{

window.addEventListener(
"devicemotion",
handleMotion,
true
);

}

}


/* ==================================================
   START RECEIVER
================================================== */

async function startReceiver(){

if(receiverActive)
return;

receiverActive =
true;


/*
IMPORTANT:
Audio starts HERE,
directly from the user's click.
This is important for Safari/iOS.
*/

startRadioNoise();


statusElement.classList.add(
"active"
);

statusElement.innerHTML =
'<span class="status-dot"></span>'+
'RECEIVER ACTIVE';


scanStatus.innerText =
"📡 RADIO RECEIVER INITIALIZING...";


startGPS();

await enableSensors();

startSkyScan();

}


/* ==================================================
   SKY SCAN
================================================== */

function startSkyScan(){

scanAnimation.style.display =
"block";

scanBar.style.width =
"0%";

let progress = 0;

scanTimer =
setInterval(

function(){

progress +=2;

scanBar.style.width =
progress+"%";

if(progress===20)
scanStatus.innerText =
"📍 LOCKING GPS POSITION...";

if(progress===40)
scanStatus.innerText =
"🧭 CALIBRATING COMPASS...";

if(progress===60)
scanStatus.innerText =
"📐 READING DEVICE ORIENTATION...";

if(progress===80)
scanStatus.innerText =
"🌌 SCANNING SKY...";

if(progress>=100){

clearInterval(scanTimer);

scanStatus.innerText =
"🌌 SKY SCAN ACTIVE";

detectionTimer =
setInterval(
detectObjects,
500
);

}

},

50

);

}


/* ==================================================
   OBJECT DETECTION
================================================== */

function detectObjects(){

if(!receiverActive)
return;


/*
Na tym etapie dźwięk pozostaje
aktywnym szumem radiowym.

Prawdziwe obliczanie pozycji obiektów
dodamy w kolejnej wersji.
*/

if(
userLatitude !== null &&
compassHeading !== null
){

/*
Symulacja sygnału odbiornika.
Później zastąpimy ją rzeczywistym
wyliczaniem pozycji obiektów.
*/

const signal =
Math.floor(
Math.random()*8
);

signalStrength.innerText =
signal;

signalFill.style.width =
signal+"%";

}

}


/* ==================================================
   STOP RECEIVER
================================================== */

function stopReceiver(){

receiverActive =
false;

clearInterval(scanTimer);

clearInterval(detectionTimer);

scanTimer =
null;

detectionTimer =
null;


/* STOP AUDIO */

stopRadioNoise();


/* STOP GPS */

if(watchID !== null){

navigator.geolocation
.clearWatch(watchID);

watchID =
null;

}


/* RESET */

statusElement.classList.remove(
"active"
);

statusElement.innerHTML =
'<span class="status-dot"></span>'+
'RECEIVER STANDBY';

scanAnimation.style.display =
"none";

scanBar.style.width =
"0%";

scanStatus.innerText =
"System ready";

audioStatus.innerText =
"🔇 RADIO RECEIVER OFFLINE";

sourceStatus.innerText =
"Source: None";


targetName.innerText =
"TARGET: NULL";

targetType.innerText =
"POINT RECEIVER AT THE SKY";

signalStrength.innerText =
"000000";

signalFill.style.width =
"0%";

targetDirection.innerText =
"---";

targetAltitude.innerText =
"---";

targetDistance.innerText =
"---";

targetDifficulty.innerText =
"---";

targetAudioSource.innerText =
"Radio noise";

lockStatus.innerText =
"🔴 NO TARGET LOCKED";

lockStatus.classList.remove(
"locked"
);

}

</script>

</body>
</html>
