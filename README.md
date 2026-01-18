# _El_Patron_23
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Rahim ❤️</title>
<style>
    body {
        margin: 0;
        overflow: hidden;
        background: black;
        font-family: 'Courier New', monospace;
    }

    canvas {
        display: block;
    }

    .message {
        position: absolute;
        top: 50%;
        width: 100%;
        text-align: center;
        font-size: 48px;
        color: red;
        opacity: 0;
        transform: translateY(-50%);
        animation: showText 3s ease forwards;
        animation-delay: 8s;
        text-shadow: 0 0 10px red, 0 0 20px crimson;
    }

    @keyframes showText {
        to {
            opacity: 1;
        }
    }
</style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="message">
    ✨ Happy Birthday To You Rahim ✨
</div>

<script>
    const canvas = document.getElementById("matrix");
    const ctx = canvas.getContext("2d");

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const phrase = "I love you rahim ";
    const fontSize = 18;
    const columns = canvas.width / fontSize;

    const drops = [];
    for (let i = 0; i < columns; i++) {
        drops[i] = Math.random() * canvas.height;
    }

    function draw() {
        ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
        ctx.fillRect(0, 0, canvas.width, canvas.height);

        ctx.fillStyle = "red";
        ctx.font = fontSize + "px monospace";

        for (let i = 0; i < drops.length; i++) {
            const text = phrase[Math.floor(Math.random() * phrase.length)];
            ctx.fillText(text, i * fontSize, drops[i]);

            if (drops[i] > canvas.height && Math.random() > 0.975) {
                drops[i] = 0;
            }
            drops[i] += fontSize;
        }
    }

    setInterval(draw, 50);

    window.onresize = () => {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    };
</script>

</body>
</html>
