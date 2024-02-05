# SDKs
SDK
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Simulation Example</title>
    <style>
        canvas {
            border: 1px solid #000;
        }
    </style>
</head>
<body>
    <h1>Welcome to the Interactive Simulation!</h1>
    <canvas id="simulationCanvas" width="600" height="400"></canvas>

    <script>
        document.addEventListener("DOMContentLoaded", function() {
            var canvas = document.getElementById("simulationCanvas");
            var ctx = canvas.getContext("2d");

            var circle = {
                x: 100,
                y: 100,
                radius: 20,
                color: "#FF0000"
            };

            function drawCircle() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                ctx.beginPath();
                ctx.arc(circle.x, circle.y, circle.radius, 0, 2 * Math.PI);
                ctx.fillStyle = circle.color;
                ctx.fill();
                ctx.stroke();
            }

            function handleMouseClick(event) {
                var mouseX = event.clientX - canvas.getBoundingClientRect().left;
                var mouseY = event.clientY - canvas.getBoundingClientRect().top;

                var distance = Math.sqrt((mouseX - circle.x) ** 2 + (mouseY - circle.y) ** 2);
                if (distance <= circle.radius) {
                    alert("You clicked the circle!");
                }
            }

            canvas.addEventListener("click", handleMouseClick);

            drawCircle();
        });
    </script>
</body>
</html>
