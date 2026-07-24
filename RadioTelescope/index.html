<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">

<meta name="viewport"
content="width=device-width,
initial-scale=1.0,
maximum-scale=1.0,
user-scalable=no">

<title>Radio Telescope v1.2.2</title>

<script src="https://cdn.jsdelivr.net/npm/astronomy-engine@2.1.19/astronomy.browser.min.js"></script>

<style>

*{
box-sizing:border-box;
}

html,body{
margin:0;
padding:0;
min-height:100%;
background:#02040a;
color:#ffffff;
font-family:-apple-system,
BlinkMacSystemFont,
"Segoe UI",
Arial,
sans-serif;
}

body{
min-height:100vh;
}

.app{
width:100%;
max-width:720px;
margin:auto;
padding:20px 14px 60px;
text-align:center;
}

h1{
margin:0;
font-size:29px;
letter-spacing:1px;
}

.subtitle{
margin-top:5px;
font-size:11px;
letter-spacing:2px;
color:#718098;
}

.panel{
margin-top:17px;
padding:18px;
border-radius:22px;
background:
linear-gradient(
145deg,
#0c131e,
#06090f
);
border:1px solid #1d2b3e;
box-shadow:
0 15px 45px #00000099;
}

.status{
font-weight:800;
letter-spacing:1px;
color:#78869a;
}

.status.active{
color:#42e6a4;
}

.status-dot{
display:inline-block;
width:9px;
height:9px;
margin-right:7px;
border-radius:50%;
background:#647286;
}

.status.active .status-dot{
background:#42e6a4;
box-shadow:
0 0 14px #42e6a4;
}

.message{
min-height:18px;
margin-top:7px;
font-size:12px;
color:#8491a4;
}

.data-grid{
display:grid;
grid-template-columns:
1fr 1fr;
gap:9px;
margin-top:17px;
}

.data-box{
padding:12px;
border-radius:15px;
background:#080d15;
border:1px solid #1b2839;
}

.data-title{
font-size:9px;
letter-spacing:1px;
color:#708097;
}

.data-value{
margin-top:6px;
font-size:15px;
font-weight:800;
}

.data-small{
margin-top:4px;
font-size:10px;
color:#77869b;
}

.signal-title{
margin-top:20px;
font-size:10px;
letter-spacing:2px;
color:#8290a4;
}

.signal-percent{
margin-top:5px;
font-size:40px;
font-weight:900;
}

.signal-bar{
height:12px;
margin-top:8px;
border-radius:20px;
background:#182333;
overflow:hidden;
}

.signal-fill{
width:0%;
height:100%;
background:#42e6a4;
transition:
width .2s ease;
}

.target{
margin-top:15px;
font-size:23px;
font-weight:900;
}

.target-type{
margin-top:4px;
font-size:11px;
letter-spacing:2px;
color:#42e6a4;
}


/* SKY MAP */

.map-title{
margin-bottom:14px;
font-size:12px;
letter-spacing:2px;
color:#42e6a4;
}

.map-wrapper{
position:relative;
width:100%;
height:500px;
overflow:hidden;
border-radius:20px;
background:
radial-gradient(
circle at center,
#111d32,
#04070c 72%
);
border:1px solid #24354b;
touch-action:none;
}

#skyMap{
position:absolute;
left:0;
top:0;
width:100%;
height:100%;
}

.map-center{
position:absolute;
left:50%;
top:50%;
width:28px;
height:28px;
transform:
translate(-50%,-50%);
pointer-events:none;
z-index:5;
}

.map-center:before,
.map-center:after{
content:"";
position:absolute;
background:#42e6a4;
box-shadow:
0 0 9px #42e6a4;
}

.map-center:before{
left:0;
top:14px;
width:28px;
height:1px;
}

.map-center:after{
left:14px;
top:0;
width:1px;
height:28px;
}

.map-label{
position:absolute;
left:50%;
top:50%;
transform:
translate(-50%,22px);
font-size:9px;
color:#42e6a4;
white-space:nowrap;
pointer-events:none;
z-index:5;
}

