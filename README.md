<!DOCTYPE html>
<html lang="pl">

<head>

<meta charset="UTF-8">

<meta
name="viewport"
content="width=device-width, initial-scale=1.0"
>

<title>Radio Telescope v0.5</title>

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

    padding: 30px 20px 50px;

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

    background: #596477;

}

.active {

    color: #42e6a4;

}

.active .status-dot {

    background: #42e6a4;

    box-shadow:
        0 0 15px
        #42e6a4;

}

.data-grid {

    margin-top: 28px;

    display: grid;

    gap: 14px;

}

.data-box {

    padding: 18px;

    background: #0b1018;

    border:
        1px solid
        #202b3c;

    border-radius: 18px;

}

.data-title {

    color: #78879c;

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

    color: #8492a7;

    font-size: 12px;

}

.sensor-ok {

    color: #42e6a4;

}

.sensor-off {

    color: #ff6b6b;

}

.compass-container {

    margin:
        25px auto;

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

    color: #ff5252;

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

    background: white;

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

    background: #42e6a4;

    color: #07101d;

    box-shadow:
        0 5px 20px
        #42e6a433;

}

#stopButton {

    background: #151c28;

    color: #cbd7e9;

    border:
        1px solid
        #293448;

}

.info {

    margin-top: 22px;

    color: #69788e;

    font-size: 12px;

    line-height: 1.6;

}

.version {

    margin-top: 25px;

    color: #42e6a4;

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
MOBILE SENSOR RECEIVER
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


<!-- COMPASS VISUAL -->


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

RADIO TELESCOPE v0.5

</div>


</div>


<div class="info">

Ten projekt wykorzystuje prawdziwe sensory
smartfona: GPS, magnetometr, żyroskop
oraz akcelerometr.

<br><br>

⚠️ Aplikacja nie odbiera jeszcze
bezpośrednio fal radiowych z kosmosu.
Jest to eksperymentalny interfejs
mobilnego radioteleskopu.

</div>


</div>


<script>


// ====================================
// ZMIENNE
// ====================================

let receiverActive = false;

let watchID = null;


// ====================================
// ELEMENTY
// ====================================

const statusElement =
document.getElementById(
    "status"
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
// ORIENTACJA / KOMPAS
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


    const rounded =
    Math.round(
        heading
    );


    headingElement.innerText =
    rounded +
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
// RUCH TELEFONU
// ŻYROSKOP + AKCELEROMETR
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


            const orientationPermission =

            await
            DeviceOrientationEvent
            .requestPermission();


            if (
                orientationPermission ===
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
                "Orientation error:",
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


    // =================================
    // MOTION PERMISSION
    // =================================


    if (

        typeof DeviceMotionEvent !==
        "undefined" &&

        typeof DeviceMotionEvent
        .requestPermission ===
        "function"

    ) {


        try {


            const motionPermission =

            await
            DeviceMotionEvent
            .requestPermission();


            if (
                motionPermission ===
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
                "Motion error:",
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


    // GPS

    startGPS();


    // SENSORY

    await enableSensors();

}


// ====================================
// STOP RECEIVER
// ====================================

function stopReceiver() {


    receiverActive =
    false;


    statusElement.classList.remove(
        "active"
    );


    statusElement.innerHTML =

    '<span class="status-dot"></span>' +

    'RECEIVER STANDBY';


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
