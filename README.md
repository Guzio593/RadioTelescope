<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Radio Telescope – Jupiter</title>

    <style>
        body {
            margin: 0;
            background: #05070b;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
        }

        .app {
            max-width: 500px;
            margin: auto;
            padding: 30px 20px;
        }

        h1 {
            font-size: 28px;
        }

        .subtitle {
            color: #8995a8;
            font-size: 13px;
        }

        .jupiter {
            width: 200px;
            height: 200px;
            margin: 40px auto 20px;

            border-radius: 50%;

            background:
                repeating-linear-gradient(
                    0deg,
                    #76513a 0px,
                    #c89d72 15px,
                    #e2c09a 30px,
                    #9a6c4a 45px
                );

            box-shadow:
                inset -30px -15px 40px #000000aa,
                0 0 50px #b87b3d55;
        }

        .status {
            margin: 20px 0;
            color: #42e6a4;
            font-weight: bold;
        }

        button {
            width: 100%;
            padding: 20px;
            margin-top: 15px;

            border: none;
            border-radius: 18px;

            font-size: 18px;
            font-weight: bold;

            background: #e0e8f7;
            color: #07101d;
        }

        .compass-container {
            margin: 35px auto 20px;
            width: 220px;
            height: 220px;

            border-radius: 50%;

            background: #0d121b;
            border: 3px solid #293448;

            position: relative;

            display: flex;
            align-items: center;
            justify-content: center;

            box-shadow:
                0 0 30px #00000088,
                inset 0 0 30px #00000088;
        }

        .compass {
            width: 180px;
            height: 180px;

            border-radius: 50%;

            position: relative;

            transition: transform 0.15s ease-out;
        }

        .direction {
            position: absolute;
            font-weight: bold;
            font-size: 18px;
        }

        .north {
            top: 5px;
            left: 50%;
            transform: translateX(-50%);
            color: #ff5252;
        }

        .east {
            right: 5px;
            top: 50%;
            transform: translateY(-50%);
        }

        .south {
            bottom: 5px;
            left: 50%;
            transform: translateX(-50%);
        }

        .west {
            left: 5px;
            top: 50%;
            transform: translateY(-50%);
        }

        .needle {
            position: absolute;

            width: 4px;
            height: 75px;

            background: linear-gradient(
                to bottom,
                #ff3b3b 50%,
                white 50%
            );

            left: 50%;
            top: 15px;

            transform-origin: 50% 75px;

            transform: translateX(-50%);

            border-radius: 5px;

            box-shadow: 0 0 10px #ff3b3b88;
        }

        .center {
            position: absolute;

            width: 18px;
            height: 18px;

            border-radius: 50%;

            background: white;

            left: 50%;
            top: 50%;

            transform: translate(-50%, -50%);

            box-shadow: 0 0 10px white;
        }

        .degree {
            font-size: 32px;
            font-weight: bold;
            margin-top: 15px;
        }

        .direction-text {
            color: #9ba8bb;
            margin-top: 5px;
        }

        #enableCompass {
            background: #42e6a4;
            color: #07101d;
        }

        .info {
            margin-top: 25px;
            padding: 15px;

            border-radius: 15px;

            background: #0d121b;

            color: #8995a8;

            font-size: 13px;

            line-height: 1.5;
        }
    </style>
</head>

<body>

<div class="app">

    <h1>📡 Radio Telescope</h1>

    <div class="subtitle">
        JUPITER RECEIVER
    </div>

    <div class="jupiter"></div>

    <h2>🪐 JOWISZ</h2>

    <div class="status" id="status">
        RECEIVER STANDBY
    </div>

    <button onclick="startReceiver()">
        ▶ START RECEIVER
    </button>


    <!-- KOMPAS -->

    <div class="compass-container">

        <div class="compass" id="compass">

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

            <div class="needle"></div>

            <div class="center"></div>

        </div>

    </div>


    <div class="degree" id="degree">
        --°
    </div>

    <div class="direction-text" id="directionText">
        Kompas wyłączony
    </div>


    <button id="enableCompass" onclick="enableCompass()">
        🧭 WŁĄCZ KOMPAS
    </button>


    <div class="info">

        📱 Obracaj iPhone'a, aby zobaczyć zmianę kierunku.

        <br><br>

        🔴 Czerwona część igły wskazuje północ.

        <br><br>

        ⚠️ Kompas wymaga zgody na dostęp do czujników telefonu.

    </div>

</div>


<script>


// ======================================
// RADIO TELESCOPE
// ======================================

function startReceiver() {

    document.getElementById("status").innerText =
        "📡 RECEIVER ACTIVE";

}


// ======================================
// KOMPAS
// ======================================

let compassEnabled = false;


// Funkcja określająca nazwę kierunku

function getDirection(degrees) {

    if (degrees >= 337.5 || degrees < 22.5) {
        return "Północ (N)";
    }

    if (degrees >= 22.5 && degrees < 67.5) {
        return "Północny wschód (NE)";
    }

    if (degrees >= 67.5 && degrees < 112.5) {
        return "Wschód (E)";
    }

    if (degrees >= 112.5 && degrees < 157.5) {
        return "Południowy wschód (SE)";
    }

    if (degrees >= 157.5 && degrees < 202.5) {
        return "Południe (S)";
    }

    if (degrees >= 202.5 && degrees < 247.5) {
        return "Południowy zachód (SW)";
    }

    if (degrees >= 247.5 && degrees < 292.5) {
        return "Zachód (W)";
    }

    return "Północny zachód (NW)";
}


// ======================================
// ODCZYT KOMPASA
// ======================================

function handleOrientation(event) {

    let heading;


    // iPhone / Safari

    if (event.webkitCompassHeading !== undefined) {

        heading = event.webkitCompassHeading;

    }

    // Inne urządzenia

    else if (event.alpha !== null) {

        heading = 360 - event.alpha;

    }


    if (heading === undefined) {

        return;

    }


    // Normalizacja

    heading = (heading + 360) % 360;


    // Zaokrąglenie

    let roundedHeading =
        Math.round(heading);


    // Aktualizacja stopni

    document.getElementById("degree").innerText =
        roundedHeading + "°";


    // Aktualizacja kierunku

    document.getElementById("directionText").innerText =
        getDirection(heading);


    // Obracanie tarczy kompasu

    document.getElementById("compass").style.transform =
        "rotate(" + (-heading) + "deg)";

}


// ======================================
// WŁĄCZANIE KOMPASA
// ======================================

async function enableCompass() {


    // iOS 13+

    if (
        typeof DeviceOrientationEvent !== "undefined" &&
        typeof DeviceOrientationEvent.requestPermission === "function"
    ) {

        try {

            const permission =
                await DeviceOrientationEvent.requestPermission();


            if (permission === "granted") {

                window.addEventListener(
                    "deviceorientation",
                    handleOrientation,
                    true
                );

                compassEnabled = true;

                document.getElementById(
                    "directionText"
                ).innerText =
                    "Kompas aktywny";

            }

            else {

                alert(
                    "Nie udzielono dostępu do kompasu."
                );

            }

        }

        catch (error) {

            alert(
                "Nie udało się uruchomić kompasu."
            );

            console.error(error);

        }

    }

    else {

        // Android / inne przeglądarki

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

        compassEnabled = true;

        document.getElementById(
            "directionText"
        ).innerText =
            "Kompas aktywny";

    }

}

</script>

</body>
</html>
