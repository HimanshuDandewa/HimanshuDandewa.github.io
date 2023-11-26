<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Solar System Interactive</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        canvas {
            display: block;
        }

        #info {
            position: absolute;
            top: 10px;
            left: 10px;
            color: #ffffff;
            font-size: 16px;
        }
    </style>
</head>
<body>

    <canvas id="solarSystem"></canvas>
    <div id="info">Click on a planet to learn more!</div>

    <script>
        const planets = [
            { name: 'Mercury', radius: 2, distance: 50, color: '#b8b8b8' },
            { name: 'Venus', radius: 4, distance: 80, color: '#e3cda4' },
            { name: 'Earth', radius: 4.5, distance: 110, color: '#5ca3d8' },
            { name: 'Mars', radius: 3, distance: 150, color: '#e07f63' },
            { name: 'Jupiter', radius: 25, distance: 220, color: '#dcb487' },
            { name: 'Saturn', radius: 20, distance: 300, color: '#d9b08c' },
            { name: 'Uranus', radius: 15, distance: 380, color: '#97c7e0' },
            { name: 'Neptune', radius: 14, distance: 450, color: '#4e87b6' },
            { name: 'Pluto', radius: 1, distance: 500, color: '#c7c7c7' },
        ];

        const canvas = document.getElementById('solarSystem');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const sunRadius = 50;

        function drawPlanet(planet) {
            ctx.beginPath();
            ctx.arc(planet.distance, canvas.height / 2, planet.radius, 0, Math.PI * 2);
            ctx.fillStyle = planet.color;
            ctx.fill();
            ctx.closePath();
        }

        function drawSun() {
            ctx.beginPath();
            ctx.arc(canvas.width / 2, canvas.height / 2, sunRadius, 0, Math.PI * 2);
            ctx.fillStyle = '#ffc72c';
            ctx.fill();
            ctx.closePath();
        }

        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            drawSun();
            planets.forEach(drawPlanet);
        }

        function getMousePos(canvas, event) {
            const rect = canvas.getBoundingClientRect();
            return {
                x: event.clientX - rect.left,
                y: event.clientY - rect.top
            };
        }

        function isClickOnPlanet(mousePos, planet) {
            const dx = mousePos.x - planet.distance;
            const dy = mousePos.y - (canvas.height / 2);
            return Math.sqrt(dx * dx + dy * dy) < planet.radius;
        }

        canvas.addEventListener('click', function (event) {
            const mousePos = getMousePos(canvas, event);
            for (const planet of planets) {
                if (isClickOnPlanet(mousePos, planet)) {
                    displayPlanetInfo(planet);
                    break;
                }
            }
        });

        function displayPlanetInfo(planet) {
            const infoElement = document.getElementById('info');
            infoElement.textContent = `You clicked on ${planet.name}.`;
        }

        function animate() {
            draw();
            requestAnimationFrame(animate);
        }

        animate();
    </script>
</body>
</html>