.map-controls{
display:flex;
gap:8px;
margin-top:11px;
}

.map-controls button{
margin:0;
padding:12px 7px;
font-size:12px;
background:#111a27;
color:#cbd7e6;
border:1px solid #27364b;
}


/* DETECTION */

.object-title{
font-size:11px;
letter-spacing:2px;
color:#42e6a4;
}

.object-name{
margin-top:8px;
font-size:25px;
font-weight:900;
}

.object-type{
margin-top:4px;
font-size:11px;
letter-spacing:2px;
color:#8c9ab0;
}

.distance{
margin-top:18px;
font-size:26px;
font-weight:900;
}

.distance-label{
font-size:10px;
letter-spacing:2px;
color:#718098;
}

.difficulty{
margin-top:10px;
font-size:12px;
color:#8c9ab0;
}


/* BUTTONS */

button{
width:100%;
padding:17px;
margin-top:14px;
border-radius:16px;
border:0;
font-size:16px;
font-weight:bold;
cursor:pointer;
}

#startButton{
background:#42e6a4;
color:#06100c;
}

#stopButton{
background:#111a27;
color:#d5dfed;
border:1px solid #2a374b;
}


/* LEGEND */

.legend{
margin-top:12px;
font-size:10px;
line-height:1.9;
color:#718097;
}

.version{
margin-top:24px;
font-size:11px;
letter-spacing:2px;
color:#42e6a4;
}

</style>

</head>

<body>

<div class="app">

<h1>📡 RADIO TELESCOPE</h1>

<div class="subtitle">
REAL SKY DETECTOR — v1.2.2
</div>

<!-- RECEIVER -->

<div class="panel">

<div id="status"
class="status">

<span class="status-dot"></span>
RECEIVER STANDBY

</div>

<div id="scanStatus"
class="message">

System ready

</div>

<div class="data-grid">

<div class="data-box">

<div class="data-title">
📍 GPS
</div>

<div id="location"
class="data-value">
---
</div>

<div id="accuracy"
class="data-small">
GPS inactive
</div>

</div>

<div class="data-box">

<div class="data-title">
🕐 TIME
</div>

<div id="time"
class="data-value">
--:--:--
</div>

</div>

<div class="data-box">

<div class="data-title">
🧭 AZIMUTH
</div>

<div id="heading"
class="data-value">
---°
</div>

<div id="direction"
class="data-small">
---
</div>

</div>

<div class="data-box">

<div class="data-title">
📐 ALTITUDE
</div>

<div id="altitude"
class="data-value">
---°
</div>

</div>

</div>

<div class="signal-title">
📶 SIGNAL STRENGTH
</div>

<div id="signalPercent"
class="signal-percent">
0%
</div>

<div class="signal-bar">

<div id="signalFill"
class="signal-fill">
</div>

</div>

<div id="targetName"
class="target">
TARGET: NULL
</div>

<div id="targetType"
class="target-type">
NO SIGNAL
</div>

<div id="signalMessage"
class="message">
📻 SCANNING SKY...
</div>

</div>

<!-- SKY MAP -->

<div class="panel">

<div class="map-title">
🌌 SKY 360
</div>

<div id="mapWrapper"
class="map-wrapper">

<canvas id="skyMap">
</canvas>

<div class="map-center">
</div>

<div class="map-label">
YOUR VIEW DIRECTION
</div>

</div>

<div class="map-controls">

<button onclick="zoomMap(1.2)">
＋ ZOOM
</button>

<button onclick="zoomMap(0.8)">
− ZOOM
</button>

<button onclick="resetMap()">
RESET
</button>

</div>

<div class="legend">

⭐ STAR — large

<br>

🪐 PLANET — medium

<br>

🌌 GALAXY — smaller

<br>

🌀 NEBULA — small

<br>

☄️ COMET — smallest

<br>

🕳️ BLACK HOLE — special

</div>

</div>

<!-- CURRENT DETECTION -->

<div class="panel">

<div class="object-title">
CURRENT DETECTION
</div>

<div id="objectName"
class="object-name">
NULL
</div>

