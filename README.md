<!DOCTYPE html>

<html lang="pl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">

<title>Radio Telescope v1.2 — Signal Hunt</title>

<script src="https://cdn.jsdelivr.net/npm/astronomy-engine@2.1.19/astronomy.browser.min.js"></script>

<style>

*{
box-sizing:border-box;
}

body{
margin:0;
min-height:100vh;
background:
radial-gradient(circle at top,#18263b,#05070b 70%);
color:white;
font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Arial,sans-serif;
text-align:center;
}

.app{
width:100%;
max-width:600px;
margin:auto;
padding:28px 18px 60px;
}

h1{
margin:0;
font-size:29px;
letter-spacing:1px;
}

.subtitle{
margin-top:7px;
color:#8290a5;
font-size:11px;
letter-spacing:2px;
}

.panel{
margin-top:22px;
padding:22px;
background:linear-gradient(145deg,#101827,#080b11);
border:1px solid #273348;
border-radius:24px;
box-shadow:0 15px 45px #00000099;
}

.status{
display:flex;
justify-content:center;
align-items:center;
gap:10px;
font-weight:bold;
letter-spacing:1px;
color:#7f8da2;
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
box-shadow:0 0 15px #42e6a4;
}

.scan-status{
margin-top:15px;
min-height:25px;
color:#8ea1bb;
font-size:13px;
}

.data-grid{
margin-top:20px;
display:grid;
gap:12px;
}

.data-box{
padding:15px;
background:#0b1018;
border:1px solid #202b3c;
border-radius:17px;
}

.data-title{
color:#78879c;
font-size:10px;
letter-spacing:1px;
}

.data-value{
margin-top:7px;
font-size:20px;
font-weight:bold;
}

.data-small{
margin-top:5px;
color:#8492a7;
font-size:11px;
}

.compass-container{
margin:25px auto;
width:210px;
height:210px;
border-radius:50%;
background:radial-gradient(circle,#151e2d,#080b11);
border:3px solid #2b374b;
display:flex;
align-items:center;
justify-content:center;
box-shadow:inset 0 0 35px #000000aa;
}

.compass{
width:175px;
height:175px;
border-radius:50%;
position:relative;
transition:transform .12s linear;
}

.direction{
position:absolute;
font-weight:bold;
font-size:17px;
}

.north{
top:2px;
left:50%;
transform:translateX(-50%);
color:#ff5252;
}

.east{
right:2px;
top:50%;
transform:translateY(-50%);
}

.south{
bottom:2px;
left:50%;
transform:translateX(-50%);
}

.west{
left:2px;
top:50%;
transform:translateY(-50%);
}

.needle{
position:absolute;
width:4px;
height:68px;
left:50%;
top:19px;
transform:translateX(-50%);
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

/* =========================
SIGNAL HUNT
========================= */

.signal-title{
margin-top:10px;
font-size:12px;
letter-spacing:2px;
color:#8ea1bb;
}

.signal-percent{
margin-top:10px;
font-size:42px;
font-weight:900;
}

.signal-bar{
margin-top:12px;
height:15px;
background:#182131;
border-radius:20px;
overflow:hidden;
border:1px solid #29364b;
}

.signal-fill{
height:100%;
width:0%;
background:#42e6a4;
transition:width .2s ease;
}

.signal-message{
margin-top:12px;
font-size:13px;
font-weight:bold;
color:#8290a5;
min-height:20px;
}

.target-name{
margin-top:15px;
font-size:25px;
font-weight:bold;
}

.target-type{
margin-top:6px;
color:#8ea1bb;
font-size:12px;
}

/* =========================
RADAR
========================= */

.radar-title{
font-size:12px;
letter-spacing:2px;
color:#42e6a4;
margin-bottom:15px;
}

.radar{
width:300px;
height:300px;
max-width:90vw;
max-height:90vw;
margin:auto;
border-radius:50%;
position:relative;
overflow:hidden;
background:
radial-gradient(circle,
transparent 0 24%,
#263548 25% 25.5%,
transparent 26% 49%,
#263548 49.5% 50%,
transparent 50.5% 74%,
#263548 74.5% 75%,
transparent 75.5%
);
border:2px solid #42e6a4;
box-shadow:
0 0 20px #42e6a433,
inset 0 0 35px #00000099;
}

.radar::before{
content:"";
position:absolute;
left:50%;
top:0;
width:1px;
height:100%;
background:#263548;
}

.radar::after{
content:"";
position:absolute;
top:50%;
left:0;
width:100%;
height:1px;
background:#263548;
}

.radar-sweep{
position:absolute;
width:50%;
height:2px;
left:50%;
top:50%;
transform-origin:left center;
background:#42e6a4;
box-shadow:0 0 10px #42e6a4;
animation:radarSweep 4s linear infinite;
}

@keyframes radarSweep{
from{
transform:rotate(0deg);
}
to{
transform:rotate(360deg);
}
}

.radar-center{
position:absolute;
width:12px;
height:12px;
left:50%;
top:50%;
transform:translate(-50%,-50%);
border-radius:50%;
background:#42e6a4;
box-shadow:0 0 15px #42e6a4;
z-index:5;
}

.radar-object{
position:absolute;
width:11px;
height:11px;
border-radius:50%;
background:#ffffff;
box-shadow:0 0 10px #ffffff;
transform:translate(-50%,-50%);
z-index:4;
transition:all .3s ease;
}

.radar-object.near{
background:#ffe600;
box-shadow:0 0 15px #ffe600;
}

.radar-object.locked{
background:#42e6a4;
box-shadow:0 0 20px #42e6a4;
width:15px;
height:15px;
}

.radar-label{
position:absolute;
font-size:8px;
white-space:nowrap;
transform:translate(-50%,10px);
color:#aab8ca;
pointer-events:none;
}

.radar-legend{
margin-top:14px;
font-size:10px;
color:#718097;
}

/* =========================
IMAGE
========================= */

.object-image-container{
display:none;
margin:20px auto;
width:100%;
border-radius:18px;
overflow:hidden;
background:#05070b;
border:1px solid #273348;
}

.object-image-container.visible{
display:block;
animation:imageAppear .7s ease;
}

@keyframes imageAppear{
from{
opacity:0;
transform:scale(.96);
}
to{
opacity:1;
transform:scale(1);
}
}

#objectImage{
display:block;
width:100%;
height:auto;
max-height:300px;
object-fit:cover;
}

.image-caption{
padding:9px;
font-size:10px;
color:#7d8ca2;
}

/* =========================
DISCOVERY
========================= */

.discovery-title{
color:#42e6a4;
font-size:12px;
letter-spacing:2px;
}

.discovery-count{
margin-top:10px;
font-size:35px;
font-weight:900;
}

.discovery-list{
margin-top:15px;
max-height:230px;
overflow-y:auto;
text-align:left;
}

.discovery-item{
padding:9px;
border-bottom:1px solid #1c2737;
font-size:12px;
color:#c4d0df;
}

.discovery-item::before{
content:"✓ ";
color:#42e6a4;
font-weight:bold;
}

/* =========================
BUTTONS
========================= */

button{
width:100%;
padding:19px;
margin-top:18px;
border:none;
border-radius:17px;
font-size:17px;
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

.info{
margin-top:20px;
color:#69788e;
font-size:11px;
line-height:1.6;
}

.version{
margin-top:25px;
color:#42e6a4;
font-size:11px;
letter-spacing:2px;
}

.black-hole{
animation:rainbow 2s linear infinite;
}

@keyframes rainbow{
0%{color:#ff004c;}
20%{color:#ff8a00;}
40%{color:#ffee00;}
60%{color:#00ff88;}
80%{color:#00c8ff;}
100%{color:#ff00ff;}
}

</style>

</head>

<body>

<div class="app">

<h1>📡 RADIO TELESCOPE</h1>

<div class="subtitle">
SIGNAL HUNT — REAL-TIME SKY DETECTION
</div>

<div class="panel">

<div class="status" id="status">
<span class="status-dot"></span>
RECEIVER STANDBY
</div>

<div class="scan-status" id="scanStatus">
System ready
</div>

<div class="data-grid">

<div class="data-box">
<div class="data-title">📍 OBSERVER POSITION</div>
<div class="data-value" id="location">---</div>
<div class="data-small" id="accuracy">GPS inactive</div>
</div>

<div class="data-box">
<div class="data-title">🕐 OBSERVATION TIME</div>
<div class="data-value" id="time">--:--:--</div>
</div>

<div class="data-box">
<div class="data-title">🧭 PHONE AZIMUTH</div>
<div class="data-value" id="heading">--°</div>
<div class="data-small" id="direction">Compass inactive</div>
</div>

<div class="data-box">
<div class="data-title">📐 PHONE ALTITUDE</div>
<div class="data-value" id="altitude">--°</div>
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

<!-- SIGNAL -->

<div class="signal-title">
📶 SIGNAL STRENGTH
</div>

<div class="signal-percent" id="signalPercent">
0%
</div>

<div class="signal-bar">

<div class="signal-fill" id="signalFill"></div>

</div>

<div class="signal-message" id="signalMessage">
📻 SCANNING FOR SIGNAL...
</div>

<div class="target-name" id="targetName">
TARGET: NULL
</div>

<div class="target-type" id="targetType">
POINT RECEIVER AT THE SKY
</div>

</div>

<!-- RADAR -->

<div class="panel">

<div class="radar-title">
🧭 360° SKY RADAR
</div>

<div class="radar" id="radar">

<div class="radar-sweep"></div>

<div class="radar-center"></div>

</div>

<div class="radar-legend">
⚪ Obiekt &nbsp; 🟡 Blisko sygnału &nbsp; 🟢 Zablokowany
</div>

</div>

<!-- OBJECT -->

<div class="panel">

<div class="object-image-container" id="objectImageContainer">

<img id="objectImage" src="" alt="Astronomical object">

<div class="image-caption" id="imageCaption">
ASTRONOMICAL IMAGE
</div>

</div>

<div class="data-grid">

<div class="data-box">
<div class="data-title">📡 TARGET SIGNAL</div>
<div class="data-value" id="targetSignal">000000</div>
</div>

<div class="data-box">
<div class="data-title">🎯 TARGET AZIMUTH</div>
<div class="data-value" id="targetDirection">---</div>
</div>

<div class="data-box">
<div class="data-title">📐 TARGET ALTITUDE</div>
<div class="data-value" id="targetAltitude">---</div>
</div>

<div class="data-box">
<div class="data-title">📏 DISTANCE</div>
<div class="data-value" id="targetDistance">---</div>
</div>

<div class="data-box">
<div class="data-title">🔭 DIFFICULTY</div>
<div class="data-value" id="targetDifficulty">---</div>
</div>

</div>

</div>

<!-- DISCOVERY -->

<div class="panel">

<div class="discovery-title">
🏆 OBJECT DISCOVERY
</div>

<div class="discovery-count">

<span id="discoveryCount">0</span>
/ <span id="totalObjects">0</span>

</div>

<div class="discovery-list" id="discoveryList">

No objects discovered yet.

</div>

</div>

<button id="startButton" onclick="startReceiver()">
▶ START RECEIVER
</button>

<button id="stopButton" onclick="stopReceiver()">
■ STOP RECEIVER
</button>

<div class="version">
RADIO TELESCOPE v1.2 🚀
</div>

<div class="info">

🌍 GPS + 🧭 COMPASS + 📐 GYROSCOPE

<br><br>

📡 SIGNAL HUNT MODE

<br><br>

🎯 FIND THE SKY

<br><br>

🌌 DISCOVER THE UNIVERSE

</div>

</div>

<script>

/* ==================================================
RADIO TELESCOPE v1.2
SIGNAL HUNT
================================================== */


/* ==================================================
AUDIO
================================================== */

const AUDIO_FILES={

moon:"moon.mp3",
sun:"sun.wav",
venus:"venus.mp4",
mercury:"mercury.mp3",
mars:null,
jupiter:null,
saturn:"saturn.mp3",
uranus:"uranus.mp3",
neptune:"neptune.mp3",

vega:"vega.mp3",
sirius:"sirius.mp3",
arcturus:"arcturus.mp3",
altair:"altair.mp3",
capella:"capella.mp3",
betelgeuse:"betelgeuse.mp3",
rigel:"rigel.mp3",
deneb:"deneb.mp3",
aldebaran:"aldebaran.mp3",
polaris:"polaris.mp3",

andromeda:"andromeda.mp3",
whirlpool:"whirlpool.mp3",
m87:"m87.mp3",
sombrero:"sombrero.mp3",
milkyway:"milkyway.mp3",
perseus:"perseus.mp3",
chandra:"chandra.mp3",

helix:"helix.mp3",
crab:"crab.mp3",
carina:"carina.mp3",
eagle:"eagle.mp3",
jellyfish:"jellyfish.mp3",
catseye:"catseye.mp3",

sagittarius_a:"sagittarius_a.mp3",
v404:"v404.mp3"

};


/* ==================================================
IMAGES
================================================== */

const OBJECT_IMAGES={

sun:"https://upload.wikimedia.org/wikipedia/commons/c/c3/SOHO-EIT_Sun_edited.jpg",

moon:"https://upload.wikimedia.org/wikipedia/commons/e/e1/FullMoon2010.jpg",

mercury:"https://upload.wikimedia.org/wikipedia/commons/4/4a/Mercury_in_true_color.jpg",

venus:"https://upload.wikimedia.org/wikipedia/commons/e/e5/Venus-real_color.jpg",

mars:"https://upload.wikimedia.org/wikipedia/commons/0/02/OSIRIS_Mars_true_color.jpg",

jupiter:"https://upload.wikimedia.org/wikipedia/commons/e/e2/Jupiter.jpg",

saturn:"https://upload.wikimedia.org/wikipedia/commons/c/c7/Saturn_during_Equinox.jpg",

uranus:"https://upload.wikimedia.org/wikipedia/commons/3/3d/Uranus2.jpg",

neptune:"https://upload.wikimedia.org/wikipedia/commons/5/56/Neptune_Full.jpg",

vega:"https://upload.wikimedia.org/wikipedia/commons/1/1f/Vega_-_a0.jpg",

sirius:"https://upload.wikimedia.org/wikipedia/commons/1/1f/Sirius_A_and_B_Hubble.jpg",

arcturus:"https://upload.wikimedia.org/wikipedia/commons/2/2d/Arcturus-star.jpg",

andromeda:"https://upload.wikimedia.org/wikipedia/commons/a/ae/Andromeda_Galaxy_%28with_h-alpha%29.jpg",

whirlpool:"https://upload.wikimedia.org/wikipedia/commons/d/db/Messier51_sRGB.jpg",

m87:"https://upload.wikimedia.org/wikipedia/commons/4/4f/Black_hole_-_Messier_87_crop_max_res.jpg",

sombrero:"https://upload.wikimedia.org/wikipedia/commons/5/5f/M104_ngc4594.jpg",

milkyway:"https://upload.wikimedia.org/wikipedia/commons/0/09/Milky_Way_Galaxy.jpg",

helix:"https://upload.wikimedia.org/wikipedia/commons/4/4b/NGC7293_%28ESO-VLT%29.jpg",

crab:"https://upload.wikimedia.org/wikipedia/commons/0/00/Crab_Nebula.jpg",

carina:"https://upload.wikimedia.org/wikipedia/commons/7/7a/ESO_-_The_Carina_Nebula_%28by%29.jpg",

eagle:"https://upload.wikimedia.org/wikipedia/commons/5/5d/M16_The_Eagle_Nebula.jpg",

catseye:"https://upload.wikimedia.org/wikipedia/commons/5/59/NGC_6543.jpg",

sagittarius_a:"https://upload.wikimedia.org/wikipedia/commons/4/4f/Black_hole_-_Messier_87_crop_max_res.jpg"

};


/* ==================================================
VARIABLES
================================================== */

let receiverActive=false;

let userLatitude=null;

let userLongitude=null;

let compassHeading=null;

let filteredHeading=null;

let phoneAltitude=null;

let filteredAltitude=null;

let watchID=null;

let detectionInterval=null;

let audioContext=null;

let noiseSource=null;

let noiseGain=null;

let currentAudio=null;

let currentAudioKey=null;

let currentTarget=null;

let discovered=
JSON.parse(
localStorage.getItem(
"radioTelescopeDiscoveries"
)||"[]"
);


/* ==================================================
ELEMENTS
================================================== */

const $=id=>
document.getElementById(id);

const status=$("status");

const scanStatus=$("scanStatus");

const locationElement=$("location");

const accuracyElement=$("accuracy");

const timeElement=$("time");

const headingElement=$("heading");

const directionElement=$("direction");

const altitudeElement=$("altitude");

const compass=$("compass");

const signalPercent=$("signalPercent");

const signalFill=$("signalFill");

const signalMessage=$("signalMessage");

const targetName=$("targetName");

const targetType=$("targetType");

const targetSignal=$("targetSignal");

const targetDirection=$("targetDirection");

const targetAltitude=$("targetAltitude");

const targetDistance=$("targetDistance");

const targetDifficulty=$("targetDifficulty");

const objectImageContainer=
$("objectImageContainer");

const objectImage=
$("objectImage");

const imageCaption=
$("imageCaption");

const radar=$("radar");

const discoveryCount=
$("discoveryCount");

const totalObjects=
$("totalObjects");

const discoveryList=
$("discoveryList");


/* ==================================================
TIME
================================================== */

setInterval(
()=>{
timeElement.innerText=
new Date().toLocaleTimeString("pl-PL");
},
1000
);


/* ==================================================
DISCOVERY
================================================== */

function updateDiscoveries(){

discoveryCount.innerText=
discovered.length;

discoveryList.innerHTML="";

if(
discovered.length===0
){

discoveryList.innerText=
"No objects discovered yet.";

return;

}

discovered.forEach(
name=>{

const div=
document.createElement("div");

div.className=
"discovery-item";

div.innerText=
name;

discoveryList.appendChild(
div
);

}

);

}


/* ==================================================
OBJECTS
================================================== */

const bodies=[

{
name:"☀️ SUN",
body:"Sun",
type:"Star",
signal:100,
detectionRadius:14,
audioKey:"sun",
imageKey:"sun",
difficulty:"VERY EASY"
},

{
name:"🌙 MOON",
body:"Moon",
type:"Natural Satellite",
signal:100,
detectionRadius:14,
audioKey:"moon",
imageKey:"moon",
difficulty:"VERY EASY"
},

{
name:"☿ MERCURY",
body:"Mercury",
type:"Planet",
signal:55,
detectionRadius:12,
audioKey:"mercury",
imageKey:"mercury",
difficulty:"HARD"
},

{
name:"♀ VENUS",
body:"Venus",
type:"Planet",
signal:95,
detectionRadius:14,
audioKey:"venus",
imageKey:"venus",
difficulty:"EASY"
},

{
name:"♂ MARS",
body:"Mars",
type:"Planet",
signal:70,
detectionRadius:12,
audioKey:"mars",
imageKey:"mars",
difficulty:"MEDIUM"
},

{
name:"♃ JUPITER",
body:"Jupiter",
type:"Planet",
signal:92,
detectionRadius:13,
audioKey:"jupiter",
imageKey:"jupiter",
difficulty:"EASY"
},

{
name:"♄ SATURN",
body:"Saturn",
type:"Planet",
signal:88,
detectionRadius:13,
audioKey:"saturn",
imageKey:"saturn",
difficulty:"EASY"
},

{
name:"♅ URANUS",
body:"Uranus",
type:"Planet",
signal:55,
detectionRadius:12,
audioKey:"uranus",
imageKey:"uranus",
difficulty:"HARD"
},

{
name:"♆ NEPTUNE",
body:"Neptune",
type:"Planet",
signal:35,
detectionRadius:11,
audioKey:"neptune",
imageKey:"neptune",
difficulty:"VERY HARD"
}

];


const stars=[

{
name:"⭐ VEGA",
type:"Star",
ra:18.6156,
dec:38.7837,
distance:25,
signal:90,
detectionRadius:15,
audioKey:"vega",
imageKey:"vega",
difficulty:"EASY"
},

{
name:"⭐ SIRIUS",
type:"Star",
ra:6.7525,
dec:-16.7161,
distance:8.6,
signal:100,
detectionRadius:15,
audioKey:"sirius",
imageKey:"sirius",
difficulty:"VERY EASY"
},

{
name:"⭐ ARCTURUS",
type:"Star",
ra:14.261,
dec:19.1825,
distance:36.7,
signal:96,
detectionRadius:15,
audioKey:"arcturus",
imageKey:"arcturus",
difficulty:"EASY"
},

{
name:"⭐ ALTAIR",
type:"Star",
ra:19.8464,
dec:8.8683,
distance:16.7,
signal:94,
detectionRadius:15,
audioKey:"altair",
difficulty:"EASY"
},

{
name:"⭐ CAPELLA",
type:"Star",
ra:5.2782,
dec:45.998,
distance:42.9,
signal:95,
detectionRadius:15,
audioKey:"capella",
difficulty:"EASY"
},

{
name:"⭐ BETELGEUSE",
type:"Star",
ra:5.9195,
dec:7.4071,
distance:642,
signal:90,
detectionRadius:15,
audioKey:"betelgeuse",
difficulty:"MEDIUM"
}

];


const deepSky=[

{
name:"🌌 M31 — ANDROMEDA",
type:"Galaxy",
ra:.712,
dec:41.269,
distanceLabel:"2.54 million light years",
signal:80,
detectionRadius:12,
audioKey:"andromeda",
imageKey:"andromeda",
difficulty:"EASY"
},

{
name:"🌀 M51 — WHIRLPOOL",
type:"Galaxy",
ra:13.498,
dec:47.195,
distanceLabel:"23 million light years",
signal:50,
detectionRadius:11,
audioKey:"whirlpool",
imageKey:"whirlpool",
difficulty:"HARD"
},

{
name:"🌌 M87",
type:"Galaxy",
ra:12.514,
dec:12.392,
distanceLabel:"53.5 million light years",
signal:40,
detectionRadius:10,
audioKey:"m87",
imageKey:"m87",
difficulty:"VERY HARD"
},

{
name:"💫 HELIX NEBULA",
type:"Nebula",
ra:22.493,
dec:-20.837,
distanceLabel:"655 light years",
signal:70,
detectionRadius:11,
audioKey:"helix",
imageKey:"helix",
difficulty:"HARD"
},

{
name:"👁️ CAT'S EYE NEBULA",
type:"Nebula",
ra:17.976,
dec:66.633,
distanceLabel:"3 300 light years",
signal:70,
detectionRadius:10,
audioKey:"catseye",
imageKey:"catseye",
difficulty:"HARD"
},

{
name:"🕳️ SAGITTARIUS A*",
type:"Supermassive Black Hole",
ra:17.761,
dec:-29.007,
distanceLabel:"26 000 light years",
signal:88,
detectionRadius:8,
audioKey:"sagittarius_a",
imageKey:"sagittarius_a",
difficulty:"VERY HARD",
blackHole:true
}

];


const allObjects=
[
...bodies,
...stars,
...deepSky
];

totalObjects.innerText=
allObjects.length;

updateDiscoveries();


/* ==================================================
GPS
================================================== */

function startGPS(){

if(
!navigator.geolocation
){

return;

}

watchID=
navigator.geolocation.watchPosition(

position=>{

userLatitude=
position.coords.latitude;

userLongitude=
position.coords.longitude;

locationElement.innerText=
userLatitude.toFixed(4)
+"°, "
+
userLongitude.toFixed(4)
+"°";

accuracyElement.innerText=
"GPS ±"+
Math.round(
position.coords.accuracy
)+" m";

},

error=>{

console.log(error);

},

{
enableHighAccuracy:true,
maximumAge:1000,
timeout:10000
}

);

}


/* ==================================================
COMPASS
================================================== */

function angleDiff(a,b){

return Math.abs(
(a-b+540)%360-180
);

}


function getDirection(degrees){

if(
degrees<22.5||
degrees>=337.5
)return"N";

if(degrees<67.5)return"NE";

if(degrees<112.5)return"E";

if(degrees<157.5)return"SE";

if(degrees<202.5)return"S";

if(degrees<247.5)return"SW";

if(degrees<292.5)return"W";

return"NW";

}


function orientation(event){

let heading;

if(
event.webkitCompassHeading
!==undefined
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
heading===undefined
)return;

heading=
(heading+360)%360;

if(
filteredHeading===null
){

filteredHeading=
heading;

}

else{

let diff=
(heading-filteredHeading+540)%360-180;

filteredHeading=
(
filteredHeading+
diff*.15+
360
)%360;

}

compassHeading=
filteredHeading;

headingElement.innerText=
Math.round(
filteredHeading
)+"°";

directionElement.innerText=
getDirection(
filteredHeading
);

compass.style.transform=
"rotate("+
(-filteredHeading)
+"deg)";

}


/* ==================================================
MOTION
================================================== */

function motion(event){

if(
!event.accelerationIncludingGravity
)return;

const y=
event.accelerationIncludingGravity.y;

const z=
event.accelerationIncludingGravity.z;

if(
y===null||
z===null
)return;

let angle=
Math.atan2(-y,z)
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
)*.15;

}

phoneAltitude=
filteredAltitude;

altitudeElement.innerText=
Math.round(
phoneAltitude
)+"°";

}


/* ==================================================
PERMISSIONS
================================================== */

async function enableSensors(){

if(
typeof DeviceOrientationEvent!=="undefined"&&
typeof DeviceOrientationEvent.requestPermission==="function"
){

try{

const p=
await DeviceOrientationEvent.requestPermission();

if(
p==="granted"
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
typeof DeviceMotionEvent!=="undefined"&&
typeof DeviceMotionEvent.requestPermission==="function"
){

try{

const p=
await DeviceMotionEvent.requestPermission();

if(
p==="granted"
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


/* ==================================================
POSITION
================================================== */

function starPosition(object){

const date=
new Date();

const observer=
new Astronomy.Observer(
userLatitude,
userLongitude,
0
);

const eq=
Astronomy.Equator(
"Sun",
date,
observer,
true,
true
);

const lst=
Astronomy.SiderealTime(date)
+
userLongitude/15;

let ha=
lst-
object.ra;

if(ha<0)ha+=24;

const haRad=
ha*15*Math.PI/180;

const dec=
object.dec*
Math.PI/
180;

const lat=
userLatitude*
Math.PI/
180;

const altitude=
Math.asin(
Math.sin(dec)*
Math.sin(lat)
+
Math.cos(dec)*
Math.cos(lat)*
Math.cos(haRad)
)
*
180/
Math.PI;

let azimuth=
Math.atan2(
Math.sin(haRad),
Math.cos(haRad)*
Math.sin(lat)
-
Math.tan(dec)*
Math.cos(lat)
)
*
180/
Math.PI;

azimuth=
(azimuth+180+360)%360;

return{
...object,
azimuth,
altitude
};

}


function getPositions(){

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

let result=[];


/* PLANETS */

bodies.forEach(
object=>{

try{

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

result.push({

...object,

azimuth:
horizontal.azimuth,

altitude:
horizontal.altitude

});

}
catch(e){}

}
);


/* STARS + DEEP SKY */

stars.forEach(
object=>
result.push(
starPosition(object)
)
);

deepSky.forEach(
object=>
result.push(
starPosition(object)
)
);

return result;

}


/* ==================================================
RADAR
================================================== */

function updateRadar(objects,best){

document
.querySelectorAll(
".radar-object"
)
.forEach(
el=>el.remove()
);

objects.forEach(
object=>{

if(
object.altitude<0
)return;

const az=
object.azimuth;

const alt=
object.altitude;

const radius=
Math.min(
1,
Math.max(
0,
alt/90
)
);

const angle=
(az-compassHeading)
*
Math.PI/
180;

const x=
50+
Math.sin(angle)
*
radius*
45;

const y=
50-
Math.cos(angle)
*
radius*
45;

const dot=
document.createElement(
"div"
);

dot.className=
"radar-object";

if(
best&&
best.name===
object.name
){

dot.classList.add(
"locked"
);

}

else if(
object.altitude>0
){

dot.classList.add(
"near"
);

}

dot.style.left=
x+"%";

dot.style.top=
y+"%";

dot.title=
object.name;

radar.appendChild(
dot
);

}
);

}


/* ==================================================
DETECTION
================================================== */

function detect(){

if(
!receiverActive||
compassHeading===null||
phoneAltitude===null
){

return;

}

const objects=
getPositions();

let best=null;

let bestScore=Infinity;

objects.forEach(
object=>{

if(
object.altitude<0
)return;

const azDiff=
angleDiff(
compassHeading,
object.azimuth
);

const altDiff=
Math.abs(
phoneAltitude-
object.altitude
);

const radius=
object.detectionRadius;

const score=
Math.sqrt(
azDiff*azDiff+
altDiff*altDiff
);

if(
azDiff<=radius&&
altDiff<=radius&&
score<bestScore
){

bestScore=
score;

best=object;

}

}
);


/* RADAR */

updateRadar(
objects,
best
);


if(!best){

signalPercent.innerText=
"0%";

signalFill.style.width=
"0%";

signalMessage.innerText=
"📻 SCANNING FOR SIGNAL...";

targetName.innerText=
"TARGET: NULL";

targetType.innerText=
"POINT RECEIVER AT THE SKY";

objectImageContainer
.classList
.remove(
"visible"
);

return;

}


/* SIGNAL */

const radius=
best.detectionRadius;

const azDiff=
angleDiff(
compassHeading,
best.azimuth
);

const altDiff=
Math.abs(
phoneAltitude-
best.altitude
);

const distance=
Math.sqrt(
azDiff*azDiff+
altDiff*altDiff
);

const alignment=
Math.max(
0,
1-distance/
(radius*
1.414)
);

const signal=
Math.round(
best.signal*
alignment
);


signalPercent.innerText=
signal+"%";

signalFill.style.width=
signal+"%";

targetName.innerText=
best.name;

targetType.innerText=
best.type;


/* SIGNAL MESSAGE */

if(
signal>=90
){

signalMessage.innerText=
"🟢 TARGET LOCKED — MAXIMUM SIGNAL";

}

else if(
signal>=60
){

signalMessage.innerText=
"🟡 STRONG SIGNAL — KEEP AIMING";

}

else if(
signal>=25
){

signalMessage.innerText=
"🟠 WEAK SIGNAL DETECTED — SEARCHING";

}

else{

signalMessage.innerText=
"🔴 VERY WEAK SIGNAL";

}


/* TARGET INFO */

targetSignal.innerText=
signal+"%";

targetDirection.innerText=
best.azimuth.toFixed(1)
+"°";

targetAltitude.innerText=
best.altitude.toFixed(1)
+"°";

targetDistance.innerText=
best.distanceLabel||
(
best.distance?
best.distance+
" light years"
:"---"
);

targetDifficulty.innerText=
best.difficulty;


/* IMAGE */

if(
best.imageKey&&
OBJECT_IMAGES[
best.imageKey
]
){

objectImage.src=
OBJECT_IMAGES[
best.imageKey
];

objectImageContainer
.classList
.add(
"visible"
);

imageCaption.innerText=
"🖼️ "+
best.name;

}


/* DISCOVERY */

if(
signal>=80
){

if(
!discovered.includes(
best.name
)
){

discovered.push(
best.name
);

localStorage.setItem(
"radioTelescopeDiscoveries",
JSON.stringify(
discovered
)
);

updateDiscoveries();

scanStatus.innerText=
"🏆 NEW DISCOVERY: "+
best.name;

}

}

}


/* ==================================================
START
================================================== */

async function startReceiver(){

if(
receiverActive
)return;

receiverActive=
true;

status.classList.add(
"active"
);

status.innerHTML=
'<span class="status-dot"></span>RECEIVER ACTIVE';

scanStatus.innerText=
"📡 INITIALIZING SIGNAL HUNT...";

startGPS();

await enableSensors();

detectionInterval=
setInterval(
detect,
500
);

}


/* ==================================================
STOP
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

if(
watchID!==null
){

navigator.geolocation.clearWatch(
watchID
);

watchID=
null;

}

status.classList.remove(
"active"
);

status.innerHTML=
'<span class="status-dot"></span>RECEIVER STANDBY';

scanStatus.innerText=
"System ready";

signalPercent.innerText=
"0%";

signalFill.style.width=
"0%";

signalMessage.innerText=
"📻 SCANNING FOR SIGNAL...";

targetName.innerText=
"TARGET: NULL";

targetType.innerText=
"POINT RECEIVER AT THE SKY";

objectImageContainer
.classList
.remove(
"visible"
);

document
.querySelectorAll(
".radar-object"
)
.forEach(
el=>el.remove()
);

}


/* ==================================================
INITIAL
================================================== */

updateDiscoveries();

timeElement.innerText=
new Date().toLocaleTimeString(
"pl-PL"
);

</script>

</body>
</html>
