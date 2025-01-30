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

        /* Heart styles */
        .hearts {
            position: absolute;
            top: -10%;
            left: 50%;
            transform: translateX(-50%);
            pointer-events: none;
            z-index: 10;
            animation: pop 3s ease-in-out infinite;
        }
        .hearts div {
            position: absolute;
            width: 25px;
            height: 25px;
            background-color: white;
            clip-path: polygon(50% 0%, 0% 50%, 50% 100%, 100% 50%);
            animation: popUp 2s ease-in-out infinite;
            opacity: 0.9;
        }
        @keyframes popUp {
            0% { transform: translateY(0) scale(1); opacity: 0.9; }
            50% { transform: translateY(-100px) scale(1.5); opacity: 1; }
            100% { transform: translateY(-200px) scale(2); opacity: 0; }
        }
        @keyframes pop {
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

    <h1>Can I be your Valentine?</h1>
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

    <!-- Heart effect -->
    <div id="hearts" class="hearts"></div>

    <script>
        function playLoveSong() {
            const loveSong = document.getElementById("loveSong");
            loveSong.play();
            // Trigger heart effect
            generateHearts();
            alert("Yay! Thank you, babe. I can't wait to spend Valentine's with you");

            // Redirect to iMessage (SMS link as a fallback)
            setTimeout(() => {
                window.location.href = "sms:?body=Yes! I would love to be your Valentine";
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

        // Generate hearts
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

        /* Heart styles */
        .hearts {
            position: absolute;
            top: -10%;
            left: 50%;
            transform: translateX(-50%);
            pointer-events: none;
            z-index: 10;
            animation: pop 3s ease-in-out infinite;
        }
        .hearts div {
            position: absolute;
            width: 25px;
            height: 25px;
            background-color: white;
            clip-path: polygon(50% 0%, 0% 50%, 50% 100%, 100% 50%);
            animation: popUp 2s ease-in-out infinite;
            opacity: 0.9;
        }
        @keyframes popUp {
            0% { transform: translateY(0) scale(1); opacity: 0.9; }
            50% { transform: translateY(-100px) scale(1.5); opacity: 1; }
            100% { transform: translateY(-200px) scale(2); opacity: 0; }
        }
        @keyframes pop {
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

    <h1>Can I be your Valentine?</h1>
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

    <!-- Heart effect -->
    <div id="hearts" class="hearts"></div>

    <script>
        function playLoveSong() {
            const loveSong = document.getElementById("loveSong");
            loveSong.play();
            // Trigger heart effect
            generateHearts();
            alert("Yay! Thank you, babe. I can't wait to spend Valentine's with you");

            // Redirect to iMessage (SMS link as a fallback)
            setTimeout(() => {
                window.location.href = "sms:?body=Yes! I would love to be your Valentine";
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

        // Generate hearts
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