<div id="objectType"
class="object-type">
NO OBJECT DETECTED
</div>

<div id="distance"
class="distance">
---
</div>

<div class="distance-label">
DISTANCE FROM EARTH
</div>

<div id="difficulty"
class="difficulty">
Difficulty: ---
</div>

</div>

<button id="startButton"
onclick="startReceiver()">

▶ START RECEIVER

</button>

<button id="stopButton"
onclick="stopReceiver()">

■ STOP RECEIVER

</button>

<div class="version">
RADIO TELESCOPE v1.2.2 🚀
</div>

</div>

<script>


/* =====================================================
RADIO TELESCOPE v1.2.2
===================================================== */


/* =====================================================
BASIC VARIABLES
===================================================== */

let receiverActive=false;

let latitude=null;

let longitude=null;

let heading=null;

let pitch=null;

let watchID=null;

let detectionTimer=null;

let zoom=1;

let filteredHeading=null;

let filteredPitch=null;

let currentObject=null;

let currentSignal=0;


/* =====================================================
AUDIO VARIABLES

RADIO NOISE IS GENERATED
DIRECTLY BY WEB AUDIO API.

NO RADIO NOISE FILE NEEDED.
===================================================== */

let audioContext=null;

let noiseSource=null;

let noiseGain=null;

let masterGain=null;

let objectAudio=null;

let objectGain=null;


/* =====================================================
OBJECT AUDIO FILES

IMPORTANT:

PUT YOUR REAL ENGLISH FILE NAMES HERE.

EXAMPLES:

"Vega.mp3"
"Saturn.mp3"
"Andromeda.mp3"

If your file is .wav, use .wav.

If your file is .mp4, browser audio support
can be inconsistent. MP3/WAV is recommended.
===================================================== */

const AUDIO_FILES={

Moon:
"Moon.mp3",

Sun:
"Sun.mp3",

Mercury:
"Mercury.mp3",

Venus:
"Venus.mp3",

Mars:
"Mars.mp3",

Jupiter:
"Jupiter.mp3",

Saturn:
"Saturn.mp3",

Uranus:
"Uranus.mp3",

Neptune:
"Neptune.mp3",

Vega:
"Vega.mp3",

Andromeda:
"Andromeda.mp3",

Whirlpool:
"Whirlpool.mp3",

Helix:
"Helix.mp3",

CatsEye:
"CatsEye.mp3",

Crab:
"CrabNebula.mp3",

Carina:
"CarinaNebula.mp3",

M87:
"M87.mp3",

SagittariusA:
"SagittariusA.mp3",

Comet67P:
"67P.mp3"

};


/* =====================================================
CREATE RADIO NOISE

GENERATED DIGITALLY
===================================================== */

function createRadioNoise(){

if(
audioContext
)
return;


audioContext=
new(
window.AudioContext||
window.webkitAudioContext
)();


noiseGain=
audioContext.createGain();


masterGain=
audioContext.createGain();


noiseGain.gain.value=
0.75;


masterGain.gain.value=
1;


noiseGain.connect(
masterGain
);


masterGain.connect(
audioContext.destination
);


/*
Create white noise buffer
*/

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

noiseSource.loop=true;


noiseSource.connect(
noiseGain
);


noiseSource.start();

}


/* =====================================================
START AUDIO
===================================================== */

async function startAudio(){

createRadioNoise();


if(
audioContext.state===
"suspended"
){

await audioContext.resume();

}

}


/* =====================================================
OBJECT AUDIO
===================================================== */

function playObjectSound(
object
){

if(
!object||
!object.audio
)
return;


const file=
AUDIO_FILES[
object.audio
];


if(
!file
)
return;


/*
If same audio is already playing,
don't restart it.
*/

if(
objectAudio&&
objectAudio.dataset.name===
object.name
)
return;


if(
objectAudio
){

objectAudio.pause();

objectAudio.src="";

objectAudio=null;

}


objectAudio=
new Audio(
file
);


objectAudio.loop=true;

objectAudio.preload=
"auto";


objectAudio.dataset.name=
object.name;


objectGain=
audioContext.createGain();


objectGain.gain.value=0;


const source=
audioContext.createMediaElementSource(
objectAudio
);


source.connect(
objectGain
);


objectGain.connect(
masterGain
);


objectAudio
.play()
.catch(
error=>{

console.log(
"Object audio blocked:",
error
);

}
);

}


