<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amigo Secreto</title>
    <style>
        /* Estilo del cuerpo */
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: url('https://cdn.pixabay.com/photo/2017/11/26/21/30/christmas-2979107_1280.jpg') no-repeat center center/cover;
        }

        /* Caja de regalo */
        .gift-box {
            position: relative;
            width: 150px;
            height: 150px;
            background: #e74c3c;
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            animation: bounce 1.5s infinite;
        }

        /* Lazo del regalo */
        .gift-box::before, .gift-box::after {
            content: '';
            position: absolute;
            background: #fff;
        }

        .gift-box::before {
            width: 20px;
            height: 100%;
        }

        .gift-box::after {
            width: 100%;
            height: 20px;
        }

        /* Animación de rebote */
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* Pantalla de revelación */
        .reveal {
            display: none;
            text-align: center;
            font-size: 2rem;
            color: white;
            animation: fadeIn 1s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>
    <!-- Caja de regalo -->
    <div id="giftBox" class="gift-box" onclick="revealSecret()">🎁</div>
    
    <!-- Mensaje de revelación -->
    <div id="reveal" class="reveal">
        Tu amigo secreto es: <span id="secretName"></span>!
    </div>

    <script>
        // Lista de participantes
        const participants = ["Ana", "Carlos", "María", "Juan", "Luisa", "Pedro"];

        // Selección aleatoria del amigo secreto
        let assignedSecret = participants[Math.floor(Math.random() * participants.length)];

        // Función para revelar el amigo secreto
        function revealSecret() {
            const giftBox = document.getElementById("giftBox");
            const reveal = document.getElementById("reveal");
            const secretName = document.getElementById("secretName");

            // Oculta la caja de regalo y muestra el mensaje
            giftBox.style.display = "none";
            reveal.style.display = "block";
            secretName.innerText = assignedSecret;
        }
    </script>
</body>
</html>
