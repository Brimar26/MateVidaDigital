
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MateVida Digital - Aprende Jugando</title>
    <style>
        :root {
            --verde: #4CAF50; --azul: #2196F3; --amarillo: #FFC107; --naranja: #FF9800;
            --fondo: #e3f2fd;
        }
        body { 
            margin: 0; background-color: var(--fondo); 
            font-family: 'Arial Rounded MT Bold', sans-serif; text-align: center; 
        }
        /* BARRA SUPERIOR */
        .top-nav {
            background: white; padding: 15px; display: flex;
            justify-content: space-around; box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        /* LOGO Y PERSONAJE */
        .hero { padding: 30px; }
        .robot { font-size: 80px; display: block; margin-bottom: 10px; }
        .titulo { font-size: 50px; color: var(--verde); margin: 0; }
        .titulo span { color: var(--naranja); }
        .slogan { 
            font-size: 20px; color: var(--azul); font-weight: bold;
            background: white; padding: 5px 20px; border-radius: 50px;
            display: inline-block; margin-top: 10px; border: 2px solid var(--azul);
        }
        /* BOTONES HORIZONTALES */
        .menu { display: flex; justify-content: center; gap: 15px; flex-wrap: wrap; padding: 20px; }
        .card {
            width: 140px; padding: 20px; border-radius: 20px; color: white;
            font-weight: bold; cursor: pointer; box-shadow: 0 5px 0px rgba(0,0,0,0.2);
        }
        .c-verde { background: var(--verde); }
        .c-azul { background: var(--azul); }
        .c-amarillo { background: var(--amarillo); }
        .c-naranja { background: var(--naranja); }
    </style>
</head>
<body>
    <div class="top-nav">
        <input type="text" placeholder="🔍 Buscar juego...">
        <div>🏠 Inicio | 👤 Perfil | 🌐 Idioma</div>
    </div>
    <div class="hero">
        <span class="robot">🤖</span>
        <h1 class="titulo">MateVida <span>Digital</span></h1>
        <div class="slogan">“Aprende jugando”</div>
    </div>
    <div class="menu">
        <div class="card c-verde">🎮<br>Juegos</div>
        <div class="card c-azul">📺<br>Videos</div>
        <div class="card c-amarillo">🏆<br>Logros</div>
        <div class="card c-naranja">📚<br>Fichas</div>
    </div>
</body>
</html>