/* =====================================================
AUDIO MIX

0% SIGNAL:
FULL RADIO NOISE

100% SIGNAL:
ORIGINAL OBJECT VOLUME
MINIMUM RADIO NOISE
===================================================== */

function updateAudio(
signal
){

if(
!audioContext||
!noiseGain
)
return;


let s=
signal/100;


/*
Noise gets quieter
*/

noiseGain.gain.value=
0.75*
(
1-
s*.95
);


/*
Object becomes louder
*/

if(
objectGain
){

objectGain.gain.value=
s;

}

}


/* =====================================================
STOP AUDIO
===================================================== */

function stopAudio(){

if(
noiseSource
){

try{

noiseSource.stop();

}
catch(e){}

noiseSource=
null;

}


if(
objectAudio
){

objectAudio.pause();

objectAudio.src="";

objectAudio=null;

}


if(
audioContext
){

audioContext.close();

audioContext=null;

}


noiseGain=null;

objectGain=null;

masterGain=null;

}


/* =====================================================
OBJECT DATABASE
===================================================== */

const objects=[

{
name:"Vega",
type:"STAR",
category:"star",
ra:18.6156,
dec:38.7837,
distance:25.04,
unit:"ly",
audio:"Vega"
},

{
name:"Sirius",
type:"STAR",
category:"star",
ra:6.7525,
dec:-16.7161,
distance:8.6,
unit:"ly"
},

{
name:"Arcturus",
type:"STAR",
category:"star",
ra:14.261,
dec:19.1825,
distance:36.7,
unit:"ly"
},

{
name:"Altair",
type:"STAR",
category:"star",
ra:19.8464,
dec:8.8683,
distance:16.7,
unit:"ly"
},

{
name:"Polaris",
type:"STAR",
category:"star",
ra:2.5303,
dec:89.2641,
distance:447,
unit:"ly"
},


{
name:"Andromeda Galaxy",
type:"GALAXY",
category:"galaxy",
ra:.712,
dec:41.269,
distance:2.5e6,
unit:"ly",
audio:"Andromeda"
},

{
name:"Whirlpool Galaxy",
type:"GALAXY",
category:"galaxy",
ra:13.498,
dec:47.195,
distance:23.16e6,
unit:"ly",
audio:"Whirlpool"
},

{
name:"M87",
type:"GALAXY",
category:"galaxy",
ra:12.514,
dec:12.392,
distance:53.5e6,
unit:"ly",
audio:"M87"
},


{
name:"Helix Nebula",
type:"NEBULA",
category:"nebula",
ra:22.493,
dec:-20.837,
distance:655,
unit:"ly",
audio:"Helix"
},

{
name:"Cat's Eye Nebula",
type:"NEBULA",
category:"nebula",
ra:17.976,
dec:66.633,
distance:3300,
unit:"ly",
audio:"CatsEye"
},

{
name:"Crab Nebula",
type:"NEBULA",
category:"nebula",
ra:5.5756,
dec:22.0145,
distance:6500,
unit:"ly",
audio:"Crab"
},

{
name:"Carina Nebula",
type:"NEBULA",
category:"nebula",
ra:10.75,
dec:-59.866,
distance:7500,
unit:"ly",
audio:"Carina"
},


{
name:"Sagittarius A*",
type:"BLACK HOLE",
category:"blackhole",
ra:17.761,
dec:-29.007,
distance:26700,
unit:"ly",
audio:"SagittariusA"
},


{
name:"67P",
type:"COMET",
category:"comet",
ra:0,
dec:0,
distance:null,
unit:"km",
audio:"Comet67P"
}

];


/* =====================================================
PLANETS
===================================================== */

