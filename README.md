# akshitha-s-birthday
birthday
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday, My Love!</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9e6e6;
            text-align: center;
            color: #8a2be2;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 800px;
            margin: 50px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 15px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            font-size: 3em;
            color: #ff6347;
            margin-bottom: 20px;
        }
        p {
            font-size: 1.5em;
            line-height: 1.5;
            color: #333;
        }
        .heart {
            font-size: 2em;
            color: #ff69b4;
            animation: heartBeat 1s infinite;
        }
        .countdown {
            font-size: 2.5em;
            color: #ff6347;
            margin-top: 20px;
            font-weight: bold;
        }
        @keyframes heartBeat {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
            100% {
                transform: scale(1);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Happy Birthday, My Love!</h1>
        <p>
            To the most amazing person in my life, I want to say I am so thankful for you. You make my world brighter every single day. Even though we had our rough moments, I truly appreciate everything you are, and I want to make this day as special as you are.
        </p>
        <p>
            I am so lucky to have you by my side, and today, I celebrate you, your love, your kindness, and your beauty. ❤️
        </p>
        <div class="heart">❤️</div>
        <p class="countdown" id="countdown"></p>
    </div>

    <script>
        // Countdown to her next birthday (adjust the date)
        const birthday = new Date("2026-01-04T00:00:00"); // Update this date to her next birthday
        const countdownElement = document.getElementById('countdown');

        function updateCountdown() {
            const now = new Date();
            const timeDifference = birthday - now;

            if (timeDifference <= 0) {
                countdownElement.textContent = "Happy Birthday!";
                return;
            }

            const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeDifference % (1000 * 60)) / 1000);

            countdownElement.textContent = `Countdown to your special day: ${days}d ${hours}h ${minutes}m ${seconds}s`;
        }

        setInterval(updateCountdown, 1000);  // Update countdown every second
    </script>
</body>
</html>
