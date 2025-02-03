<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Descifra la Contraseña</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #0a0a23;
            color: white;
        }
        .container {
            width: 80%;
            margin: auto;
            background: #1a1a2e;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px gray;
        }
        .pista {
            background: #007BFF;
            padding: 10px;
            margin: 10px;
            border-radius: 5px;
            cursor: pointer;
            display: inline-block;
            color: white;
            font-size: 18px;
        }
        .pista:hover {
            background: #0056b3;
        }
        #respuesta {
            padding: 10px;
            font-size: 16px;
            border-radius: 5px;
        }
        button {
            padding: 12px 20px;
            font-size: 18px;
            border: none;
            background: #28a745;
            color: white;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #218838;
        }
        #resultado {
            margin-top: 20px;
            font-size: 18px;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>🔐 Descifra la Contraseña</h1>
        <p>Haz clic en las pistas para descubrir la clave secreta y escríbela en el campo de respuesta.</p>

        <div class="pista" onclick="mostrarPista(1)">📜 Pista 1</div>
        <div class="pista" onclick="mostrarPista(2)">📜 Pista 2</div>
        <div class="pista" onclick="mostrarPista(3)">📜 Pista 3</div>

        <p id="pistaTexto"></p>

        <label for="respuesta">🔑 Ingresa la contraseña:</label>
        <input type="text" id="respuesta" placeholder="Escribe aquí..." />

        <br><br>
        <button onclick="validarContraseña()">✅ Comprobar</button>

        <p id="resultado"></p>
    </div>

    <script>
        function mostrarPista(num) {
            let pistaTexto = document.getElementById("pistaTexto");
            if (num === 1) {
                pistaTexto.innerHTML = "🔍 Pista 1: La primera letra es la inicial de la empresa que trabaja en ciberseguridad y espacio.";
            } else if (num === 2) {
                pistaTexto.innerHTML = "🧮 Pista 2: El número de letras en 'Ciberseguridad' menos el número de vocales en 'Hacker' te dará la segunda letra, será la posición del alfabeto que te dará la segunda letra";
            } else if (num === 3) {
                pistaTexto.innerHTML = "🖥️ Pista 3: En código ASCII, la letra 86 representa la última letra de la contraseña.";
            }
        }

        function validarContraseña() {
            let respuesta = document.getElementById("respuesta").value.toUpperCase();
            let resultado = document.getElementById("resultado");

            if (respuesta === "GMV") {
                resultado.innerHTML = "✅ ¡Contraseña correcta! Has detenido el ciberataque.";
                resultado.style.color = "lightgreen";
            } else {
                resultado.innerHTML = "❌ Contraseña incorrecta. Vuelve a intentarlo.";
                resultado.style.color = "red";
            }
        }
    </script>

</body>
</html>