const planets=[

{
name:"Sun",
type:"SUN",
category:"planet",
body:"Sun",
audio:"Sun"
},

{
name:"Moon",
type:"MOON",
category:"planet",
body:"Moon",
audio:"Moon"
},

{
name:"Mercury",
type:"PLANET",
category:"planet",
body:"Mercury",
audio:"Mercury"
},

{
name:"Venus",
type:"PLANET",
category:"planet",
body:"Venus",
audio:"Venus"
},

{
name:"Mars",
type:"PLANET",
category:"planet",
body:"Mars",
audio:"Mars"
},

{
name:"Jupiter",
type:"PLANET",
category:"planet",
body:"Jupiter",
audio:"Jupiter"
},

{
name:"Saturn",
type:"PLANET",
category:"planet",
body:"Saturn",
audio:"Saturn"
},

{
name:"Uranus",
type:"PLANET",
category:"planet",
body:"Uranus",
audio:"Uranus"
},

{
name:"Neptune",
type:"PLANET",
category:"planet",
body:"Neptune",
audio:"Neptune"
}

];


/* =====================================================
CANVAS
===================================================== */

const canvas=
document.getElementById(
"skyMap"
);

const ctx=
canvas.getContext(
"2d"
);

const wrapper=
document.getElementById(
"mapWrapper"
);


/* =====================================================
TIME
===================================================== */

setInterval(
()=>{

document.getElementById(
"time"
).innerText=
new Date()
.toLocaleTimeString(
"pl-PL"
);

},
1000
);


/* =====================================================
GPS
===================================================== */

function startGPS(){

if(
!navigator.geolocation
)
return;


watchID=
navigator.geolocation.watchPosition(

position=>{

latitude=
position.coords.latitude;

longitude=
position.coords.longitude;


document.getElementById(
"location"
).innerText=

latitude.toFixed(4)
+
"°, "
+
longitude.toFixed(4)
+
"°";


document.getElementById(
"accuracy"
).innerText=

"±"
+
Math.round(
position.coords.accuracy
)
+
" m";

},

error=>{

document.getElementById(
"accuracy"
).innerText=
"GPS ERROR";

},

{

enableHighAccuracy:true,

maximumAge:1000,

timeout:10000

}

);

}


/* =====================================================
COMPASS
===================================================== */

function orientation(
event
){

let h;


if(
event.webkitCompassHeading
!==undefined
){

h=
event.webkitCompassHeading;

}

else if(
event.alpha!==null
){

h=
360-event.alpha;

}


if(
h===undefined
)
return;


h=
(h+360)%360;


if(
filteredHeading===null
){

filteredHeading=h;

}

else{

let diff=
(
h-
filteredHeading+
540
)
%360-
180;


filteredHeading+=
diff*.15;


filteredHeading=
(
filteredHeading+
360
)%360;

}


heading=
filteredHeading;


document.getElementById(
"heading"
).innerText=
Math.round(
heading
)
+
"°";


document.getElementById(
"direction"
).innerText=
directionName(
heading
);

}


/* =====================================================
MOTION
===================================================== */

function motion(
event
){

if(
!event.accelerationIncludingGravity
)
return;


let y=
event.accelerationIncludingGravity.y;

let z=
event.accelerationIncludingGravity.z;


if(
y===null||
z===null
)
return;


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
filteredPitch===null
)
filteredPitch=
angle;

else
filteredPitch+=
(
angle-
filteredPitch
)
*
.15;


pitch=
filteredPitch;


document.getElementById(
"altitude"
).innerText=
Math.round(
pitch
)
+
"°";

}


/* =====================================================
DIRECTION
===================================================== */

function directionName(
d
){

if(
d<22.5||
d>=337.5
)
return"N";

if(
d<67.5
)
return"NE";

if(
d<112.5
)
return"E";

if(
d<157.5
)
return"SE";

if(
d<202.5
)
return"S";

if(
d<247.5
)
return"SW";

if(
d<292.5
)
return"W";

return"NW";

}


/* =====================================================
SENSOR PERMISSIONS
===================================================== */

