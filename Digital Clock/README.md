# Dynamic Digital Clock

This project demonstrates a digital clock that dynamically displays the current time using javascript

# Bulid your own digital clock using Javascript

# Features

- Displays current date & time
- Increments time on its own
- Fully dynamic

# Technologies

- vanilla javascript

# Javacsript

- The entire code for working of the clock is done within `setInterval()` function.
- Inside it a fuction of object called `Date()` is used to call year, hours, minutes, seconds,

```
let currentTime = new Date();
```

- In this project this is used to store hours, mintues & seconds in different variables

```
const hrs = document.getElementById("hrs")
const min = document.getElementById("min")
const sec = document.getElementById("sec")
```

- The obtained hours, minutes and seconds will be displayed in single digit if less than 10. For example, the current hour will be displayed as 7 instead of 07. To always display the elements of time in two-digit format, a 0 is appended before them whenever they are less than 10

```
hrs.innerHTML = (currentTime.getHours() < 10?"0":"") + currentTime.getHours();
min.innerHTML = (currentTime.getMinutes() < 10?"0":"") + currentTime.getMinutes();
sec.innerHTML = (currentTime.getSeconds() < 10?"0":"") + currentTime.getSeconds();
```

- For incrementation use ` setInterval()` function

```
setInterval(() => {
    let currentTime = new Date();

    hrs.innerHTML = (currentTime.getHours() < 10?"0":"") + currentTime.getHours();
    min.innerHTML = (currentTime.getMinutes() < 10?"0":"") + currentTime.getMinutes();
    sec.innerHTML = (currentTime.getSeconds() < 10?"0":"") + currentTime.getSeconds();
},1000)
```

## Base Deign

- Basic html structure

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Clock</title>
</head>
<body>
    <div class="hero">
        <div class="container">
            <div class="clock">
                <span id="hrs">00</span>
                <span>:</span>
                <span id="min">00</span>
                <span>:</span>
                <span id="sec">00</span>
            </div>
        </div>
    </div>
    <!-- js -->
     <script src="js/main.js"></script>
</body>
</html>
```

- Attached Css

```
<link rel="stylesheet" href="css/main.css">
```

## Styling

- Used a ` blur()` effect for class like texture

```
:root{
    --primary-color: linear-gradient(45deg,darkblue,purple);
}

*{
    margin: 0;
    padding: 0;
}

.hero{
    width: 100%;
    min-height: 100vh;
    background: var(--primary-color);
    color: #fff;
    position: relative;
}

.container{
    width: 800px;
    height: 180px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
}

.clock{
    width: 100%;
    height: 100%;
    background: rgba(235, 0, 255, 0.11);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    backdrop-filter: blur(40px);
}

.container:before{
    content: '';
    width: 180px;
    aspect-ratio: 1/1;
    background: hotpink;
    border-radius: 5px;
    position: absolute;
    left: -50px;
    top: -50px;
    z-index: -1;
}

.container::after{
    content: '';
    width: 180px;
    aspect-ratio: 1/1;
    background: darkorange;
    border-radius: 50%;
    position: absolute;
    right: -30px;
    bottom: -50px;
    z-index: -1;
}


.clock span{
    font-size: 70px;
    width: 110px;
    display: inline-block;
    text-align: center;
    position: relative;
}

.clock span::after{
    font-size: 14px;
    position: absolute;
    bottom: -5px;
    left: 50%;
    transform: translateX(-50%);
}

#hrs::after{
    content: 'Hours';
}

#min::after{
    content: 'Mintues';
}

#sec::after{
    content: 'Seconds';
}
```
