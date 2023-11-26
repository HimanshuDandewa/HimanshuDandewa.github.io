<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Galaxy and Planets</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #282c34;
            color: #ffffff;
        }

        header {
            background-color: #61dafb;
            color: #282c34;
            text-align: center;
            padding: 1em;
        }

        main {
            padding: 20px;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
        }

        .planet {
            border: 2px solid #61dafb;
            margin: 10px;
            padding: 15px;
            background-color: #ffffff;
            cursor: pointer;
            transition: transform 0.3s;
            flex: 0 1 calc(33.333% - 20px);
            max-width: calc(33.333% - 20px);
            box-sizing: border-box;
        }

        .planet:hover {
            transform: scale(1.05);
        }

        .planet img {
            width: 100%;
            height: auto;
            border-bottom: 2px solid #61dafb;
            margin-bottom: 10px;
        }

        .planet-details {
            display: none;
            margin-top: 10px;
        }

        @media (max-width: 768px) {
            .planet {
                flex: 0 1 calc(50% - 20px);
                max-width: calc(50% - 20px);
            }
        }

        @media (max-width: 480px) {
            .planet {
                flex: 1 0 calc(100% - 20px);
                max-width: calc(100% - 20px);
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>Our Galaxy and Planets</h1>
    </header>

    <main>
        <div class="planet" onclick="showDetails('mercury')">
            <img src="mercury.jpg" alt="Mercury">
            <h2>Mercury</h2>
        </div>
        <div class="planet" onclick="showDetails('venus')">
            <img src="venus.jpg" alt="Venus">
            <h2>Venus</h2>
        </div>
        <!-- Add more planets as needed -->

        <div id="mercury-details" class="planet-details">
            <h3>Mercury</h3>
            <p>Mercury is the smallest and innermost planet in our solar system. It is named after the Roman god of commerce, travel, and thievery.</p>
            <p>Distance from the Sun: 57.9 million km</p>
            <p>Orbital Period: 88 Earth days</p>
            <p>Surface Temperature: -173 to 427 °C</p>
        </div>
        <div id="venus-details" class="planet-details">
            <h3>Venus</h3>
            <p>Venus is the second planet from the Sun. It is often called the "Morning Star" or the "Evening Star" due to its brightness.</p>
            <p>Distance from the Sun: 108.2 million km</p>
            <p>Orbital Period: 225 Earth days</p>
            <p>Surface Temperature: 462 °C</p>
        </div>
        <!-- Add more planet details as needed -->
    </main>

    <script>
        function showDetails(planet) {
            // Hide all planet details
            const planetDetails = document.querySelectorAll('.planet-details');
            planetDetails.forEach(detail => {
                detail.style.display = 'none';
            });

            // Show the details of the clicked planet
            const planetDetailsToShow = document.getElementById(planet + '-details');
            if (planetDetailsToShow) {
                planetDetailsToShow.style.display = 'block';
            }
        }
    </script>

</body>
</html>