async function enableSensors(){

if(
typeof DeviceOrientationEvent
!=="undefined"&&
typeof DeviceOrientationEvent
.requestPermission
==="function"
){

try{

let permission=
await DeviceOrientationEvent
.requestPermission();


if(
permission==="granted"
){

window.addEventListener(
"deviceorientation",
orientation,
true
);

}

}
catch(e){}

}

else{

window.addEventListener(
"deviceorientation",
orientation,
true
);

}


if(
typeof DeviceMotionEvent
!=="undefined"&&
typeof DeviceMotionEvent
.requestPermission
==="function"
){

try{

let permission=
await DeviceMotionEvent
.requestPermission();


if(
permission==="granted"
){

window.addEventListener(
"devicemotion",
motion,
true
);

}

}
catch(e){}

}

else{

window.addEventListener(
"devicemotion",
motion,
true
);

}

}


/* =====================================================
STAR POSITION
===================================================== */

function calculateStar(
object
){

if(
latitude===null||
longitude===null
)
return null;


const date=
new Date();


const lst=
Astronomy.SiderealTime(
date
)+
longitude/15;


let ha=
lst-
object.ra;


while(
ha<0
)
ha+=24;


while(
ha>=24
)
ha-=24;


const H=
ha*
15*
Math.PI/
180;


const dec=
object.dec*
Math.PI/
180;


const lat=
latitude*
Math.PI/
180;


let altitude=

Math.asin(

Math.sin(dec)
*
Math.sin(lat)

+

Math.cos(dec)
*
Math.cos(lat)
*
Math.cos(H)

)
*
180/
Math.PI;


let azimuth=

Math.atan2(

Math.sin(H),

Math.cos(H)
*
Math.sin(lat)

-

Math.tan(dec)
*
Math.cos(lat)

)
*
180/
Math.PI;


azimuth=
(
azimuth+
180+
360
)%360;


return{

...object,

azimuth,

altitude

};

}


/* =====================================================
PLANET POSITION
===================================================== */

function calculatePlanet(
object
){

if(
latitude===null||
longitude===null
)
return null;


try{

const observer=
new Astronomy.Observer(
latitude,
longitude,
0
);


const date=
new Date();


const eq=
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
eq.ra,
eq.dec,
"normal"
);


let distanceKm=
eq.dist*
149597870.7;


return{

...object,

azimuth:
horizontal.azimuth,

altitude:
horizontal.altitude,

distanceKm:
distanceKm

};

}

catch(e){

return null;

}

}


/* =====================================================
ALL OBJECT POSITIONS
===================================================== */

function calculateAllObjects(){

let result=[];


objects.forEach(
object=>{

let p=
calculateStar(
object
);

if(
p
)
result.push(
p
);

}
);


planets.forEach(
object=>{

let p=
calculatePlanet(
object
);

if(
p
)
result.push(
p
);

}
);


return result;

}


/* =====================================================
DISTANCE FORMAT
===================================================== */

function formatDistance(
object
){

if(
object.distanceKm
){

let km=
object.distanceKm;


if(
km>=1e9
){

return(
(
km/1e9
).toFixed(2)
+
" billion km"
);

}


if(
km>=1e6
){

return(
(
km/1e6
).toFixed(2)
+
" million km"
);

}


return(
Math.round(km)
+
" km"
);

}


if(
object.distance
){

if(
object.distance>=1e6
){

return(
(
object.distance/1e6
).toFixed(2)
+
" million light-years"
);

}


return(
object.distance
+
" light-years"
);

}


return"Unknown";

}


/* =====================================================
MAP
===================================================== */

function resizeCanvas(){

canvas.width=
wrapper.clientWidth*
devicePixelRatio;

canvas.height=
wrapper.clientHeight*
devicePixelRatio;


canvas.style.width=
wrapper.clientWidth+
"px";

canvas.style.height=
wrapper.clientHeight+
"px";


ctx.setTransform(
devicePixelRatio,
0,
0,
devicePixelRatio,
0,
0
);

}


window.addEventListener(
"resize",
resizeCanvas
);

