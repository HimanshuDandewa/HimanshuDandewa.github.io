<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Solar System</title>
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
        <h1>Our Solar System</h1>
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
        <div class="planet" onclick="showDetails('earth')">
            <img src="earth.jpg" alt="Earth">
            <h2>Earth</h2>
        </div>
        <div class="planet" onclick="showDetails('mars')">
            <img src="mars.jpg" alt="Mars">
            <h2>Mars</h2>
        </div>
        <div class="planet" onclick="showDetails('jupiter')">
            <img src="jupiter.jpg" alt="Jupiter">
            <h2>Jupiter</h2>
        </div>
        <div class="planet" onclick="showDetails('saturn')">
            <img src="saturn.jpg" alt="Saturn">
            <h2>Saturn</h2>
        </div>
        <div class="planet" onclick="showDetails('uranus')">
            <img src="uranus.jpg" alt="Uranus">
            <h2>Uranus</h2>
        </div>
        <div class="planet" onclick="showDetails('neptune')">
            <img src="neptune.jpg" alt="Neptune">
            <h2>Neptune</h2>
        </div>
        <div class="planet" onclick="showDetails('pluto')">
            <img src="pluto.jpg" alt="Pluto">
            <h2>Pluto</h2>
        </div>

        <div id="mercury-details" class="planet-details">
            <h3>Mercury</h3>
            <p>Mercury is the smallest and innermost planet in our solar system...</p>
            <!-- Additional details go here -->
        </div>
        <div id="venus-details" class="planet-details">
            <h3>Venus</h3>
            <p>Venus is the second planet from the Sun. It is often called the "Morning Star"...</p>
            <!-- Additional details go here -->
        </div>
        <div id="earth-details" class="planet-details">
            <h3>Earth</h3>
            <p>Earth is the third planet from the Sun and the only known astronomical object to support life...</p>
            <!-- Additional details go here -->
        </div>
        <div id="mars-details" class="planet-details">
            <h3>Mars</h3>
            <p>Mars is the fourth planet from the Sun and the second smallest planet in the solar system...</p>
            <!-- Additional details go here -->
        </div>
        <div id="jupiter-details" class="planet-details">
            <h3>Jupiter</h3>
            <p>Jupiter is the fifth planet from the Sun and the largest in the Solar System...</p>
            <!-- Additional details go here -->
        </div>
        <div id="saturn-details" class="planet-details">
            <h3>Saturn</h3>
            <p>Saturn is the sixth planet from the Sun and the second-largest in the Solar System...</p>
            <!-- Additional details go here -->
        </div>
        <div id="uranus-details" class="planet-details">
            <h3>Uranus</h3>
            <p>Uranus is the seventh planet from the Sun. It has the third-largest planetary radius and fourth-largest planetary mass...</p>
            <!-- Additional details go here -->
        </div>
        <div id="neptune-details" class="planet-details">
            <h3>Neptune</h3>
            <p>Neptune is the eighth and farthest known Solar planet from the Sun. It is the fourth-largest planet by diameter and the third-largest by mass...</p>
            <!-- Additional details go here -->
        </div>
        <div id="pluto-details" class="planet-details">
            <h3>Pluto</h3>
            <p>Pluto is a dwarf planet in our solar system. It was reclassified as a dwarf planet by the International Astronomical Union (IAU) in 2006...</p>
            <!-- Additional details go here -->
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
