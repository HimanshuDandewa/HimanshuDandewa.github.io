<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Galaxy and Planets</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em;
        }

        main {
            padding: 20px;
        }

        .planet {
            border: 1px solid #ccc;
            margin: 10px;
            padding: 15px;
            background-color: white;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .planet:hover {
            transform: scale(1.05);
        }

        .planet img {
            width: 100%;
            height: auto;
        }

        .planet-details {
            display: none;
            margin-top: 10px;
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
            <p>Mercury is the smallest planet in our solar system...</p>
        </div>
        <div id="venus-details" class="planet-details">
            <p>Venus is the second planet from the Sun...</p>
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