resizeCanvas();


/* =====================================================
OBJECT SIZE
===================================================== */

function objectSize(
category
){

if(
category==="star"
)
return 7;

if(
category==="planet"
)
return 5;

if(
category==="galaxy"
)
return 4;

if(
category==="nebula"
)
return 3;

if(
category==="comet"
)
return 2;

if(
category==="blackhole"
)
return 7;

return 4;

}


/* =====================================================
OBJECT COLOR
===================================================== */

function objectColor(
category
){

if(
category==="star"
)
return"#dbeaff";

if(
category==="planet"
)
return"#42e6a4";

if(
category==="galaxy"
)
return"#b46cff";

if(
category==="nebula"
)
return"#ff6bcf";

if(
category==="comet"
)
return"#d5f8ff";

if(
category==="blackhole"
)
return"#ff00d4";

return"#ffffff";

}


/* =====================================================
DRAW SKY MAP
===================================================== */

function drawMap(){

const w=
wrapper.clientWidth;

const h=
wrapper.clientHeight;


ctx.clearRect(
0,
0,
w,
h
);


ctx.fillStyle=
"#03050a";

ctx.fillRect(
0,
0,
w,
h
);


/* GRID */

ctx.strokeStyle=
"#142234";

ctx.lineWidth=1;


for(
let i=1;
i<6;
i++
){

let y=
h/6*i;


ctx.beginPath();

ctx.moveTo(
0,
y
);

ctx.lineTo(
w,
y
);

ctx.stroke();

}


for(
let i=1;
i<8;
i++
){

let x=
w/8*i;


ctx.beginPath();

ctx.moveTo(
x,
0
);

ctx.lineTo(
x,
h
);

ctx.stroke();

}


/* OBJECTS */

const list=
calculateAllObjects();


list.forEach(
object=>{

if(
object.altitude<0
)
return;


let deltaAz=
object.azimuth-
(
heading||
0
);


while(
deltaAz>180
)
deltaAz-=360;


while(
deltaAz<-180
)
deltaAz+=360;


let x=
w/2+
(
deltaAz/
45
)
*
w/2*
zoom;


let y=
h/2-
(
(
object.altitude-
(
pitch||
45
)
)/
30
)
*
h/2*
zoom;


if(
x<-80||
x>w+80||
y<-80||
y>h+80
)
return;


let size=
objectSize(
object.category
);


let color=
objectColor(
object.category
);


ctx.beginPath();

ctx.arc(
x,
y,
size,
0,
Math.PI*2
);


ctx.fillStyle=
color;


ctx.shadowBlur=
object.category===
"blackhole"
?
20:
10;


ctx.shadowColor=
color;

ctx.fill();

ctx.shadowBlur=0;


ctx.fillStyle=
"#d5dfed";

ctx.font=
"bold 9px Arial";

ctx.textAlign=
"center";


ctx.fillText(
object.name,
x,
y+
size+
12
);


ctx.font=
"8px Arial";

ctx.fillStyle=
"#718098";


ctx.fillText(
object.type,
x,
y+
size+
22
);

});

}


/* =====================================================
ZOOM
===================================================== */

function zoomMap(
value
){

zoom*=value;


zoom=
Math.max(
.6,
Math.min(
4,
zoom
)
);


drawMap();

}


function resetMap(){

zoom=1;

drawMap();

}


/* =====================================================
DETECTION
===================================================== */

