<!DOCTYPE html>
<html lang="pl">

<head>

<meta charset="UTF-8">

<meta
name="viewport"
content="width=device-width, initial-scale=1.0"
>

<title>Radio Telescope v0.6</title>


<style>

* {
    box-sizing: border-box;
}


body {

    margin: 0;

    min-height: 100vh;

    background:
        radial-gradient(
            circle at top,
            #111b2b,
            #05070b 70%
        );

    color: white;

    font-family:
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        Arial,
        sans-serif;

    text-align: center;

}


.app {

    max-width: 520px;

    margin: auto;

    padding:
        30px
        20px
        50px;

}


h1 {

    margin: 0;

    font-size: 29px;

    letter-spacing: 1px;

}


.subtitle {

    margin-top: 8px;

    color: #8290a5;

    font-size: 12px;

    letter-spacing: 2px;

}


.receiver-panel {

    margin-top: 30px;

    padding: 25px;

    background:

        linear-gradient(
            145deg,
            #0f1622,
            #080b11
        );

    border:
        1px solid
        #273348;

    border-radius: 25px;

    box-shadow:
        0 15px 45px
        #00000099;

}


.status {

    display: flex;

    justify-content: center;

    align-items: center;

    gap: 10px;

    color: #7f8da2;

    font-weight: bold;

    letter-spacing: 1px;

}


.status-dot {

    width: 10px;

    height: 10px;

    border-radius: 50%;

    background:
        #596477;

}


.active {

    color:
        #42e6a4;

}


.active .status-dot {

    background:
        #42e6a4;

    box-shadow:
        0 0 15px
        #42e6a4;

}


.scan-status {

    margin-top: 18px;

    min-height: 24px;

    color:
        #8ea1bb;

    font-size: 13px;

    letter-spacing: 1px;

}


.scan-animation {

    margin:
        18px
        auto;

    width: 100%;

    height: 5px;

    background:
        #182131;

    border-radius: 10px;

    overflow: hidden;

    display: none;

}


.scan-bar {

    height: 100%;

    width: 0%;

    background:
        #42e6a4;

    border-radius: 10px;

    box-shadow:
        0 0 15px
        #42e6a4;

    transition:
        width
        0.2s
        linear;

}


.data-grid {

    margin-top: 28px;

    display: grid;

    gap: 14px;

}


.data-box {

    padding: 18px;

    background:
        #0b1018;

    border:
        1px solid
        #202b3c;

    border-radius: 18px;

}


.data-title {

    color:
        #78879c;

    font-size: 11px;

    letter-spacing: 1px;

    margin-bottom: 9px;

}


.data-value {

    font-size: 21px;

    font-weight: bold;

}


.data-small {

    margin-top: 6px;

    color:
        #8492a7;

    font-size: 12px;

}


.sensor-ok {

    color:
        #42e6a4;

}


.compass-container {

    margin:
        25px
        auto;

    width: 220px;

    height: 220px;

    border-radius: 50%;

    background:

        radial-gradient(
            circle,
            #151e2d,
            #080b11
        );

    border:
        3px solid
        #2b374b;

    display: flex;

    align-items: center;

    justify-content: center;

    box-shadow:

        inset
        0 0 35px
        #000000aa,

        0 0 25px
        #00000066;

}


.compass {

    width: 180px;

    height: 180px;

    border-radius: 50%;

    position: relative;

    transition:
        transform
        0.12s
        linear;

}


.direction {

    position: absolute;

    font-weight: bold;

    font-size: 18px;

}


.north {

    top: 3px;

    left: 50%;

    transform:
        translateX(-50%);

    color:
        #ff5252;

}


.east {

    right: 3px;

    top: 50%;

    transform:
        translateY(-50%);

}


.south {

    bottom: 3px;

    left: 50%;

    transform:
        translateX(-50%);

}


.west {

    left: 3px;

    top: 50%;

    transform:
        translateY(-50%);

}


.needle {

    position: absolute;

    width: 4px;

    height: 70px;

    left: 50%;

    top: 20px;

    transform:
        translateX(-50%);

    transform-origin:
        50%
        70px;

    background:

        linear-gradient(
            to bottom,
            #ff3b3b 50%,
            white 50%
        );

    border-radius: 5px;

    box-shadow:
        0 0 12px
        #ff3b3b88;

}


.center {

    position: absolute;

    width: 18px;

    height: 18px;

    border-radius: 50%;

    background:
        white;

    left: 50%;

    top: 50%;

    transform:
        translate(
            -50%,
            -50%
        );

    box-shadow:
        0 0 12px
        white;

}


