<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Can I be your Valentine?</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap" rel="stylesheet">
    <style>
        body {
            background-color: #8B0000; /* Dark Red */
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            position: relative;
            overflow: hidden;
        }
        h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 3em;
            margin: 20px;
        }
        .message {
            font-size: 1.5em;
            margin: 10px;
        }
        .button-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            position: relative;
        }
        .button {
            background-color: #B22222; /* Firebrick */
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 5px;
            font-size: 1.2em;
            cursor: pointer;
            text-decoration: none;
            transition: background-color 0.3s, transform 0.2s;
            position: relative;
        }
        .button:hover {
            background-color: #FF6347; /* Tomato */
            transform: scale(1.1);
        }
        .footer {
            margin-top: 30px;
            font-size: 1em;
        }

        /* Heart styles */
        .hearts {
            position: absolute;
            top: -10%;
            left: 50%;
            transform: translateX(-50%);
            pointer-events: none;
            z-index: 10;
        }
        .hearts div {
            position: absolute;
            width: 25px;
            height: 25px;
            background-color: white;
            clip-path: polygon(50% 0%, 0% 50%, 50% 100%, 100% 50%);
            animation: float 3s ease-in-out infinite;
            opacity: 0.9;
        }
        @keyframes float {
            0% { transform: translateY(0); }
            100% { transform: translateY(-300px); }
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 2em;
            }
            .button {
                font-size: 1em;
                padding: 10px 20px;
            }
        }
    </style>
</head>
<body>

    <h1>Can I be your Valentine?</h1>
    <div class="message">
        <p>Hey Babyy :3</p>
    </div>

    <div class="button-container">
        <button class="button" id="yesButton" onclick="playLoveSong()">Yes!</button>
        <button class="button" id="noButton" onmouseover="moveNoButton(event)">No!</button>
    </div>

    <div class="footer"></div>

    <!-- Heart effect -->
    <div id="hearts" class="hearts"></div>

    <script>
        function playLoveSong() {
          
            window.open("https://open.spotify.com/playlist/6G3huDZn1EH2dFPVLlVo3I?si=268a4b1611fd4381", "_blank");

            generateHearts();
            alert("Yay! Thank you, babe. I can't wait to spend Valentine's with you ❤️");

          
            setTimeout(() => {
                window.location.href = "sms:?body=Yes! I would love to be your Valentine ❤️";
            }, 2000);
        }

        function moveNoButton(event) {
            event.preventDefault();
            const noButton = document.getElementById('noButton');
            const randomX = Math.random() * (window.innerWidth - 200);
            const randomY = Math.random() * (window.innerHeight - 100);
            noButton.style.position = 'absolute';
            noButton.style.left = `${randomX}px`;
            noButton.style.top = `${randomY}px`;
        }

     
        function generateHearts() {
            const heartsContainer = document.getElementById('hearts');
            for (let i = 0; i < 30; i++) {
                const heartPiece = document.createElement('div');
                heartPiece.style.left = `${Math.random() * 100}%`;
                heartPiece.style.animationDelay = `${Math.random() * 2}s`;
                heartsContainer.appendChild(heartPiece);
            }
        }
    </script>

</body>
</html>
