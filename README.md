<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
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

        /* Confetti styles */
        .confetti {
            position: absolute;
            top: -10%;
            left: 50%;
            transform: translateX(-50%);
            pointer-events: none;
            z-index: 10;
            animation: fall 3s linear infinite;
        }
        .confetti div {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: white;
            opacity: 0.9;
            animation: move 2s ease-in-out infinite;
        }
        @keyframes move {
            0% { transform: translateY(0) rotate(0); }
            50% { transform: translateY(50vh) rotate(180deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }
        @keyframes fall {
            0% { top: -10%; opacity: 1; }
            100% { top: 100%; opacity: 0; }
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

    <h1>Will You Be My Valentine?</h1>
    <div class="message">
        <p>Hey Babyy :3</p>
    </div>

    <audio id="valentineSong" src="https://docs.google.com/uc?export=download&id=1xqjwLtFFrFHiZ_a_nD0zV9hCPQyLJTXw"></audio>
    <audio id="loveSong" src="https://open.spotify.com/track/4HFAhNtnR6mXagPhUBqY07" type="audio/mpeg"></audio>

    <div class="button-container">
        <button class="button" id="yesButton" onclick="playLoveSong()">Yes!</button>
        <button class="button" id="noButton" onmouseover="moveNoButton(event)">No!</button>
    </div>

    <div class="footer"></div>

    <!-- Confetti effect -->
    <div id="confetti" class="confetti"></div>

    <script>
        function playLoveSong() {
            const loveSong = document.getElementById("loveSong");
            loveSong.play();
            // Trigger confetti effect
            generateConfetti();
            alert("Yay! Can't wait to spend Valentine's with you ❤️");

            // Redirect to iMessage (SMS link as a fallback)
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

        // Generate confetti
        function generateConfetti() {
            const confettiContainer = document.getElementById('confetti');
            for (let i = 0; i < 30; i++) {
                const confettiPiece = document.createElement('div');
                confettiPiece.style.left = `${Math.random() * 100}%`;
                confettiPiece.style.animationDelay = `${Math.random() * 2}s`;
                confettiContainer.appendChild(confettiPiece);
            }
        }
    </script>

</body>
</html>
