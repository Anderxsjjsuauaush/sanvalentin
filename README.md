<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz San Valentín ❤️</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #ffebf0;
            font-family: 'Arial', sans-serif;
            overflow: hidden;
        }

        #container {
            text-align: center;
        }

        #mensaje {
            font-size: 24px;
            color: #d6336c;
            font-weight: bold;
            margin-bottom: 20px;
        }

        #boton {
            padding: 12px 25px;
            font-size: 18px;
            background-color: #d6336c;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        #boton:hover {
            background-color: #a52652;
        }

        .flor {
            position: absolute;
            width: 50px;
            height: 50px;
            background: radial-gradient(circle, #ff69b4, #d6336c);
            border-radius: 50%;
            opacity: 0;
            animation: florecer 4s ease-in-out forwards;
        }

        @keyframes florecer {
            0% {
                transform: scale(0);
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: scale(1.5);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div id="container">
        <p id="mensaje">Hoy es un día muy especial, y he hecho esto para ti ❤️</p>
        <button id="boton" onclick="mostrarFlores()">Haz clic aquí</button>
    </div>

    <script>
        function mostrarFlores() {
            const numFlores = 30;
            const colores = ['#ff69b4', '#ff1493', '#ff6eb4', '#ff8c69', '#ff6347'];

            for (let i = 0; i < numFlores; i++) {
                const flor = document.createElement('div');
                flor.className = 'flor';
                flor.style.left = Math.random() * 100 + 'vw';
                flor.style.top = Math.random() * 100 + 'vh';
                flor.style.backgroundColor = colores[Math.floor(Math.random() * colores.length)];
                flor.style.animationDelay = Math.random() * 2 + 's';
                document.body.appendChild(flor);

                // Eliminar la flor después de la animación
                flor.addEventListener('animationend', () => {
                    flor.remove();
                });
            }
        }
    </script>
</body>
</html>
