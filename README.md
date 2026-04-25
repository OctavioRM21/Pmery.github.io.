<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PropuestaParaMery ❤️</title>
    <style>
        :root {
            --color-papel: #fff9f1;
            --color-texto: #5a444e;
            --color-acento: #ff4d6d;
        }

        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: radial-gradient(circle, #ffe5ec 0%, #ffc2d1 100%);
            font-family: 'Georgia', serif;
            overflow: hidden;
        }

        /* --- Estructura del Libro --- */
        .libro {
            position: relative;
            width: 350px;
            height: 450px;
            perspective: 1500px;
        }

        .pagina {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            background-color: var(--color-papel);
            border-radius: 10px 20px 20px 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            transform-origin: left;
            transition: transform 0.8s cubic-bezier(0.645, 0.045, 0.355, 1);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 40px;
            box-sizing: border-box;
            text-align: center;
            cursor: pointer;
            border-left: 2px solid rgba(0,0,0,0.1);
        }

        .pagina.volteada {
            transform: rotateY(-180deg);
            z-index: 0;
        }

        /* --- Contenido --- */
        h2 { color: var(--color-acento); font-size: 1.8rem; margin-bottom: 20px; }
        p { color: var(--color-texto); font-size: 1.3rem; line-height: 1.6; font-style: italic; }
        .instruccion { 
            position: absolute; 
            bottom: 20px; 
            font-size: 0.8rem; 
            color: #999; 
            font-family: sans-serif;
        }

        /* --- Página Final (Propuesta) --- */
        .ultima-pagina {
            background-color: #fff;
            z-index: -1; /* Se queda al fondo */
        }

        .botones {
            display: flex;
            gap: 20px;
            margin-top: 30px;
        }

        .btn {
            padding: 12px 25px;
            font-size: 1.1rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            background-color: var(--color-acento);
            color: white;
            transition: transform 0.2s;
            box-shadow: 0 4px 15px rgba(255, 77, 109, 0.3);
        }

        .btn:hover { transform: scale(1.1); }

        /* --- Efecto Pétalos (JavaScript los creará) --- */
        .petalo {
            position: absolute;
            width: 15px;
            height: 15px;
            background: #ffb3c1;
            border-radius: 0 50% 50% 50%;
            opacity: 0.6;
            z-index: -1;
            animation: caer linear forwards;
        }

        @keyframes caer {
            to { transform: translateY(100vh) rotate(360deg); }
        }
    </style>
</head>
<body>

    <div class="libro" id="libro">
        
        <div class="pagina ultima-pagina">
            <h2>¿Quieres ser mi novia? ❤️</h2>
            <p>Y no es pregunta...</p>
            <div class="botones">
                <button class="btn" onclick="aceptar()">¡SÍ! 😍</button>
                <button class="btn" onclick="aceptar()">¡OBVIO SÍ! 🌹</button>
            </div>
        </div>

        <div class="pagina" onclick="voltear(this)" style="z-index: 3;">
            <h2>Por último...</h2>
            <p>"Se que no hice las cosas muy bien, Pero quiero prometerte que estoy comprometido en hacerte la mujer mas feliz, y dia con dia ser mejor, y hacerte sentir muy especial, Tengo mucho que decir pero, hasta ver tu respuesta My Love "</p>
            <span class="instruccion">Toca para llegar al final...</span>
        </div>

        <div class="pagina" onclick="voltear(this)" style="z-index: 4;">
            <h2>A tu lado...</h2>
            <p>"Quiero tener un futuro contigo, Que seamos un gran equipo, Eres muy especial para mí, Una gran mujer y estaria muy contento de poder formar una vida contigo, si me lo permites, Claro"</p>
            <span class="instruccion">Toca para seguir leyendo...</span>
        </div>

        <div class="pagina" onclick="voltear(this)" style="z-index: 5;">
            <h2>Para El Amor De Vida</h2>
            <p> "Se que no fue lo que planeamos, Pero estoy contento que hoy estemos acá, dare lo mejor de mí"</p>
            <span class="instruccion">Toca para pasar la página...</span>
        </div>

        <div class="pagina" onclick="voltear(this)" style="z-index: 6; background: var(--color-acento);">
            <h1 style="color: white; font-size: 2.5rem;">Propuesta Para Mi Niña ❤️</h1>
            <p style="color: white;">Tengo algo que decirte...</p>
            <span class="instruccion" style="color: white;">Toca para abrir el libro</span>
        </div>

    </div>

    <script>
        // Función para pasar las páginas
        function voltear(elemento) {
            elemento.classList.add('volteada');
            // Reducimos el z-index después de la animación para que no bloquee clics
            setTimeout(() => {
                elemento.style.zIndex = 0;
            }, 800);
        }

        // Función al aceptar
        function aceptar() {
            alert('¡SABÍA QUE DIRÍAS QUE SÍ! Si no... Te ¡RAPTO! Te amo con todo mi corazón ❤️');
            lluviaPetalos();
        }

        // Decoración extra al aceptar
        function lluviaPetalos() {
            for (let i = 0; i < 50; i++) {
                const petalo = document.createElement('div');
                petalo.classList.add('petalo');
                petalo.style.left = Math.random() * 100 + 'vw';
                petalo.style.animationDuration = (Math.random() * 3 + 2) + 's';
                petalo.style.top = '-20px';
                document.body.appendChild(petalo);
            }
        }
    </script>
</body>
</html>