.audio-status {

    margin-top: 15px;

    color:
        #68788e;

    font-size: 12px;

}


button {

    width: 100%;

    padding: 20px;

    margin-top: 20px;

    border: none;

    border-radius: 18px;

    font-size: 18px;

    font-weight: bold;

    cursor: pointer;

}


#startButton {

    background:
        #42e6a4;

    color:
        #07101d;

    box-shadow:
        0 5px 20px
        #42e6a433;

}


#stopButton {

    background:
        #151c28;

    color:
        #cbd7e9;

    border:
        1px solid
        #293448;

}


.info {

    margin-top: 22px;

    color:
        #69788e;

    font-size: 12px;

    line-height: 1.6;

}


.version {

    margin-top: 25px;

    color:
        #42e6a4;

    font-size: 11px;

    letter-spacing: 2px;

}

</style>

</head>


<body>


<div class="app">


<h1>
📡 RADIO TELESCOPE
</h1>


<div class="subtitle">
MOBILE SKY SCANNER
</div>


<div class="receiver-panel">


<div
class="status"
id="status"
>

<span
class="status-dot"
></span>

RECEIVER STANDBY

</div>


<div
class="scan-status"
id="scanStatus"
>

System ready

</div>


<div
class="scan-animation"
id="scanAnimation"
>

<div
class="scan-bar"
id="scanBar"
></div>

</div>


<div class="data-grid">


<!-- GPS -->


<div class="data-box">

<div class="data-title">

📍 USER POSITION

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


<!-- TIME -->


<div class="data-box">

<div class="data-title">

🕐 LOCAL TIME

</div>


<div
class="data-value"
id="time"
>

--:--:--

</div>

</div>


<!-- COMPASS -->


<div class="data-box">

<div class="data-title">

🧭 MAGNETOMETER / COMPASS

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


<!-- GYROSCOPE -->


<div class="data-box">

<div class="data-title">

🔄 GYROSCOPE

</div>


<div
class="data-value"
id="rotation"
>

X: --° | Y: --° | Z: --°

</div>


<div
class="data-small"
id="gyroStatus"
>

Gyroscope inactive

</div>

</div>


<!-- ACCELEROMETER -->


<div class="data-box">

<div class="data-title">

📐 ACCELEROMETER / TILT

</div>


<div
class="data-value"
id="acceleration"
>

X: -- | Y: -- | Z: --

</div>


<div
class="data-small"
id="accelStatus"
>

Accelerometer inactive

</div>

</div>


</div>


<!-- COMPASS -->


<div class="compass-container">


<div
class="compass"
id="compass"
>


<div
class="direction north"
>
N
</div>


<div
class="direction east"
>
E
</div>


<div
class="direction south"
>
S
</div>


<div
class="direction west"
>
W
</div>


<div class="needle"></div>


<div class="center"></div>


</div>


</div>


<div
class="audio-status"
id="audioStatus"
>

🔇 Radio receiver offline

</div>


<button
id="startButton"
onclick="startReceiver()"
>

📡 START RECEIVER

</button>


<button
id="stopButton"
onclick="stopReceiver()"
>

■ STOP RECEIVER

</button>


<div class="version">

RADIO TELESCOPE v0.6

</div>


</div>


<div class="info">

🌌 Sky Scanner

<br><br>

System wykorzystuje sensory smartfona
do określenia pozycji i orientacji urządzenia.

<br><br>

🔊 Radio Noise Generator aktywny podczas odbioru.

</div>


</div>


<script>


// ====================================
// ZMIENNE
// ====================================


let receiverActive =
false;


let watchID =
null;


let audioContext =
null;


let noiseSource =
null;


let noiseGain =
null;


let scanTimer =
null;


// ====================================
// ELEMENTY
// ====================================


const statusElement =
document.getElementById(
    "status"
);


const scanStatus =
document.getElementById(
    "scanStatus"
);


const scanAnimation =
document.getElementById(
    "scanAnimation"
);


const scanBar =
document.getElementById(
    "scanBar"
);


const locationElement =
document.getElementById(
    "location"
);


const accuracyElement =
document.getElementById(
    "accuracy"
);


const timeElement =
document.getElementById(
    "time"
);


const headingElement =
document.getElementById(
    "heading"
);


const directionElement =
document.getElementById(
    "direction"
);


const rotationElement =
document.getElementById(
    "rotation"
);


const accelerationElement =
document.getElementById(
    "acceleration"
);


const gyroStatus =
document.getElementById(
    "gyroStatus"
);


const accelStatus =
document.getElementById(
    "accelStatus"
);


