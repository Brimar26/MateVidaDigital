<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MateVida Digital - Portal Educativo</title>
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
            align-items: center;
        }
        .top-nav input { padding: 8px; border-radius: 20px; border: 1px solid #ccc; width: 200px; }

        /* CABECERA */
        .hero { padding: 20px; }
        .robot { font-size: 60px; display: block; }
        .titulo { font-size: 40px; color: var(--verde); margin: 0; }
        .titulo span { color: var(--naranja); }
        .slogan { font-weight: bold; color: var(--azul); margin-bottom: 20px; display: block; }

        /* MENÚ DE BOTONES (LAS "CARPETAS") */
        .menu { display: flex; justify-content: center; gap: 15px; flex-wrap: wrap; padding: 10px; }
        .card {
            width: 120px; padding: 15px; border-radius: 20px; color: white;
            font-weight: bold; cursor: pointer; box-shadow: 0 5px 0px rgba(0,0,0,0.2);
            transition: 0.2s;
        }
        .card:active { transform: translateY(4px); box-shadow: 0 1px 0px rgba(0,0,0,0.2); }
        .c-verde { background: var(--verde); }
        .c-azul { background: var(--azul); }
        .c-amarillo { background: var(--amarillo); }
        .c-naranja { background: var(--naranja); }

        /* CONTENEDOR DINÁMICO (AQUÍ APARECEN LAS LISTAS) */
        .main-stage {
            max-width: 900px; margin: 30px auto; background: white;
            padding: 30px; border-radius: 30px; min-height: 400px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        /* ESTILO DE LAS LISTAS DE CONTENIDO */
        .grid-contenido {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px; margin-top: 20px;
        }
        .item-lista {
            border: 2px solid #f0f0f0; padding: 15px; border-radius: 15px;
            cursor: pointer; transition: 0.3s;
        }
        .item-lista:hover { background: #f9f9f9; border-color: var(--azul); }
        .item-lista img { width: 50px; margin-bottom: 10px; }
    </style>
</head>
<body>

    <div class="top-nav">
        <input type="text" placeholder="🔍 Buscar...">
        <div>🏠 Inicio | 👤 Perfil | 🌐 ES</div>
    </div>

    <div class="hero">
        <span class="robot">🤖</span>
        <h1 class="titulo">MateVida <span>Digital</span></h1>
        <span class="slogan">“Aprende jugando”</span>
    </div>

    <div class="menu">
        <div class="card c-verde" onclick="cargarSeccion('juegos')">🎮<br>Juegos</div>
        <div class="card c-azul" onclick="cargarSeccion('videos')">📺<br>Videos</div>
        <div class="card c-amarillo" onclick="cargarSeccion('fichas')">📚<br>Fichas</div>
        <div class="card c-naranja" onclick="cargarSeccion('padres')">👥<br>Padres</div>
    </div>

    <div id="pantalla-principal" class="main-stage">
        <h2>Bienvenido al Mundo Matemático</h2>
        <p>Selecciona una categoría arriba para comenzar a aprender.</p>
        <img src="https://img.freepik.com/vector-gratis/ilustracion-concepto-clase-matematicas_114360-3945.jpg" width="300">
    </div>

    <script>
        function cargarSeccion(tipo) {
            const pantalla = document.getElementById('pantalla-principal');
            
            if (tipo === 'juegos') {
                pantalla.innerHTML = `
                    <h2 style="color:var(--verde)">🎮 Lista de Juegos</h2>
                    <div class="grid-contenido">
                        <div class="item-lista" onclick="alert('Cargando Dominó...')">
                            <div style="font-size:30px">🎲</div>
                            <h3>Dominó Matemático</h3>
                            <p>Practica sumas y restas.</p>
                        </div>
                        <div class="item-lista" onclick="alert('Cargando Carrera...')">
                            <div style="font-size:30px">🏎️</div>
                            <h3>Carrera de Números</h3>
                            <p>¡Llega a la meta calculando!</p>
                        </div>
                    </div>
                `;
            } else if (tipo === 'videos') {
                pantalla.innerHTML = `
                    <h2 style="color:var(--azul)">📺 Videotutoriales</h2>
                    <div class="grid-contenido">
                        <div class="item-lista">
                            <div style="font-size:30px">🎥</div>
                            <h3>Aprender a Sumar</h3>
                            <p>Video para 1er grado.</p>
                        </div>
                        <div class="item-lista">
                            <div style="font-size:30px">🎥</div>
                            <h3>Las Tablas de Multiplicar</h3>
                            <p>Video musical divertido.</p>
                        </div>
                    </div>
                `;
            } else if (tipo === 'fichas') {
                pantalla.innerHTML = `
                    <h2 style="color:var(--amarillo)">📚 Fichas e Imprimibles</h2>
                    <div class="grid-contenido">
                        <div class="item-lista">
                            <div style="font-size:30px">📄</div>
                            <h3>Guía de Fracciones</h3>
                            <p>PDF para descargar.</p>
                        </div>
                    </div>
                `;
            }
        }
    </script>
</body>
</html>
