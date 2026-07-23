/* =========================================
   RADIO TELESCOPE v0.8.1
   STABILIZED SENSOR SYSTEM
========================================= */

let rawHeading = null;
let filteredHeading = null;

let rawAltitude = null;
let filteredAltitude = null;

const SMOOTHING = 0.15;


/* =========================================
   ANGLE SMOOTHING
========================================= */

function smoothAngle(previous, current, factor){

    if(previous === null){
        return current;
    }

    let difference =
        ((current - previous + 540) % 360) - 180;

    return (
        previous +
        difference * factor +
        360
    ) % 360;

}


/* =========================================
   SENSOR ORIENTATION
========================================= */

function handleOrientation(event){

    let heading = null;


    /*
    iPhone / iPad
    */

    if(
        event.webkitCompassHeading !== undefined &&
        event.webkitCompassHeading !== null
    ){

        heading =
            event.webkitCompassHeading;

    }


    /*
    Other browsers
    */

    else if(
        event.alpha !== null
    ){

        heading =
            360 - event.alpha;

    }


    if(
        heading === null ||
        isNaN(heading)
    ){

        return;

    }


    rawHeading =
        (heading + 360) % 360;


    /*
    Smooth compass
    */

    filteredHeading =
        smoothAngle(
            filteredHeading,
            rawHeading,
            SMOOTHING
        );


    compassHeading =
        filteredHeading;


    headingElement.innerText =

        Math.round(
            filteredHeading
        ) +
        "°";


    directionElement.innerText =

        getDirection(
            filteredHeading
        );


    /*
    Visual compass
    */

    compassElement.style.transform =

        "rotate(" +
        (-filteredHeading) +
        "deg)";


    /*
    Update detection immediately
    */

    if(receiverActive){

        detectObjects();

    }

}


/* =========================================
   PHONE ALTITUDE
========================================= */

function handleMotion(event){

    if(
        !event.accelerationIncludingGravity
    ){

        return;

    }


    const y =
        event.accelerationIncludingGravity.y;

    const z =
        event.accelerationIncludingGravity.z;


    if(
        y === null ||
        z === null
    ){

        return;

    }


    let angle =

        Math.atan2(
            -y,
            z
        )
        *
        180
        /
        Math.PI;


    angle =

        Math.max(
            0,
            Math.min(
                90,
                angle
            )
        );


    rawAltitude =
        angle;


    /*
    Smooth altitude
    */

    if(
        filteredAltitude === null
    ){

        filteredAltitude =
            rawAltitude;

    }

    else{

        filteredAltitude =

            filteredAltitude +
            (
                rawAltitude -
                filteredAltitude
            )
            *
            SMOOTHING;

    }


    phoneAltitude =
        filteredAltitude;


    altitudeElement.innerText =

        Math.round(
            filteredAltitude
        ) +
        "°";


    altitudeStatus.innerText =
        "Gyroscope + accelerometer active";


    if(receiverActive){

        detectObjects();

    }

}


/* =========================================
   IMPROVED OBJECT DETECTION
========================================= */

function detectObjects(){

    if(
        !receiverActive
    ){

        return;

    }


    if(
        userLatitude === null ||
        userLongitude === null
    ){

        scanStatus.innerText =
            "🌍 Waiting for GPS...";

        return;

    }


    if(
        filteredHeading === null ||
        filteredAltitude === null
    ){

        scanStatus.innerText =
            "🧭 Waiting for phone orientation...";

        return;

    }


    const objects =
        calculateSkyPositions();


    let bestTarget =
        null;


    let bestScore =
        Infinity;


    for(
        const object
        of objects
    ){


        /*
        Object below horizon
        */

        if(
            object.altitude < 0
        ){

            continue;

        }


        /*
        Calculate direction error
        */

        const azimuthDifference =

            angleDifference(
                filteredHeading,
                object.azimuth
            );


        /*
        Calculate altitude error
        */

        const altitudeDifference =

            Math.abs(
                filteredAltitude -
                object.altitude
            );


        /*
        Detection field

        ±12° azimuth
        ±12° altitude
        */

        if(

            azimuthDifference <= 12

            &&

            altitudeDifference <= 12

        ){


            /*
            Weighted detection score

            Smaller = better

            */

            const score =

                azimuthDifference * 1.5

                +

                altitudeDifference;


            if(
                score < bestScore
            ){

                bestScore =
                    score;

                bestTarget =
                    object;

            }

        }

    }


    if(
        bestTarget
    ){

        lockTarget(
            bestTarget
        );

    }

    else{

        unlockTarget();

    }

}


/* =========================================
   IMPROVED TARGET LOCK
========================================= */

function lockTarget(object){

    currentTarget =
        object;


    targetName.innerText =

        "🎯 " +
        object.name;


    targetType.innerText =

        object.type;


    signalStrength.innerText =

        object.signal;


    signalFill.style.width =

        object.signal +
        "%";


    targetDirection.innerText =

        object.azimuth.toFixed(1) +
        "° " +
        getDirection(
            object.azimuth
        );


    targetAltitude.innerText =

        object.altitude.toFixed(1) +
        "°";


    if(
        object.distance
    ){

        targetDistance.innerText =

            object.distance.toFixed(4) +
            " AU";

    }


    targetDifficulty.innerText =

        object.difficulty;


    targetAudioSource.innerText =

        "Object signal";


    lockStatus.innerText =

        "🟢 TARGET LOCKED";


    lockStatus.classList.add(
        "locked"
    );


    audioStatus.innerText =

        "🎯 OBJECT DETECTED";


    sourceStatus.innerText =

        "Source: " +
        object.name;


    scanStatus.innerText =

        "🎯 LOCKED: " +
        object.name;

}