const compassElement =
document.getElementById(
    "compass"
);


const audioStatus =
document.getElementById(
    "audioStatus"
);


// ====================================
// CZAS
// ====================================


function updateTime() {

    const now =
    new Date();

    timeElement.innerText =
    now.toLocaleTimeString(
        "pl-PL"
    );

}


setInterval(
    updateTime,
    1000
);


updateTime();


// ====================================
// RADIO NOISE
// ====================================


function startRadioNoise() {


    if (
        audioContext
    )
        return;


    const AudioContext =
    window.AudioContext ||
    window.webkitAudioContext;


    audioContext =
    new AudioContext();


    const bufferSize =
    audioContext.sampleRate * 2;


    const buffer =
    audioContext.createBuffer(
        1,
        bufferSize,
        audioContext.sampleRate
    );


    const data =
    buffer.getChannelData(0);


    for (
        let i = 0;
        i < bufferSize;
        i++
    ) {


        data[i] =
        Math.random() * 2 - 1;

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


    noiseSource.connect(
        noiseGain
    );


    noiseGain.connect(
        audioContext.destination
    );


    noiseSource.start();


    audioStatus.innerText =
    "🔊 RADIO RECEIVER — LISTENING";


    audioStatus.style.color =
    "#42e6a4";

}


// ====================================
// STOP RADIO
// ====================================


function stopRadioNoise() {


    if (
        noiseSource
    ) {


        try {

            noiseSource.stop();

        }

        catch(error) {}

    }


    noiseSource =
    null;


    noiseGain =
    null;


    if (
        audioContext
    ) {


        audioContext.close();

    }


    audioContext =
    null;


    audioStatus.innerText =
    "🔇 Radio receiver offline";


    audioStatus.style.color =
    "#68788e";

}


// ====================================
// SKY SCAN
// ====================================


function startSkyScan() {


    scanAnimation.style.display =
    "block";


    scanBar.style.width =
    "0%";


    scanStatus.innerText =
    "INITIALIZING SKY SCAN...";


    let progress =
    0;


    scanTimer =
    setInterval(

        function() {


            progress +=
            2;


            scanBar.style.width =
            progress + "%";


            if (
                progress === 20
            ) {


                scanStatus.innerText =
                "LOCKING GPS POSITION...";

            }


            if (
                progress === 40
            ) {


                scanStatus.innerText =
                "CALIBRATING COMPASS...";

            }


            if (
                progress === 60
            ) {


                scanStatus.innerText =
                "READING DEVICE ORIENTATION...";

            }


            if (
                progress === 80
            ) {


                scanStatus.innerText =
                "SCANNING CELESTIAL DATABASE...";

            }


            if (
                progress >= 100
            ) {


                clearInterval(
                    scanTimer
                );


                scanStatus.innerText =
                "🌌 CELESTIAL DATABASE READY";


                startRadioNoise();


            }


        },

        50

    );

}


// ====================================
// KIERUNEK
// ====================================


function getDirection(
    degrees
) {


    if (
        degrees >= 337.5 ||
        degrees < 22.5
    )

        return "Północ (N)";


    if (
        degrees < 67.5
    )

        return "Północny wschód (NE)";


    if (
        degrees < 112.5
    )

        return "Wschód (E)";


    if (
        degrees < 157.5
    )

        return "Południowy wschód (SE)";


    if (
        degrees < 202.5
    )

        return "Południe (S)";


    if (
        degrees < 247.5
    )

        return "Południowy zachód (SW)";


    if (
        degrees < 292.5
    )

        return "Zachód (W)";


    return "Północny zachód (NW)";

}


// ====================================
// KOMPAS
// ====================================


function handleOrientation(
    event
) {


    let heading;


    if (
        event.webkitCompassHeading !==
        undefined
    ) {


        heading =
        event.webkitCompassHeading;


    }


    else if (
        event.alpha !== null
    ) {


        heading =
        360 -
        event.alpha;

    }


    if (
        heading === undefined
    )

        return;


    heading =
    (
        heading +
        360
    ) % 360;


    headingElement.innerText =

    Math.round(
        heading
    ) +

    "°";


    directionElement.innerText =

    getDirection(
        heading
    );


    compassElement.style.transform =

    "rotate(" +

    (-heading) +

    "deg)";

}


// ====================================
// GYRO + ACCELEROMETER
// ====================================


function handleMotion(
    event
) {


    const rotationRate =
    event.rotationRate;


    const acceleration =
    event.accelerationIncludingGravity;


    if (
        rotationRate
    ) {


        const alpha =
        rotationRate.alpha || 0;


        const beta =
        rotationRate.beta || 0;


        const gamma =
        rotationRate.gamma || 0;


        rotationElement.innerText =

        "X: " +
        beta.toFixed(1) +

        "° | Y: " +
        gamma.toFixed(1) +

        "° | Z: " +
        alpha.toFixed(1) +

        "°";


        gyroStatus.innerText =
        "Gyroscope active";


        gyroStatus.className =
        "data-small sensor-ok";

    }


    if (
        acceleration
    ) {


        const x =
        acceleration.x || 0;


        const y =
        acceleration.y || 0;


        const z =
        acceleration.z || 0;


        accelerationElement.innerText =

        "X: " +
        x.toFixed(2) +

        " | Y: " +
        y.toFixed(2) +

        " | Z: " +
        z.toFixed(2);


        accelStatus.innerText =
        "Accelerometer active";


        accelStatus.className =
        "data-small sensor-ok";

    }

}


// ====================================
// GPS
// ====================================


function startGPS() {


    if (
        !navigator.geolocation
    ) {


        locationElement.innerText =
        "GPS unavailable";


        return;

    }


    watchID =

    navigator.geolocation.watchPosition(

        function(position) {


            const latitude =
            position.coords.latitude;


            const longitude =
            position.coords.longitude;


            const accuracy =
            position.coords.accuracy;


            locationElement.innerText =

            latitude.toFixed(6) +

            "°, " +

            longitude.toFixed(6) +

            "°";


            accuracyElement.innerText =

            "Accuracy: ±" +

            Math.round(
                accuracy
            ) +

            " m";


        },


        function(error) {


            locationElement.innerText =
            "GPS permission denied";


            accuracyElement.innerText =
            "Unable to get location";


        },


        {

            enableHighAccuracy:
            true,

            maximumAge:
            1000,

            timeout:
            10000

        }

    );

}


// ====================================
// SENSOR PERMISSIONS
// ====================================


async function enableSensors() {


    if (

        typeof DeviceOrientationEvent !==
        "undefined" &&

        typeof DeviceOrientationEvent
        .requestPermission ===
        "function"

    ) {


        try {


            const permission =

            await
            DeviceOrientationEvent
            .requestPermission();


            if (
                permission ===
                "granted"
            ) {


                window.addEventListener(

                    "deviceorientation",

                    handleOrientation,

                    true

                );

            }


        }

        catch(error) {


            console.error(
                error
            );

        }

    }


    else {


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


    if (

        typeof DeviceMotionEvent !==
        "undefined" &&

        typeof DeviceMotionEvent
        .requestPermission ===
        "function"

    ) {


        try {


            const permission =

            await
            DeviceMotionEvent
            .requestPermission();


            if (
                permission ===
                "granted"
            ) {


                window.addEventListener(

                    "devicemotion",

                    handleMotion,

                    true

                );

            }


        }

        catch(error) {


            console.error(
                error
            );

        }

    }


    else {


        window.addEventListener(

            "devicemotion",

            handleMotion,

            true

        );

    }

}


// ====================================
// START RECEIVER
// ====================================


async function startReceiver() {


    if (
        receiverActive
    )
        return;


    receiverActive =
    true;


    statusElement.classList.add(
        "active"
    );


    statusElement.innerHTML =

    '<span class="status-dot"></span>' +

    'RECEIVER ACTIVE';


    startGPS();


    await enableSensors();


    startSkyScan();

}


// ====================================
// STOP RECEIVER
// ====================================


function stopReceiver() {


    receiverActive =
    false;


    clearInterval(
        scanTimer
    );


    scanTimer =
    null;


    stopRadioNoise();


    statusElement.classList.remove(
        "active"
    );


    statusElement.innerHTML =

    '<span class="status-dot"></span>' +

    'RECEIVER STANDBY';


    scanAnimation.style.display =
    "none";


    scanBar.style.width =
    "0%";


    scanStatus.innerText =
    "System ready";


    if (
        watchID !== null
    ) {


        navigator.geolocation
        .clearWatch(
            watchID
        );


        watchID =
        null;

    }


    locationElement.innerText =
    "---";


    accuracyElement.innerText =
    "GPS inactive";


    headingElement.innerText =
    "--°";


    directionElement.innerText =
    "Compass inactive";


    rotationElement.innerText =
    "X: --° | Y: --° | Z: --°";


    accelerationElement.innerText =
    "X: -- | Y: -- | Z: --";


    gyroStatus.innerText =
    "Gyroscope inactive";


    accelStatus.innerText =
    "Accelerometer inactive";

}

</script>


</body>

</html>
