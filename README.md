# formybibi-
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 Surprise for You 💖</title>
    <style>
        body {
            text-align: center;
            font-family: 'Arial', sans-serif;
            background-color: #ffe6f2;
            color: #ff4081;
            margin: 0;
            padding: 20px;
        }
        h1 {
            font-size: 28px;
            margin-top: 50px;
        }
        .hidden {
            display: none;
        }
        button {
            background-color: #ff4081;
            color: white;
            border: none;
            padding: 15px 20px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 8px;
            margin-top: 20px;
        }
        button:hover {
            background-color: #e91e63;
        }
        #message {
            font-size: 22px;
            font-weight: bold;
            white-space: pre-line;
            display: inline-block;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 24px;
            animation: float 4s linear infinite;
        }
        @keyframes float {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }
    </style>
</head>
<body>

    <h1>สุขสันต์วันวาเลนไทน์นะที่รัก! 💘</h1>
    <p>ฉันมีบางอย่างอยากบอกเธอ...</p>
    <button onclick="showMessage()">กดเพื่อดูเซอร์ไพรส์! 🎁</button>
    
    <p id="message" class="hidden"></p>

    <audio id="loveSong" loop>
        <source src="your-song.mp3" type="audio/mp3">
        Your browser does not support the audio element.
    </audio>
    <br>
    <button onclick="toggleMusic()">🔊 เปิด/ปิดเพลง</button>

    <script>
        function showMessage() {
            const message = "รักเธอที่สุดเลยนะ 💖\nขอบคุณที่อยู่ด้วยกันเสมอ 💕\nขอให้วันนี้เป็นวันที่พิเศษของเรา!";
            let i = 0;
            const textDisplay = document.getElementById("message");
            textDisplay.classList.remove("hidden");
            textDisplay.innerHTML = "";

            function typeWriter() {
                if (i < message.length) {
                    textDisplay.innerHTML += message.charAt(i);
                    i++;
                    setTimeout(typeWriter, 50);
                }
            }
            typeWriter();
            createHearts();
        }

        function createHearts() {
            setInterval(() => {
                const heart = document.createElement("div");
                heart.classList.add("heart");
                heart.innerHTML = "❤️";
                document.body.appendChild(heart);
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.animationDuration = Math.random() * 3 + 2 + "s";
                setTimeout(() => {
                    heart.remove();
                }, 4000);
            }, 500);
        }

        function toggleMusic() {
            const song = document.getElementById("loveSong");
            if (song.paused) {
                song.play();
            } else {
                song.pause();
            }
        }
    </script>

</body>
</html>
