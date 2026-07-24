<!DOCTYPE html>
<html lang="pl">

<head>

<meta charset="UTF-8">

<meta
name="viewport"
content="width=device-width, initial-scale=1.0, viewport-fit=cover"
>

<title>Radio Telescope v1.2.3</title>

<script src="https://cdn.jsdelivr.net/npm/astronomy-engine@2.1.19/astronomy.browser.min.js"></script>

<style>

*{
box-sizing:border-box;
}

body{

margin:0;

min-height:100vh;

background:
radial-gradient(
circle at top,
#18263b,
#05070b 70%
);

color:white;

font-family:
-apple-system,
BlinkMacSystemFont,
"Segoe UI",
Arial,
sans-serif;

text-align:center;

}

.app{

width:100%;

max-width:650px;

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

background:
linear-gradient(
145deg,
#101827,
#080b11
);

border:1px solid #273348;

border-radius:25px;

box-shadow:
0 15px 45px #00000099;

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

.status.active{

color:#42e6a4;

}

.status.active .status-dot{

background:#42e6a4;

box-shadow:
0 0 15px #42e6a4;

}

.scan-status{

margin-top:18px;

min-height:24px;

color:#8ea1bb;

font-size:13px;

letter-spacing:1px;

}

.data-grid{

margin-top:28px;

display:grid;

grid-template-columns:
1fr 1fr;

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

font-size:17px;

font-weight:bold;

word-break:break-word;

}

.data-small{

margin-top:6px;

color:#8492a7;

font-size:12px;

}


/* ================================
   COMPASS
================================ */

.compass-container{

margin:25px auto;

width:220px;

height:220px;

border-radius:50%;

background:
radial-gradient(
circle,
#151e2d,
#080b11
);

border:3px solid #2b374b;

display:flex;

align-items:center;

justify-content:center;

box-shadow:
inset 0 0 35px #000000aa,
0 0 25px #00000066;

}

.compass{

width:180px;

height:180px;

border-radius:50%;

position:relative;

transition:
transform .12s linear;

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

background:
linear-gradient(
to bottom,
#ff3b3b 50%,
white 50%
);

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

transform:
translate(-50%,-50%);

box-shadow:
0 0 12px white;

}


/* ================================
   AUDIO
================================ */

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

.audio-meter{

margin-top:20px;

height:10px;

background:#182131;

border-radius:10px;

overflow:hidden;

}

.audio-meter-fill{

height:100%;

width:0%;

background:#42e6a4;

transition:
width .2s ease;

}

.audio-info{

margin-top:8px;

font-size:11px;

color:#738197;

}


/* ================================
   BUTTONS
================================ */

button{

width:100%;

padding:20px;

margin-top:20px;

border:none;

border-radius:18px;

font-size:18px;

font-weight:bold;

cursor:pointer;

-webkit-tap-highlight-color:transparent;

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


/* ================================
   DETECTION
================================ */

.detection-panel{

margin-top:25px;

padding:25px 20px;

background:
linear-gradient(
145deg,
#101827,
#080c13
);

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

transition:
width .3s ease;

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


/* ================================
   BLACK HOLE
================================ */

.black-hole{

animation:
blackHoleRainbow 2s linear infinite,
blackHolePulse 1s ease-in-out infinite alternate;

font-weight:900;

}

@keyframes blackHoleRainbow{

0%{color:#ff004c;}

20%{color:#ff8a00;}

40%{color:#ffee00;}

60%{color:#00ff88;}

80%{color:#00c8ff;}

100%{color:#ff00ff;}

}

@keyframes blackHolePulse{

from{

transform:scale(1);

text-shadow:
0 0 5px currentColor;

}

to{

transform:scale(1.08);

text-shadow:
0 0 20px currentColor,
0 0 40px currentColor;

}

}

.black-hole-panel{

border-color:#ff00ff;

box-shadow:

0 0 20px #ff00ff33,

inset 0 0 20px #ff00ff11;

}


/* ================================
   SKY 360
================================ */

.sky-panel{

margin-top:25px;

padding:20px;

background:
linear-gradient(
145deg,
#101827,
#080c13
);

border:1px solid #29364b;

border-radius:22px;

}

.sky-title{

color:#42e6a4;

font-size:12px;

letter-spacing:2px;

margin-bottom:15px;

}

#skyCanvas{

width:100%;

height:400px;

display:block;

border-radius:18px;

background:
radial-gradient(
circle,
#101c30,
#02040a 75%
);

border:1px solid #1f2e43;

}

.sky-legend{

margin-top:12px;

font-size:10px;

line-height:1.8;

color:#718097;

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


<h1>

📡 RADIO TELESCOPE

</h1>


<div class="subtitle">

REAL-TIME ASTRONOMICAL SKY TRACKER

</div>


<div class="receiver-panel">


<div
class="status"
id="status"
>

<span class="status-dot"></span>

RECEIVER STANDBY

</div>


<div
class="scan-status"
id="scanStatus"
>

System ready

</div>


<div class="data-grid">


<div class="data-box">

<div class="data-title">

📍 OBSERVER POSITION

</div>

<div
class="data-value"
id="location"
>

---

</div>

<div
class="data-small"
id="accuracy"
>

GPS inactive

</div>

</div>


<div class="data-box">

<div class="data-title">

🕐 OBSERVATION TIME

</div>

<div
class="data-value"
id="time"
>

--:--:--

</div>

</div>


<div class="data-box">

<div class="data-title">

🧭 PHONE AZIMUTH

</div>

<div
class="data-value"
id="heading"
>

--°

</div>

<div
class="data-small"
id="direction"
>

Compass inactive

</div>

</div>


<div class="data-box">

<div class="data-title">

📐 PHONE ALTITUDE

</div>

<div
class="data-value"
id="altitude"
>

--°

</div>

<div
class="data-small"
id="altitudeStatus"
>

Orientation unavailable

</div>

</div>


</div>


<div class="compass-container">


<div
class="compass"
id="compass"
>


<div class="direction north">
N
</div>

<div class="direction east">
E
</div>

<div class="direction south">
S
</div>

<div class="direction west">
W
</div>


<div class="needle">
</div>


<div class="center">
</div>


</div>


</div>


<div
class="audio-status"
id="audioStatus"
>

🔇 RADIO RECEIVER OFFLINE

</div>


<div
class="source-status"
id="sourceStatus"
>

Source: None

</div>


<div class="audio-meter">

<div
class="audio-meter-fill"
id="audioMeterFill"
>

</div>

</div>


<div
class="audio-info"
id="audioInfo"
>

Signal audio: 0%

</div>


<button
id="startButton"
onclick="startReceiver()"
>

▶ START RECEIVER

</button>


<button
id="stopButton"
onclick="stopReceiver()"
>

■ STOP RECEIVER

</button>


<div
class="detection-panel"
id="detectionPanel"
>


<div class="detection-title">

🌌 REAL-TIME SKY OBJECT DETECTION

</div>


<div
class="target-name"
id="targetName"
>

TARGET: NULL

</div>


<div
class="target-type"
id="targetType"
>

POINT RECEIVER AT THE SKY

</div>


<div class="detection-row">

<span class="detection-label">
📡 Signal strength
</span>

<span
class="detection-value"
id="signalStrength"
>
000000
</span>

</div>


<div class="detection-row">

<span class="detection-label">
🧭 Object azimuth
</span>

<span
class="detection-value"
id="targetDirection"
>
---
</span>

</div>


<div class="detection-row">

<span class="detection-label">
📐 Object altitude
</span>

<span
class="detection-value"
id="targetAltitude"
>
---
</span>

</div>


<div class="detection-row">

<span class="detection-label">
📏 Distance
</span>

<span
class="detection-value"
id="targetDistance"
>
---
</span>

</div>


<div class="detection-row">

<span class="detection-label">
🔭 Detection difficulty
</span>

<span
class="detection-value"
id="targetDifficulty"
>
---
</span>

</div>


<div class="detection-row">

<span class="detection-label">
🎯 Detection field
</span>

<span
class="detection-value"
id="targetField"
>
---
</span>

</div>


<div class="detection-row">

<span class="detection-label">
🎧 Audio signal
</span>

<span
class="detection-value"
id="targetAudioSource"
>
Radio noise
</span>

</div>


<div class="signal-bar">

<div
class="signal-fill"
id="signalFill"
>

</div>

</div>


<div
class="lock-status"
id="lockStatus"
>

🔴 NO TARGET LOCKED

</div>


</div>


</div>


<!-- ================================
     SKY 360
================================ -->


<div class="sky-panel">


<div class="sky-title">

🌌 SKY 360 — LIVE SKY MAP

</div>


<canvas
id="skyCanvas"
>
</canvas>


<div class="sky-legend">

⭐ Stars — large

<br>

🪐 Planets — medium

<br>

🌌 Galaxies — smaller

<br>

💫 Nebulae — small

<br>

☄️ Comets — smallest

<br>

🕳️ Black holes — special rainbow signal

</div>


</div>


<div class="version">

RADIO TELESCOPE v1.2.3

</div>


<div class="info">

🌍 GPS określa pozycję obserwatora.

<br><br>

🧭 Kompas i czujniki telefonu
określają kierunek obserwacji.

<br><br>

🎧 Dźwięk obiektu jest odtwarzany
tak długo, jak długo obiekt znajduje
się w polu sygnału.

<br><br>

📻 Im dokładniejsze namierzenie,
tym mniej słyszalny jest szum.

<br><br>

📡 Projekt jest edukacyjnym
symulatorem radioteleskopu.

</div>


</div>


<script>


/* ==================================================
   RADIO TELESCOPE v1.2.3
================================================== */


/* ==================================================
   AUDIO FILES

   NAZWY ZACHOWANE ZE STAREGO SKRYPTU.

   WAŻNE:
   PLIKI MUSZĄ BYĆ W TYM SAMYM FOLDERZE
   CO index.html.
================================================== */


const AUDIO_FILES={

moon:"moon.mp3",

sun:"sun.wav",

venus:"venus.mp4",

andromeda:"andromeda.mp3",

vega:"vega.wav",

whirlpool:null

};


/* ==================================================
   VARIABLES
================================================== */


let receiverActive=false;

let watchID=null;

let compassHeading=null;

let filteredHeading=null;

let phoneAltitude=null;

let filteredAltitude=null;

let userLatitude=null;

let userLongitude=null;

let audioContext=null;

let noiseSource=null;

let noiseGain=null;

let detectionInterval=null;

let currentTarget=null;

let currentAudio=null;

let currentAudioKey=null;

let audioFadeInterval=null;

const SMOOTHING=0.15;


/* ==================================================
   ELEMENTS
================================================== */


const statusElement=
document.getElementById("status");

const scanStatus=
document.getElementById("scanStatus");

const locationElement=
document.getElementById("location");

const accuracyElement=
document.getElementById("accuracy");

const timeElement=
document.getElementById("time");

const headingElement=
document.getElementById("heading");

const directionElement=
document.getElementById("direction");

const altitudeElement=
document.getElementById("altitude");

const altitudeStatus=
document.getElementById("altitudeStatus");

const compassElement=
document.getElementById("compass");

const audioStatus=
document.getElementById("audioStatus");

const sourceStatus=
document.getElementById("sourceStatus");

const audioMeterFill=
document.getElementById("audioMeterFill");

const audioInfo=
document.getElementById("audioInfo");

const targetName=
document.getElementById("targetName");

const targetType=
document.getElementById("targetType");

const signalStrength=
document.getElementById("signalStrength");

const signalFill=
document.getElementById("signalFill");

const targetDirection=
document.getElementById("targetDirection");

const targetAltitude=
document.getElementById("targetAltitude");

const targetDistance=
document.getElementById("targetDistance");

const targetDifficulty=
document.getElementById("targetDifficulty");

const targetField=
document.getElementById("targetField");

const targetAudioSource=
document.getElementById("targetAudioSource");

const lockStatus=
document.getElementById("lockStatus");

const detectionPanel=
document.getElementById("detectionPanel");


/* ==================================================
   TIME
================================================== */


function updateTime(){

const now=
new Date();

timeElement.innerText=
now.toLocaleTimeString(
"pl-PL"
);

}


setInterval(
updateTime,
1000
);

updateTime();


/* ==================================================
   DIRECTION
================================================== */


function getDirection(
degrees
){

if(
degrees>=337.5||
degrees<22.5
)
return"N";

if(
degrees<67.5
)
return"NE";

if(
degrees<112.5
)
return"E";

if(
degrees<157.5
)
return"SE";

if(
degrees<202.5
)
return"S";

if(
degrees<247.5
)
return"SW";

if(
degrees<292.5
)
return"W";

return"NW";

}


/* ==================================================
   ANGLE DIFFERENCE
================================================== */


function angleDifference(
a,
b
){

const difference=
Math.abs(
a-b
);

return Math.min(

difference,

360-difference

);

}


/* ==================================================
   SMOOTH ANGLE
================================================== */


function smoothAngle(
previous,
current,
factor
){

if(
previous===null
){

return current;

}

let difference=

(
current-
previous+
540
)
%
360
-
180;

return(

previous+
difference*
factor+
360

)
%
360;

}


/* ==================================================
   RADIO NOISE
================================================== */


function startRadioNoise(){

const AudioContextClass=

window.AudioContext||
window.webkitAudioContext;

if(
!AudioContextClass
){

audioStatus.innerText=
"⚠️ Web Audio unavailable";

return;

}


if(
audioContext
){

if(
audioContext.state===
"suspended"
){

audioContext.resume();

}

return;

}


audioContext=
new AudioContextClass();


const buffer=

audioContext.createBuffer(

1,

audioContext.sampleRate*2,

audioContext.sampleRate

);


const data=
buffer.getChannelData(0);


for(

let i=0;

i<data.length;

i++

){

data[i]=

Math.random()*2-1;

}


noiseSource=
audioContext.createBufferSource();


noiseSource.buffer=
buffer;

noiseSource.loop=
true;


noiseGain=
audioContext.createGain();


noiseGain.gain.value=
0.04;


noiseSource.connect(
noiseGain
);


noiseGain.connect(
audioContext.destination
);


noiseSource.start();


audioStatus.innerText=
"🔊 RADIO RECEIVER ACTIVE";


sourceStatus.innerText=
"Source: Generated radio noise";

}


/* ==================================================
   AUDIO KEY
================================================== */


function getAudioKey(
object
){

if(
object.audioKey
){

return object.audioKey;

}


if(
object.name.includes("MOON")
){

return"moon";

}


if(
object.name.includes("SUN")
){

return"sun";

}


if(
object.name.includes("VENUS")
){

return"venus";

}


if(
object.name.includes("VEGA")
){

return"vega";

}


if(
object.name.includes("M31")
){

return"andromeda";

}


if(
object.name.includes("M51")
){

return"whirlpool";

}


return null;

}


/* ==================================================
   PLAY OBJECT AUDIO
================================================== */


function playObjectAudio(
object,
volume
){

const key=
getAudioKey(
object
);


const file=
AUDIO_FILES[key];


if(
!file
){

return;

}


/* SAME AUDIO */

if(

currentAudio&&

currentAudioKey===key

){

fadeAudioVolume(
volume
);

return;

}


/* STOP PREVIOUS */

stopObjectAudio();


currentAudio=
new Audio(
file
);


currentAudio.loop=
true;


currentAudio.volume=
0;


currentAudio.preload=
"auto";


currentAudioKey=
key;


/* SAFARI AUDIO */

const playPromise=
currentAudio.play();


if(
playPromise
){

playPromise.catch(

function(error){

console.warn(
"Audio playback blocked:",
error
);

sourceStatus.innerText=
"⚠️ Audio error: "+
file;

}

);

}


fadeAudioVolume(
volume
);


audioStatus.innerText=
"🎧 OBJECT AUDIO ACTIVE";


sourceStatus.innerText=
"Source: "+
file;


targetAudioSource.innerText=
"🎧 "+
file;

}


/* ==================================================
   FADE AUDIO
================================================== */


function fadeAudioVolume(
targetVolume
){

if(
!currentAudio
){

return;

}


targetVolume=

Math.max(

0,

Math.min(

1,

targetVolume

)

);


if(
audioFadeInterval
){

clearInterval(
audioFadeInterval
);

}


const start=
currentAudio.volume;


const difference=
targetVolume-start;


const steps=
12;


let step=0;


audioFadeInterval=

setInterval(

function(){

step++;


if(
currentAudio
){

currentAudio.volume=

Math.max(

0,

Math.min(

1,

start+
difference*
(
step/
steps
)

)

);

}


if(
step>=steps
){

clearInterval(
audioFadeInterval
);

audioFadeInterval=
null;

}

},

30

);

}


/* ==================================================
   STOP OBJECT AUDIO
================================================== */


function stopObjectAudio(){

if(
audioFadeInterval
){

clearInterval(
audioFadeInterval
);

audioFadeInterval=
null;

}


if(
currentAudio
){

try{

currentAudio.pause();

currentAudio.currentTime=0;

}

catch(e){}

}


currentAudio=
null;


currentAudioKey=
null;

}


/* ==================================================
   AUDIO MIX
================================================== */


function updateAudioMix(
object,
accuracyScore
){

if(
!noiseGain||
!audioContext
){

return;

}


const signalBase=
object.signal/
100;


/*

0 = center
1 = edge

*/

const proximity=

Math.max(

0,

Math.min(

1,

1-accuracyScore

)

);


/*

OBJECT VOLUME

100% signal = original volume

*/

const objectVolume=

signalBase*
proximity;


/*

RADIO NOISE

Strong signal = less noise

*/

const noiseVolume=

0.04*
(
1-
proximity*
signalBase
);


/* NOISE */

noiseGain.gain.setTargetAtTime(

noiseVolume,

audioContext.currentTime,

0.05

);


/* OBJECT */

if(
getAudioKey(object)
){

playObjectAudio(

object,

objectVolume

);

}

else{

stopObjectAudio();

}


/* UI */

audioMeterFill.style.width=

Math.round(
objectVolume*
100
)
+
"%";


audioInfo.innerText=

"Object signal: "+
Math.round(
objectVolume*
100
)
+
"% | Radio noise: "+
Math.round(
(
noiseVolume/
0.04
)
*
100
)
+
"%";

}


/* ==================================================
   STOP RADIO
================================================== */


function stopRadioNoise(){

stopObjectAudio();


if(
noiseSource
){

try{

noiseSource.stop();

}

catch(e){}


noiseSource.disconnect();

noiseSource=null;

}


if(
audioContext
){

audioContext.close();

audioContext=null;

}


noiseGain=null;

}


/* ==================================================
   COMPASS
================================================== */


function handleOrientation(
event
){

let heading;


if(

event.webkitCompassHeading!==undefined&&

event.webkitCompassHeading!==null

){

heading=
event.webkitCompassHeading;

}

else if(
event.alpha!==null
){

heading=
360-event.alpha;

}


if(

heading===undefined||

heading===null||

isNaN(heading)

){

return;

}


heading=

(
heading+
360
)
%
360;


filteredHeading=

smoothAngle(

filteredHeading,

heading,

SMOOTHING

);


compassHeading=
filteredHeading;


headingElement.innerText=

Math.round(
filteredHeading
)
+
"°";


directionElement.innerText=

getDirection(
filteredHeading
);


compassElement.style.transform=

"rotate("+
(-filteredHeading)+
"deg)";


if(
receiverActive
){

detectObjects();

}

}


/* ==================================================
   PHONE ALTITUDE
================================================== */


function handleMotion(
event
){

if(

!event.accelerationIncludingGravity

){

return;

}


const y=
event.accelerationIncludingGravity.y;

const z=
event.accelerationIncludingGravity.z;


if(
y===null||
z===null
){

return;

}


let angle=

Math.atan2(
-y,
z
)
*
180/
Math.PI;


angle=

Math.max(

0,

Math.min(

90,

angle

)

);


if(
filteredAltitude===null
){

filteredAltitude=
angle;

}

else{

filteredAltitude+=

(
angle-
filteredAltitude
)
*
SMOOTHING;

}


phoneAltitude=
filteredAltitude;


altitudeElement.innerText=

Math.round(
filteredAltitude
)
+
"°";


altitudeStatus.innerText=
"Orientation active";


if(
receiverActive
){

detectObjects();

}

}


/* ==================================================
   GPS
================================================== */


function startGPS(){

if(
!navigator.geolocation
){

locationElement.innerText=
"GPS unavailable";

return;

}


watchID=

navigator.geolocation.watchPosition(

function(position){

userLatitude=
position.coords.latitude;


userLongitude=
position.coords.longitude;


locationElement.innerText=

userLatitude.toFixed(5)

+
"°, "

+
userLongitude.toFixed(5)

+
"°";


accuracyElement.innerText=

"Accuracy ±"+
Math.round(
position.coords.accuracy
)
+
" m";


scanStatus.innerText=
"🌍 GPS POSITION LOCKED";

},

function(){

scanStatus.innerText=
"⚠️ GPS ERROR";

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

typeof DeviceOrientationEvent!=="undefined"

&&

typeof DeviceOrientationEvent.requestPermission==="function"

){

try{

const permission=

await
DeviceOrientationEvent
.requestPermission();


if(
permission==="granted"
){

window.addEventListener(

"deviceorientation",

handleOrientation,

true

);

}

}

catch(error){

console.error(error);

}

}

else{

window.addEventListener(

"deviceorientation",

handleOrientation,

true

);

}


if(

typeof DeviceMotionEvent!=="undefined"

&&

typeof DeviceMotionEvent.requestPermission==="function"

){

try{

const permission=

await
DeviceMotionEvent
.requestPermission();


if(
permission==="granted"
){

window.addEventListener(

"devicemotion",

handleMotion,

true

);

}

}

catch(error){

console.error(error);

}

}

else{

window.addEventListener(

"devicemotion",

handleMotion,

true

);

}

}


/* ==================================================
   PLANETS
================================================== */


const bodies=[

{

name:"☀️ SUN",

body:"Sun",

type:"Star",

difficulty:"BARDZO ŁATWE",

signal:100,

detectionRadius:14,

distanceLabel:"150 million km"

},

{

name:"🌙 MOON",

body:"Moon",

type:"Natural satellite",

difficulty:"BARDZO ŁATWE",

signal:100,

detectionRadius:14

},

{

name:"☿ MERCURY",

body:"Mercury",

type:"Planet",

difficulty:"TRUDNE",

signal:55,

detectionRadius:10

},

{

name:"♀ VENUS",

body:"Venus",

type:"Planet",

difficulty:"ŁATWE",

signal:95,

detectionRadius:14,

audioKey:"venus"

},

{

name:"♂ MARS",

body:"Mars",

type:"Planet",

difficulty:"ŚREDNIE",

signal:70,

detectionRadius:12

},

{

name:"♃ JUPITER",

body:"Jupiter",

type:"Planet",

difficulty:"ŁATWE",

signal:92,

detectionRadius:13

},

{

name:"♄ SATURN",

body:"Saturn",

type:"Planet",

difficulty:"ŁATWE",

signal:88,

detectionRadius:12

},

{

name:"♅ URANUS",

body:"Uranus",

type:"Planet",

difficulty:"TRUDNE",

signal:55,

detectionRadius:10

},

{

name:"♆ NEPTUNE",

body:"Neptune",

type:"Planet",

difficulty:"BARDZO TRUDNE",

signal:35,

detectionRadius:10

}

];


/* ==================================================
   STARS
================================================== */


const stars=[

{

name:"⭐ VEGA",

type:"Star",

ra:18.6156,

dec:38.7837,

distance:25.04,

difficulty:"ŁATWE",

signal:90,

detectionRadius:13,

audioKey:"vega"

},

{

name:"⭐ SIRIUS",

type:"Star",

ra:6.7525,

dec:-16.7161,

distance:8.60,

difficulty:"BARDZO ŁATWE",

signal:100,

detectionRadius:12

},

{

name:"⭐ ARCTURUS",

type:"Star",

ra:14.2610,

dec:19.1825,

distance:36.7,

difficulty:"ŁATWE",

signal:96,

detectionRadius:12

},

{

name:"⭐ ALTAIR",

type:"Star",

ra:19.8464,

dec:8.8683,

distance:16.73,

difficulty:"ŁATWE",

signal:94,

detectionRadius:12

},

{

name:"⭐ CAPELLA",

type:"Star",

ra:5.2782,

dec:45.9980,

distance:42.92,

difficulty:"ŁATWE",

signal:95,

detectionRadius:12

},

{

name:"⭐ BETELGEUSE",

type:"Star",

ra:5.9195,

dec:7.4071,

distance:642.5,

difficulty:"ŚREDNIE",

signal:90,

detectionRadius:12

},

{

name:"⭐ RIGEL",

type:"Star",

ra:5.2423,

dec:-8.2016,

distance:860,

difficulty:"ŚREDNIE",

signal:85,

detectionRadius:12

},

{

name:"⭐ DENEB",

type:"Star",

ra:20.6905,

dec:45.2803,

distance:2615,

difficulty:"ŚREDNIE",

signal:88,

detectionRadius:12

},

{

name:"⭐ ALDEBARAN",

type:"Star",

ra:4.5987,

dec:16.5093,

distance:65.23,

difficulty:"ŁATWE",

signal:91,

detectionRadius:12

},

{

name:"⭐ POLARIS",

type:"Star",

ra:2.5303,

dec:89.2641,

distance:447,

difficulty:"ŁATWE",

signal:93,

detectionRadius:12

}

];


/* ==================================================
   DEEP SKY
================================================== */


const deepSky=[

{

name:"🌌 M31 — ANDROMEDA GALAXY",

type:"Galaxy",

ra:0.712,

dec:41.269,

distance:2540000,

difficulty:"ŁATWE",

signal:80,

detectionRadius:12,

distanceLabel:"2.54 million light years",

audioKey:"andromeda"

},

{

name:"🌀 M51 — WHIRLPOOL GALAXY",

type:"Galaxy",

ra:13.498,

dec:47.195,

distance:23000000,

difficulty:"TRUDNE",

signal:50,

detectionRadius:11,

distanceLabel:"23 million light years",

audioKey:"whirlpool"

},

{

name:"🌌 M87",

type:"Galaxy",

ra:12.514,

dec:12.392,

distance:53500000,

difficulty:"BARDZO TRUDNE",

signal:50,

detectionRadius:10,

distanceLabel:"53.5 million light years"

},

{

name:"🌌 M104 — SOMBRERO GALAXY",

type:"Galaxy",

ra:12.667,

dec:-11.623,

distance:31000000,

difficulty:"TRUDNE",

signal:50,

detectionRadius:10,

distanceLabel:"31 million light years"

},

{

name:"🌌 MILKY WAY CENTER",

type:"Galaxy",

ra:17.761,

dec:-29.007,

distance:26000,

difficulty:"ŚREDNIE",

signal:90,

detectionRadius:11,

distanceLabel:"26 000 light years"

},

{

name:"💫 HELIX NEBULA",

type:"Nebula",

ra:22.493,

dec:-20.837,

distance:655,

difficulty:"TRUDNE",

signal:70,

detectionRadius:11,

distanceLabel:"655 light years"

},

{

name:"💫 CRAB NEBULA",

type:"Nebula",

ra:5.5756,

dec:22.0145,

distance:6500,

difficulty:"ŚREDNIE",

signal:82,

detectionRadius:11,

distanceLabel:"6 500 light years"

},

{

name:"💫 CARINA NEBULA",

type:"Nebula",

ra:10.75,

dec:-59.87,

distance:8500,

difficulty:"ŚREDNIE",

signal:80,

detectionRadius:11,

distanceLabel:"8 500 light years"

},

{

name:"💫 M16 — EAGLE NEBULA",

type:"Nebula",

ra:18.313,

dec:-13.783,

distance:7000,

difficulty:"ŚREDNIE",

signal:78,

detectionRadius:11,

distanceLabel:"7 000 light years"

},

{

name:"💫 NGC 6543 — CAT'S EYE",

type:"Nebula",

ra:17.976,

dec:66.633,

distance:3300,

difficulty:"TRUDNE",

signal:60,

detectionRadius:10,

distanceLabel:"3 300 light years"

},

{

name:"💫 IC 443 — JELLYFISH NEBULA",

type:"Nebula",

ra:6.283,

dec:22.533,

distance:5000,

difficulty:"TRUDNE",

signal:55,

detectionRadius:10,

distanceLabel:"5 000 light years"

},

{

name:"🪨 67P — CHURYUMOV-GERASIMENKO",

type:"Comet",

ra:0,

dec:0,

distance:0,

difficulty:"BARDZO TRUDNE",

signal:35,

detectionRadius:9,

distanceLabel:"Dynamic comet"

},

{

name:"🌀 PERSEUS CLUSTER",

type:"Galaxy Cluster",

ra:3.333,

dec:41.5,

distance:240000000,

difficulty:"BARDZO TRUDNE",

signal:45,

detectionRadius:10,

distanceLabel:"240 million light years"

},

{

name:"💥 CHANDRA DEEP FIELD",

type:"Deep Field",

ra:3.5,

dec:-27.8,

distance:13000000000,

difficulty:"EKSTREMALNIE TRUDNE",

signal:25,

detectionRadius:9,

distanceLabel:"Billions of light years"

},

{

name:"💫 V404 CYGNI",

type:"Black Hole Binary",

ra:20.411,

dec:33.867,

distance:7800,

difficulty:"BARDZO TRUDNE",

signal:40,

detectionRadius:9,

distanceLabel:"7 800 light years"

},

{

name:"🕳️ SAGITTARIUS A*",

type:"Supermassive Black Hole",

ra:17.761,

dec:-29.007,

distance:26000,

difficulty:"BARDZO TRUDNE",

signal:88,

detectionRadius:8,

distanceLabel:"26 000 light years",

blackHole:true

}

];


/* ==================================================
   STAR POSITION
================================================== */


function calculateStarPosition(
star
){

const date=
new Date();


const jd=
Astronomy.MakeTime(
date
).ut;


const T=

(
jd-
2451545.0
)
/
36525.0;


const raDegrees=
star.ra*15;


const ra=

raDegrees+

(
3.075+
1.336*
Math.sin(
star.dec*
Math.PI/
180
)
)
*
T;


const dec=

star.dec+

(
20.04*T
)
/
3600;


const gst=
Astronomy.SiderealTime(
date
);


const lst=

(
gst+
userLongitude/15
)
%24;


let ha=

lst-
ra/15;


if(
ha<-12
){

ha+=24;

}


if(
ha>12
){

ha-=24;

}


const haRad=

ha*
15*
Math.PI/
180;


const decRad=

dec*
Math.PI/
180;


const latRad=

userLatitude*
Math.PI/
180;


const sinAltitude=

Math.sin(decRad)*
Math.sin(latRad)

+

Math.cos(decRad)*
Math.cos(latRad)*
Math.cos(haRad);


const altitude=

Math.asin(
sinAltitude
)
*
180/
Math.PI;


let azimuth=

Math.atan2(

Math.sin(haRad),

Math.cos(haRad)*
Math.sin(latRad)

-

Math.tan(decRad)*
Math.cos(latRad)

)
*
180/
Math.PI;


azimuth=

(
azimuth+
180+
360
)
%360;


return{

...star,

azimuth:
azimuth,

altitude:
altitude

};

}


/* ==================================================
   SKY POSITIONS
================================================== */


function calculateSkyPositions(){

if(

userLatitude===null||

userLongitude===null

){

return[];

}


const observer=

new Astronomy.Observer(

userLatitude,

userLongitude,

0

);


const date=
new Date();


const results=[];


/* PLANETS */

for(
const object of bodies
){

try{

const equator=

Astronomy.Equator(

object.body,

date,

observer,

true,

true

);


const horizontal=

Astronomy.Horizon(

date,

observer,

equator.ra,

equator.dec,

"normal"

);


results.push({

...object,

azimuth:
horizontal.azimuth,

altitude:
horizontal.altitude,

distance:
horizontal.dist

});

}

catch(error){

console.error(
"Planet error",
error
);

}

}


/* STARS */

for(
const star of stars
){

try{

results.push(

calculateStarPosition(
star
)

);

}

catch(error){

console.error(
"Star error",
error
);

}

}


/* DEEP SKY */

for(
const object of deepSky
){

try{

results.push(

calculateStarPosition(
object
)

);

}

catch(error){

console.error(
"Deep sky error",
error
);

}

}


return results;

}


/* ==================================================
   DETECTION
================================================== */


function detectObjects(){

if(
!receiverActive
){

return;

}


if(

userLatitude===null||

userLongitude===null

){

scanStatus.innerText=
"🌍 Waiting for GPS...";

return;

}


if(

compassHeading===null||

phoneAltitude===null

){

scanStatus.innerText=
"🧭 Waiting for phone orientation...";

return;

}


const skyObjects=
calculateSkyPositions();


let bestTarget=
null;

let bestScore=
Infinity;


for(
const object of skyObjects
){

if(
object.altitude<0
){

continue;

}


const azimuthDifference=

angleDifference(

compassHeading,

object.azimuth

);


const altitudeDifference=

Math.abs(

phoneAltitude-

object.altitude

);


const radius=

object.detectionRadius||
12;


if(

azimuthDifference<=radius&&

altitudeDifference<=radius

){

const score=

azimuthDifference+
altitudeDifference;


if(
score<bestScore
){

bestScore=
score;

bestTarget=
object;

}

}

}


if(
bestTarget
){

const radius=

bestTarget.detectionRadius||
12;


const azimuthDifference=

angleDifference(

compassHeading,

bestTarget.azimuth

);


const altitudeDifference=

Math.abs(

phoneAltitude-
bestTarget.altitude

);


const accuracy=

Math.min(

1,

(

azimuthDifference+
altitudeDifference
)

/
(
radius*2
)

);


updateAudioMix(

bestTarget,

accuracy

);


lockTarget(

bestTarget,

accuracy

);

}

else{

unlockTarget();

}

}


/* ==================================================
   LOCK TARGET
================================================== */


function lockTarget(
object,
accuracy
){

currentTarget=
object;


targetName.innerText=
object.name;


targetType.innerText=
object.type;


signalStrength.innerText=
object.signal;


signalFill.style.width=
object.signal+
"%";


targetDirection.innerText=

object.azimuth.toFixed(1)

+
"° "
+
getDirection(
object.azimuth
);


targetAltitude.innerText=

object.altitude.toFixed(1)
+
"°";


if(
object.distanceLabel
){

targetDistance.innerText=
object.distanceLabel;

}

else if(
object.type==="Star"
){

targetDistance.innerText=

object.distance+
" light years";

}

else{

targetDistance.innerText=

object.distance
?

object.distance.toFixed(4)
+
" AU"

:

"---";

}


targetDifficulty.innerText=
object.difficulty;


targetField.innerText=

"±"+
object.detectionRadius+
"°";


const audioKey=
getAudioKey(
object
);


if(

audioKey&&

AUDIO_FILES[audioKey]

){

targetAudioSource.innerText=

"🎧 "+
AUDIO_FILES[audioKey];

}

else{

targetAudioSource.innerText=
"📻 Radio noise";

}


lockStatus.innerText=
"🟢 TARGET LOCKED";


lockStatus.classList.add(
"locked"
);


/* BLACK HOLE */

if(
object.blackHole
){

targetName.classList.add(
"black-hole"
);


detectionPanel.classList.add(
"black-hole-panel"
);


scanStatus.innerText=

"🕳️🌈 YOU FOUND THE VOID! 🌈🕳️";

}

else{

targetName.classList.remove(
"black-hole"
);


detectionPanel.classList.remove(
"black-hole-panel"
);


scanStatus.innerText=

"🎯 LOCKED: "+
object.name;

}

}


/* ==================================================
   UNLOCK
================================================== */


function unlockTarget(){

currentTarget=
null;


if(
noiseGain&&
audioContext
){

noiseGain.gain.setTargetAtTime(

0.04,

audioContext.currentTime,

0.15

);

}


stopObjectAudio();


audioMeterFill.style.width=
"0%";


audioInfo.innerText=

"Signal audio: 0% | Radio noise: 100%";


targetName.classList.remove(
"black-hole"
);


detectionPanel.classList.remove(
"black-hole-panel"
);


targetName.innerText=
"TARGET: NULL";


targetType.innerText=
"POINT RECEIVER AT THE SKY";


signalStrength.innerText=
"000000";


signalFill.style.width=
"0%";


targetDirection.innerText=
"---";


targetAltitude.innerText=
"---";


targetDistance.innerText=
"---";


targetDifficulty.innerText=
"---";


targetField.innerText=
"---";


targetAudioSource.innerText=
"Radio noise";


lockStatus.innerText=
"🔴 NO TARGET LOCKED";


lockStatus.classList.remove(
"locked"
);


audioStatus.innerText=
"🔊 RADIO RECEIVER ACTIVE";


sourceStatus.innerText=
"Source: Generated radio noise";


scanStatus.innerText=
"🌌 SCANNING SKY...";

}


/* ==================================================
   SKY 360
================================================== */


const skyCanvas=
document.getElementById(
"skyCanvas"
);


const skyCtx=
skyCanvas.getContext(
"2d"
);


function resizeSkyCanvas(){

const rect=
skyCanvas.getBoundingClientRect();


const ratio=
window.devicePixelRatio||
1;


skyCanvas.width=
rect.width*
ratio;


skyCanvas.height=
rect.height*
ratio;


skyCtx.setTransform(

ratio,

0,

0,

ratio,

0,

0

);

}


window.addEventListener(
"resize",
resizeSkyCanvas
);


resizeSkyCanvas();


function getObjectSize(
object
){

if(
object.blackHole
)
return 9;


if(
object.type==="Star"
)
return 7;


if(
object.type==="Planet"
)
return 5;


if(
object.type==="Natural satellite"
)
return 6;


if(
object.type==="Galaxy"
)
return 4;


if(
object.type==="Nebula"
)
return 3;


if(
object.type==="Comet"
)
return 2;


if(
object.type==="Galaxy Cluster"
)
return 3;


return 3;

}


function getObjectColor(
object
){

if(
object.blackHole
)
return"#ff00ff";


if(
object.type==="Star"
)
return"#ffffff";


if(
object.type==="Planet"
)
return"#42e6a4";


if(
object.type==="Natural satellite"
)
return"#dddddd";


if(
object.type==="Galaxy"
)
return"#a66cff";


if(
object.type==="Nebula"
)
return"#ff6bd6";


if(
object.type==="Comet"
)
return"#8defff";


return"#ffb84d";

}


function drawSky(){

const width=
skyCanvas.clientWidth;


const height=
skyCanvas.clientHeight;


skyCtx.clearRect(

0,

0,

width,

height

);


/* BACKGROUND */

skyCtx.fillStyle=
"#03060d";


skyCtx.fillRect(

0,

0,

width,

height

);


/* GRID */

skyCtx.strokeStyle=
"#122033";


skyCtx.lineWidth=1;


for(
let i=1;
i<8;
i++
){

const x=
width*i/8;


skyCtx.beginPath();

skyCtx.moveTo(
x,
0
);

skyCtx.lineTo(
x,
height
);

skyCtx.stroke();

}


for(
let i=1;
i<6;
i++
){

const y=
height*i/6;


skyCtx.beginPath();

skyCtx.moveTo(
0,
y
);

skyCtx.lineTo(
width,
y
);

skyCtx.stroke();

}


/* CENTER */

skyCtx.beginPath();

skyCtx.arc(

width/2,

height/2,

7,

0,

Math.PI*2

);


skyCtx.fillStyle=
"#42e6a4";


skyCtx.fill();


/* OBJECTS */

if(
userLatitude===null||
userLongitude===null||
compassHeading===null||
phoneAltitude===null
){

skyCtx.fillStyle=
"#718097";


skyCtx.font=
"13px Arial";


skyCtx.textAlign=
"center";


skyCtx.fillText(

"Start receiver to calculate the sky",

width/2,

height/2+35

);


return;

}


const objects=
calculateSkyPositions();


for(
const object of objects
){

if(
object.altitude<0
)
continue;


let azDifference=

(
object.azimuth-
compassHeading+
540
)
%360-
180;


let x=

width/2+

(
azDifference/
90
)
*
width/2;


let altitudeDifference=

object.altitude-
phoneAltitude;


let y=

height/2-

(
altitudeDifference/
45
)
*
height/2;


if(
x<0||
x>width||
y<0||
y>height
)
continue;


const size=
getObjectSize(
object
);


const color=
getObjectColor(
object
);


skyCtx.beginPath();


skyCtx.arc(

x,

y,

size,

0,

Math.PI*2

);


skyCtx.fillStyle=
color;


skyCtx.shadowBlur=

object.blackHole
?
20
:
8;


skyCtx.shadowColor=
color;


skyCtx.fill();


skyCtx.shadowBlur=0;


skyCtx.font=
"9px Arial";


skyCtx.textAlign=
"center";


skyCtx.fillStyle=
"#d7e0ed";


skyCtx.fillText(

object.name,

x,

y+
size+
12

);

}

}


setInterval(

drawSky,

1000

);


/* ==================================================
   START RECEIVER
================================================== */


async function startReceiver(){

if(
receiverActive
){

return;

}


receiverActive=
true;


/*

Audio is started directly
from START RECEIVER.

Important for Safari/iPad/iPhone.

*/


startRadioNoise();


statusElement.classList.add(
"active"
);


statusElement.innerHTML=

'<span class="status-dot"></span>RECEIVER ACTIVE';


scanStatus.innerText=
"📡 INITIALIZING RECEIVER...";


startGPS();


await enableSensors();


setTimeout(

function(){

scanStatus.innerText=
"🌌 CALCULATING SKY OBJECTS...";

},

1000

);


detectionInterval=

setInterval(

detectObjects,

500

);


drawSky();

}


/* ==================================================
   STOP RECEIVER
================================================== */


function stopReceiver(){

receiverActive=
false;


if(
detectionInterval
){

clearInterval(
detectionInterval
);

detectionInterval=
null;

}


stopRadioNoise();


if(
watchID!==null
){

navigator.geolocation.clearWatch(
watchID
);

watchID=
null;

}


currentTarget=
null;


statusElement.classList.remove(
"active"
);


statusElement.innerHTML=

'<span class="status-dot"></span>RECEIVER STANDBY';


scanStatus.innerText=
"System ready";


audioStatus.innerText=
"🔇 RADIO RECEIVER OFFLINE";


sourceStatus.innerText=
"Source: None";


audioMeterFill.style.width=
"0%";


audioInfo.innerText=
"Signal audio: 0%";


targetName.classList.remove(
"black-hole"
);


detectionPanel.classList.remove(
"black-hole-panel"
);


targetName.innerText=
"TARGET: NULL";


targetType.innerText=
"POINT RECEIVER AT THE SKY";


signalStrength.innerText=
"000000";


signalFill.style.width=
"0%";


targetDirection.innerText=
"---";


targetAltitude.innerText=
"---";


targetDistance.innerText=
"---";


targetDifficulty.innerText=
"---";


targetField.innerText=
"---";


targetAudioSource.innerText=
"Radio noise";


lockStatus.innerText=
"🔴 NO TARGET LOCKED";


lockStatus.classList.remove(
"locked"
);


drawSky();

}


/* ==================================================
   INITIAL
================================================== */


drawSky();

</script>

</body>

</html>
