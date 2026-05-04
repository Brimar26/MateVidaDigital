
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MateVida Digital - Portal Educativo</title>
    <style>
        :root {
            --verde: #4CAF50; --azul: #2196F3; --amarillo: #FFC107; --naranja: #FF9800;
            --fondo: #e3f2fd; --azul-tech: #1a237e;
        }
        body { 
            margin: 0; background-color: var(--fondo); 
            font-family: 'Arial Rounded MT Bold', sans-serif; text-align: center; 
        }
        
        .top-nav {
            background: white; padding: 15px; display: flex;
            justify-content: space-between; box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            align-items: center; flex-wrap: wrap; gap: 10px;
        }
        .top-nav input { padding: 8px; border-radius: 20px; border: 1px solid #ccc; width: 200px; }
        .menu-usuario-top { display: flex; align-items: center; gap: 10px; font-size: 14px; }

        .hero { padding: 20px; }
        .robot { font-size: 60px; display: block; }
        .titulo { font-size: 40px; color: var(--verde); margin: 0; }
        .titulo span { color: var(--naranja); }
        .slogan { font-weight: bold; color: var(--azul); margin-bottom: 20px; display: block; }

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

        .main-stage {
            max-width: 900px; margin: 30px auto; background: white;
            padding: 30px; border-radius: 30px; min-height: 400px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        .grid-contenido {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px; margin-top: 20px;
        }
        .item-lista {
            border: 2px solid #f0f0f0; padding: 20px; border-radius: 15px;
            cursor: pointer; transition: 0.3s; background: white;
            text-decoration: none; color: black; display: block;
        }
        .item-lista:hover { border-color: var(--azul); transform: scale(1.05); }
        
        #visor-pro {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
            background: white; z-index: 1000;
        }
        .barra-visor {
            background: #2c3e50; color: white; padding: 10px 20px; 
            display: flex; justify-content: space-between; align-items: center;
        }
    </style>
</head>
<body>

<div class="top-nav">
    <input type="text" id="inputBusqueda" onkeyup="buscarContenido()" placeholder="🔍 Buscar actividad...">
    <div class="menu-usuario-top">
        <span onclick="irInicio()" style="cursor:pointer">🏠 Inicio</span> | 
        <span onclick="mostrarPerfil()" style="cursor:pointer">👤 Perfil</span>
    </div>
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
    <div class="card c-naranja" onclick="cargarSeccion('recursos')">👥<br>Recursos</div>
</div>

<div id="pantalla" class="main-stage">
    <h2>Entrena tu Mente, Domina los Números</h2>
    <p>Selecciona una categoría arriba para comenzar a aprender.</p>
    <img src="https://i.postimg.cc/Hn9YMpgX/Gemini-Generated-Image-at68jgat68jgat68.jpg" style="max-width:100%; border-radius:20px;">   
</div>

<div id="visor-pro">
    <div class="barra-visor">
        <strong id="titulo-juego-actual">Cargando...</strong>
        <button onclick="cerrarSoftware()" style="background:#e74c3c; color:white; border:none; padding:8px 15px; border-radius:5px; cursor:pointer;">✖ CERRAR</button>
    </div>
    <iframe id="iframe-software" src="" style="width:100%; height:calc(100% - 50px); border:none;"></iframe>
</div>

<script>
function buscarContenido() {
    let input = document.getElementById('inputBusqueda').value.toLowerCase();
    let items = document.getElementsByClassName('item-lista');
    for (let i = 0; i < items.length; i++) {
        let texto = items[i].innerText.toLowerCase();
        items[i].style.display = texto.includes(input) ? "block" : "none";
    }
}

function irInicio() {
    location.reload();
}

function mostrarPerfil() {
    document.getElementById('pantalla').innerHTML = `
        <h2 style="color:var(--azul)">👤 Mi Perfil de Estudiante</h2>
        <div style="background:#f9f9f9; padding:20px; border-radius:15px; display:inline-block;">
            <p><strong>Nombre:</strong> Explorador Matemático</p>
            <p><strong>Nivel:</strong> Primaria</p>
            <p><strong>Logros:</strong> 🎖️ Maestro de Sumas</p>
        </div>`;
}

function cargarSeccion(tipo) {
    const pantalla = document.getElementById('pantalla');
    let html = "";

    if (tipo === 'juegos') {
        html = `
            <h2 style="color:var(--verde)">🎮 Panel de Actividades Interactivas</h2>
            <div class="grid-contenido">
                <div class="item-lista" onclick="lanzarSoftware('https://view.genially.com/69ec0dd6dc5b8be996902a64', 'Carrera Operaciones')">
                    <div style="font-size:40px">🏎️</div><h3>Carrera Operaciones</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://view.genially.com/69ec0094c6e29311f5854247', 'Operaciones Matemáticas')">
                    <div style="font-size:40px">➕</div><h3>Operaciones Matemáticas</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://es.educaplay.com/juego/28831395-operaciones_fundamentales_si_no.html', 'Si o No')">
                    <div style="font-size:40px">✅</div><h3>Si o No</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://es.educaplay.com/juego/28831338-operaciones_en_la_vida_diaria.html', 'Vida Diaria')">
                    <div style="font-size:40px">📋</div><h3>Vida Diaria</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://es.educaplay.com/juego/28918221-desafios_cotidianos_con_operaciones.html', 'Desafíos Cotidianos')">
                    <div style="font-size:40px">🏆</div><h3>Desafíos Cotidianos</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://view.genially.com/69f7e18ce15a962730ed9a10', 'Compras')">
                    <div style="font-size:40px">🎮</div><h3>Compras</h3>
                </div>
                
            </div>`;
    } 
    else if (tipo === 'videos') {
        html = `
            <h2 style="color:var(--azul)">📺 Videoteca Educativa</h2>
            <div class="grid-contenido">
                <div class="item-lista" onclick="lanzarSoftware('https://www.youtube.com/embed/aEh9WnqiyAg', 'Operaciones Vida Diaria')">
                    <img src="https://img.youtube.com/vi/aEh9WnqiyAg/mqdefault.jpg" width="100%" style="border-radius:10px; margin-bottom:10px;">
                    <h3>Vida Diaria</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://www.youtube.com/embed/otatgqU8o0w', 'Fracciones Homogéneas')">
                    <img src="https://img.youtube.com/vi/otatgqU8o0w/mqdefault.jpg" width="100%" style="border-radius:10px; margin-bottom:10px;">
                    <h3>Fracciones Homogéneas</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://www.youtube.com/embed/yyKkL0R59g0', 'Fracciones Heterogéneas')">
                    <img src="https://img.youtube.com/vi/yyKkL0R59g0/mqdefault.jpg" width="100%" style="border-radius:10px; margin-bottom:10px;">
                    <h3>Fracciones Heterogéneas</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://www.youtube.com/embed/WBqXpj1_96g', 'Resta de Fracciones')">
                    <img src="https://img.youtube.com/vi/WBqXpj1_96g/mqdefault.jpg" width="100%" style="border-radius:10px; margin-bottom:10px;">
                    <h3>Resta de Fracciones</h3>
                </div>
            </div>`;
    }
    else if (tipo === 'fichas') {
        html = `
            <h2 style="color:var(--amarillo)">📚 Fichas e Imprimibles</h2>
            <div class="grid-contenido">
                <a href="https://web.seducoahuila.gob.mx/biblioweb/upload/operaciones-y-problemas-3c2ba-de-primaria%20(1).pdf" target="_blank" class="item-lista">
                    <div style="font-size:40px">🧮</div><h3>Operaciones y Problemas</h3>
                </a>
                <a href="https://www.jica.go.jp/Resource/project/elsalvador/004/materials/ku57pq00003u6zom-att/cuaderno_ejercicios_primaria_05.pdf" target="_blank" class="item-lista">
                    <div style="font-size:40px">📓</div><h3>Cuaderno de Ejercicios</h3>
                </a>
                <a href="https://www.mamutmatematicas.com/ejercicios/tabla-orden-operaciones.php" target="_blank" class="item-lista">
                    <div style="font-size:40px">⚖️</div><h3>Orden de Operaciones</h3>
                </a>
                <a href="https://arbolabc.com/juegos-tablas-de-multiplicar/tablas-imprimibles/operaciones-tabla-del-7" target="_blank" class="item-lista">
                    <div style="font-size:40px">✖️</div><h3>Tablas de Multiplicar</h3>
                </a>
                <a href="https://www.thatquiz.org/es/preview?c=eirl0256" target="_blank" class="item-lista">
                    <div style="font-size:40px">💡</div><h3>Problemas Básicos</h3>
                </a>
                <a href="https://pruebat.org/lo-que-debes-saber-sobre-las-matematicas-para-la-vida-diaria/ejercicio-practica-resolviendo-operaciones-basicas/11407-331498" target="_blank" class="item-lista">
                    <div style="font-size:40px">🛠️</div><h3>Práctica para la Vida</h3>
                </a>
            </div>`;
    }
    else if (tipo === 'recursos') {
        html = `
            <h2 style="color:var(--naranja)">👥 Sección de Recursos</h2>
            <p>Consejos pedagógicos para apoyar el aprendizaje.</p>
            <div class="grid-contenido">
                <div class="item-lista">
                    <div style="font-size:40px">🏠</div>
                    <h3>Guía para Padres</h3>
                    <p>Cómo motivar el estudio de las matemáticas.</p>
               <li> <a href='https://gu-a-para-padres.tiiny.site/'>Menú de Padres</a></li>
                 </div>
                <div class="item-lista">
                    <div style="font-size:40px">👤</div>
                    <h3>Guía para Estudiantes</h3>
                 <li> <a href='https://www.pdffiller.com/s/1LObffqZo7'>Menú de Estudiantes</a></li>
                </div>
                <div class="item-lista">
                <div style="font-size:40px">🎖️</div>
                <h3>Guía para Docentes</h3>
                <li> <a href='https://www.pdffiller.com/s/ULtGifon'>Menú de Docentes</a></li>
                </div>
            </div>`;
    }

    pantalla.innerHTML = html;
}

function lanzarSoftware(url, nombre) {
    document.getElementById('titulo-juego-actual').innerText = nombre;
    const iframe = document.getElementById('iframe-software');
    iframe.src = url;
    document.getElementById('visor-pro').style.display = 'block';
    document.body.style.overflow = 'hidden'; 
}

function cerrarSoftware() {
    document.getElementById('visor-pro').style.display = 'none';
    document.getElementById('iframe-software').src = ""; 
    document.body.style.overflow = 'auto';
}
</script>
</body>
</html>