function detectTarget(){

if(
!receiverActive||
heading===null||
pitch===null
)
return;


const list=
calculateAllObjects();


let best=null;

let bestScore=999;


list.forEach(
object=>{

if(
object.altitude<0
)
return;


let azDiff=
Math.abs(

(
object.azimuth-
heading+
540
)
%360-
180

);


let altDiff=
Math.abs(

object.altitude-
pitch

);


let score=
Math.sqrt(

azDiff*
azDiff+
altDiff*
altDiff

);


if(
score<
bestScore
){

bestScore=
score;

best=
object;

}

});


/*
Large detection field
*/

const radius=15;


if(
!best||
bestScore>
radius
){

currentObject=null;

currentSignal=0;


updateAudio(
0
);


document.getElementById(
"signalPercent"
).innerText=
"0%";


document.getElementById(
"signalFill"
).style.width=
"0%";


document.getElementById(
"targetName"
).innerText=
"TARGET: NULL";


document.getElementById(
"targetType"
).innerText=
"NO SIGNAL";


document.getElementById(
"objectName"
).innerText=
"NULL";


document.getElementById(
"objectType"
).innerText=
"NO OBJECT DETECTED";


document.getElementById(
"distance"
).innerText=
"---";


document.getElementById(
"difficulty"
).innerText=
"Difficulty: ---";


return;

}


/* SIGNAL */

let signal=
Math.round(

100*
(
1-
bestScore/
radius
)

);


signal=
Math.max(
0,
Math.min(
100,
signal
)
);


currentObject=
best;

currentSignal=
signal;


/* OBJECT AUDIO */

playObjectSound(
best
);


/* MIX */

updateAudio(
signal
);


/* UI */

document.getElementById(
"signalPercent"
).innerText=
signal+
"%";


document.getElementById(
"signalFill"
).style.width=
signal+
"%";


document.getElementById(
"targetName"
).innerText=
best.name;


document.getElementById(
"targetType"
).innerText=
best.type;


document.getElementById(
"objectName"
).innerText=
best.name;


document.getElementById(
"objectType"
).innerText=
best.type;


document.getElementById(
"distance"
).innerText=
formatDistance(
best
);


let difficulty=
signal>=80
?
"EASY"
:
signal>=50
?
"MEDIUM"
:
"HARD";


document.getElementById(
"difficulty"
).innerText=
"Difficulty: "
+
difficulty;


if(
signal>=90
){

document.getElementById(
"signalMessage"
).innerText=
"🟢 TARGET LOCKED!";

}

else if(
signal>=50
){

document.getElementById(
"signalMessage"
).innerText=
"🟡 STRONG SIGNAL — KEEP AIMING";

}

else{

document.getElementById(
"signalMessage"
).innerText=
"🟠 WEAK SIGNAL DETECTED";

}

}


/* =====================================================
START
===================================================== */

async function startReceiver(){

if(
receiverActive
)
return;


receiverActive=true;


document.getElementById(
"status"
).classList.add(
"active"
);


document.getElementById(
"status"
).innerHTML=
'<span class="status-dot"></span>RECEIVER ACTIVE';


document.getElementById(
"scanStatus"
).innerText=
"📡 Radio telescope online";


/*
IMPORTANT:

The audio context is started directly
from the START button click.

This is required by Safari/iOS.
*/

await startAudio();


startGPS();


await enableSensors();


detectionTimer=
setInterval(

()=>{

drawMap();

detectTarget();

},

500

);

}


/* =====================================================
STOP
===================================================== */

function stopReceiver(){

receiverActive=false;


if(
detectionTimer
){

clearInterval(
detectionTimer
);

detectionTimer=null;

}


if(
watchID!==null
){

navigator.geolocation
.clearWatch(
watchID
);

watchID=null;

}


stopAudio();


document.getElementById(
"status"
).classList.remove(
"active"
);


document.getElementById(
"status"
).innerHTML=
'<span class="status-dot"></span>RECEIVER STANDBY';


document.getElementById(
"targetName"
).innerText=
"TARGET: NULL";


document.getElementById(
"targetType"
).innerText=
"NO SIGNAL";


document.getElementById(
"signalPercent"
).innerText=
"0%";


document.getElementById(
"signalFill"
).style.width=
"0%";


document.getElementById(
"objectName"
).innerText=
"NULL";


document.getElementById(
"objectType"
).innerText=
"NO OBJECT DETECTED";


document.getElementById(
"distance"
).innerText=
"---";


drawMap();

}


/* =====================================================
INITIAL
===================================================== */

document.getElementById(
"time"
).innerText=
new Date()
.toLocaleTimeString(
"pl-PL"
);


drawMap();

</script>

</body>
</html>
