<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>MateVida Digital - Portal Educativo</title>
    <meta name="theme-color" content="#2196F3">
    
    <script>
        (function() {
            const avatarMateBase64 = "data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MTIgNTEyIj48Y2lyY2xlIGN4PSIyNTYiIGN5PSIyNTYiIHI9IjI0MCIgZmlsbD0iIzIxOTZGMyIvPjs8Y2lyY2xlIGN4PSIyNTYiIGN5PSIyNTYiIHI9IjIwMCIgZmlsbD0iIzFBMjM3RSIvPjxyZWN0IHg9IjE0MCIgeT0iMTcwIiB3aWR0aD0iMjMyIiBoZWlnaHQ9IjE4MCIgcng9IjMwIiBmaWxsPSIjRUNGMEYxIi8+PHJlY3QgeD0iMTgwIiB5PSIyMTAiIHdpZHRoPSI0MCIgaGVpZ2h0PSI0MCIgcng9IjEwIiBmaWxsPSIjNENBRjUwIi8+PHJlY3QgeD0iMjkyIiB5PSIyMTAiIHdpZHRoPSI0MCIgaGVpZ2h0PSI0MCIgcng9IjEwIiBmaWxsPSIjNENBRjUwIi8+PHBhdGggZD0iTTIxMCAyODBIMzAyIiBzdHJva2U9IiNGRjk4MDAiIHN0cm9rZS13aWR0aD0iMTIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIvPjxwYXRoIGQ9Ik0yMTAgMzAwSDMwMiIgc3Ryb2tlPSIjRkY5ODAwIiBzdHJva2Utd2lkdGg9IjEyIiBzdHJva2UtbGluZWNhcD0icm91bmQiLz48Y2lyY2xlIGN4PSIyNTYiIGN5PSIxMjAiIHI9IjIwIiBmaWxsPSIjRkZDMTA3Ii8+PGxpbmUgeDE9IjI1NiIgeTE9IjEyMCIgeDI9IjI1NiIgeTI9IjE3MCIgc3Ryb2tlPSIjRUNGMEYxIiBzdHJva2Utd2lkdGg9IjguIi8+PC9zdmc+";

            const manifest = {
                "name": "MateVida Digital",
                "short_name": "MateVida",
                "description": "Portal Educativo de Matemática Interactive",
                "start_url": window.location.href,
                "display": "standalone",
                "background_color": "#e3f2fd",
                "theme_color": "#2196F3",
                "orientation": "portrait-primary",
                "icons": [
                    {
                        "src": avatarMateBase64,
                        "sizes": "512x512",
                        "type": "image/svg+xml",
                        "purpose": "any maskable"
                    }
                ]
            };

            const stringManifest = JSON.stringify(manifest);
            const blob = new Blob([stringManifest], {type: 'application/json'});
            const manifestURL = URL.createObjectURL(blob);
            
            const link = document.createElement('link');
            link.rel = 'manifest';
            link.href = manifestURL;
            document.head.appendChild(link);
        })();
    </script>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
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
            align-items: center; flex-wrap: wrap; gap: 15px;
        }
        .top-nav input { padding: 10px 15px; border-radius: 20px; border: 1px solid #ccc; width: 100%; max-width: 250px; }
        .menu-usuario-top { display: flex; align-items: center; gap: 15px; font-size: 14px; font-weight: bold; }

        .hero { padding: 20px 10px; }
        .robot { font-size: 60px; display: block; }
        .titulo { font-size: clamp(30px, 8vw, 45px); color: var(--verde); margin: 5px 0; }
        .titulo span { color: var(--naranja); }
        .slogan { font-weight: bold; color: var(--azul); margin-bottom: 20px; display: block; font-size: 18px; }

        .btn-instalar-app {
            background: var(--azul); color: white; border: none; padding: 14px 22px;
            font-size: 15px; font-weight: bold; border-radius: 25px; cursor: pointer;
            box-shadow: 0 5px 0px #1976D2; display: inline-flex; align-items: center;
            justify-content: center; gap: 10px; margin: 15px auto 5px auto; transition: 0.2s;
            width: 100%; box-sizing: border-box;
        }
        .btn-instalar-app:active { transform: translateY(2px); box-shadow: 0 3px 0px #1976D2; }

        .menu { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; padding: 10px; max-width: 1000px; margin: 0 auto; }
        .card {
            width: calc(50% - 20px); max-width: 140px; padding: 18px 10px; border-radius: 20px; color: white;
            font-weight: bold; cursor: pointer; box-shadow: 0 5px 0px rgba(0,0,0,0.2);
            transition: 0.2s; font-size: 16px; box-sizing: border-box;
        }
        .card:active { transform: translateY(4px); box-shadow: 0 1px 0px rgba(0,0,0,0.2); }
        .c-verde { background: var(--verde); }
        .c-azul { background: var(--azul); }
        .c-amarillo { background: var(--amarillo); }
        .c-naranja { background: var(--naranja); }

        .main-stage {
            max-width: 900px; margin: 20px 15px; background: white; padding: 25px; border-radius: 30px; 
            min-height: 400px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); display: inline-block; 
            width: calc(100% - 30px); box-sizing: border-box;
        }

        .grid-contenido { display: grid; grid-template-columns: repeat(auto-fill, minmax(160px, 1fr)); gap: 15px; margin-top: 20px; }
        .item-lista {
            border: 2px solid #f0f0f0; padding: 15px; border-radius: 15px; cursor: pointer; transition: 0.3s; 
            background: white; text-decoration: none; color: black; display: flex; flex-direction: column; 
            align-items: center; justify-content: center;
        }
        .item-lista h3 { font-size: 1rem; margin: 10px 0 0 0; line-height: 1.2; }
        .item-lista:hover { border-color: var(--azul); transform: scale(1.03); }
        
        /* VISOR PRO MEJORADO */
        #visor-pro { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #1a1a2e; z-index: 2000; }
        .barra-visor { background: #16213e; color: white; padding: 10px 15px; display: flex; justify-content: space-between; align-items: center; gap: 10px; flex-wrap: wrap; }
        #titulo-juego-actual { font-size: 1rem; flex: 1; text-align: left; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
        .grupo-botones { display: flex; gap: 6px; flex-shrink: 0; flex-wrap: wrap; }
        .btn-accion { border: none; padding: 8px 12px; border-radius: 8px; cursor: pointer; color: white; font-weight: bold; font-size: 12px; display: flex; align-items: center; gap: 5px; }

        /* MODALES */
        #modal-qr, #modal-mensaje { display: none; position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%); background: white; padding: 20px; border-radius: 20px; box-shadow: 0 0 20px rgba(0,0,0,0.5); z-index: 2002; text-align: center; width: 85%; max-width: 320px; }
        #modal-mensaje textarea { width: 100%; height: 100px; padding: 10px; border-radius: 10px; border: 2px solid #ddd; resize: none; font-family: sans-serif; box-sizing: border-box; margin-bottom: 10px; }
        #overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 2001; }

        @media (min-width: 601px) { .card { width: 120px; } .top-nav { padding: 15px 40px; } .main-stage { margin: 30px auto; } }
        @media (max-width: 600px) {
            .top-nav { justify-content: center; }
            .menu-usuario-top { width: 100%; justify-content: center; border-top: 1px solid #eee; padding-top: 10px; }
            .barra-visor { padding: 8px; }
            #titulo-juego-actual { font-size: 0.85rem; width: 100%; text-align: center; }
            .grupo-botones { width: 100%; justify-content: center; }
        }

        #bloqueo-inicio { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: var(--fondo); z-index: 3000; display: flex; justify-content: center; align-items: center; padding: 20px; box-sizing: border-box; }
        .contenedor-login { background: white; padding: 30px; border-radius: 30px; box-shadow: 0 10px 25px rgba(0,0,0,0.1); width: 100%; max-width: 400px; }
        .contenedor-login input { width: 100%; padding: 12px 20px; margin: 15px 0; border-radius: 25px; border: 2px solid #ddd; font-size: 16px; box-sizing: border-box; text-align: center; }
        .contenedor-login button.btn-comenzar { background: var(--verde); color: white; border: none; padding: 12px 30px; font-size: 18px; font-weight: bold; border-radius: 25px; cursor: pointer; width: 100%; box-shadow: 0 4px 0px #388E3C; transition: 0.2s; }
        .contenedor-login button.btn-comenzar:active { transform: translateY(4px); box-shadow: 0 0px 0px #388E3C; }
    </style>
</head>
<body>

<audio id="musica-fondo" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<div id="bloqueo-inicio">
    <div class="contenedor-login">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" style="width: 100px; height: 100px; margin-bottom: 10px;">
            <circle cx="256" cy="256" r="240" fill="#2196F3"/>
            <circle cx="256" cy="256" r="200" fill="#1A237E"/>
            <rect x="140" y="170" width="232" height="180" rx="30" fill="#ECF0F1"/>
            <rect x="180" y="210" width="40" height="40" rx="10" fill="#4CAF50"/>
            <rect x="292" y="210" width="40" height="40" rx="10" fill="#4CAF50"/>
            <path d="M210 280H302" stroke="#FF9800" stroke-width="12" stroke-linecap="round"/>
            <path d="M210 300H302" stroke="#FF9800" stroke-width="12" stroke-linecap="round"/>
            <circle cx="256" cy="120" r="20" fill="#FFC107"/>
            <line x1="256" y1="120" x2="256" y2="170" stroke="#ECF0F1" stroke-width="8"/>
        </svg>
        <h2 style="color: var(--azul); margin: 10px 0;">¡Bienvenido a MateVida!</h2>
        <p style="color: #666; font-size: 14px;">Ingresa tu nombre o usuario para comenzar a jugar</p>
        <input type="text" id="nombreUsuarioInput" placeholder="Tu Nombre o Usuario...">
        <button class="btn-comenzar" onclick="ingresarAApp()">¡Comenzar! 🚀</button>
        
        <button id="btnInstalarPWA" class="btn-instalar-app" onclick="ejecutarInstalacion()">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" style="width: 22px; height: 22px;">
                <circle cx="256" cy="256" r="240" fill="#ffffff"/>
                <circle cx="256" cy="256" r="200" fill="#1A237E"/>
                <rect x="140" y="170" width="232" height="180" rx="30" fill="#ECF0F1"/>
                <rect x="180" y="210" width="40" height="40" rx="10" fill="#4CAF50"/>
                <rect x="292" y="210" width="40" height="40" rx="10" fill="#4CAF50"/>
            </svg>
            <span>Instalar Aplicación en Dispositivo</span>
        </button>
    </div>
</div>

<div class="top-nav">
    <input type="text" id="inputBusqueda" onkeyup="buscarContenido()" placeholder="🔍 Buscar actividad...">
    <div class="menu-usuario-top">
        <span onclick="irInicio()" style="cursor:pointer">🏠 Inicio</span> | 
        <span onclick="accederTrafico()" style="cursor:pointer; color: var(--naranja);">📊 Tráfico</span>
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
    <img src="https://raw.githubusercontent.com/Brimar26/portada/main/portadamate.png" alt="Portada MateVida" style="max-width:100%; border-radius:20px; display: block; margin: 20px auto;">   
</div>

<div id="visor-pro">
    <div class="barra-visor" translate="no">
        <strong id="titulo-juego-actual">Cargando...</strong>
        <div class="grupo-botones">
            <button onclick="alternarMusica()" id="btn-musica" class="btn-accion" style="background: #9b59b6;">
                <span>🎵</span> <span id="txt-musica">MÚSICA: OFF</span>
            </button>
            <button onclick="darMeGusta()" class="btn-accion" style="background: #e67e22;">
                <span>👍</span> <span id="txt-megusta">ME GUSTA (0)</span>
            </button>
            <button onclick="abrirModalMensaje()" class="btn-accion" style="background: #1abc9c;">
                <span>💬</span> <span>MENSAJE</span>
            </button>
            <button onclick="reiniciarJuego()" class="btn-accion" style="background: #27ae60;">
                <span>🔄</span> <span>REINICIAR</span>
            </button>
            <button onclick="compartirJuego()" class="btn-accion" style="background: var(--azul);"><span>🔗</span> <span>COMPARTIR</span></button>
            <button onclick="mostrarQR()" class="btn-accion" style="background: var(--amarillo); color: black;"><span>📱</span> <span>QR</span></button>
            <button onclick="cerrarSoftware()" class="btn-accion" style="background:#e74c3c;"><span>✖</span> <span>CERRAR</span></button>
        </div>
    </div>
    <iframe id="iframe-software" src="" style="width:100%; height:calc(100% - 55px); border:none; background: white;"></iframe>
</div>

<div id="overlay" onclick="cerrarTodosModales()"></div>

<div id="modal-qr">
    <h3>Escanea para jugar</h3>
    <div id="qrcode" style="display: flex; justify-content: center; margin: 15px;"></div>
    <button onclick="cerrarTodosModales()" class="btn-accion" style="background: #333; margin: 0 auto; display: block; width: 100px; justify-content: center;">Cerrar</button>
</div>

<div id="modal-mensaje">
    <h3 style="margin-top:0; color:var(--azul);">💬 Enviar Mensaje Privado</h3>
    <p style="font-size:12px; color:#666;">Este mensaje solo lo podrás ver tú y el administrador.</p>
    <textarea id="textoMensajePrivado" placeholder="Escribe tu duda o mensaje para el maestro aquí..."></textarea>
    <div style="display:flex; gap:10px;">
        <button onclick="cerrarTodosModales()" class="btn-accion" style="background:#95a5a6; flex:1; justify-content:center;">Cancelar</button>
        <button onclick="enviarMensajePrivado()" class="btn-accion" style="background:var(--verde); flex:1; justify-content:center;">Enviar 🚀</button>
    </div>
</div>

<script>
let urlActual = "";
let nombreActual = "";
let usuarioActualGlobal = "Invitado Anónimo"; 

if ('serviceWorker' in navigator) {
    const swCode = `
        self.addEventListener('install', (e) => self.skipWaiting());
        self.addEventListener('activate', (e) => e.waitUntil(self.clients.claim()));
        self.addEventListener('fetch', (e) => e.respondWith(fetch(e.request).catch(() => new Response('Conectado a MateVida Digital'))));
    `;
    const blob = new Blob([swCode], { type: 'application/javascript' });
    const swURL = URL.createObjectURL(blob);
    navigator.serviceWorker.register(swURL).catch(err => console.log("SW Error:", err));
}

let eventoInstalacion = null;
window.addEventListener('beforeinstallprompt', (e) => {
    e.preventDefault();
    eventoInstalacion = e;
    const btnInstalar = document.getElementById('btnInstalarPWA');
    if (btnInstalar) {
        btnInstalar.style.background = 'var(--verde)';
        btnInstalar.style.boxShadow = '0 5px 0px #388E3C';
        btnInstalar.querySelector('span').innerHTML = '✅ ¡Instalar MateVida en el Dispositivo!';
    }
});

function ejecutarInstalacion() {
    if (eventoInstalacion) {
        eventoInstalacion.prompt();
        eventoInstalacion.userChoice.then((choiceResult) => {
            eventoInstalacion = null;
        });
    } else {
        alert("¡MateVida Digital está lista!\n\nSi el botón no se activa automáticamente en tu navegador:\n1. En Android: Tres puntos -> 'Instalar aplicación'.\n2. En iPhone: Compartir -> 'Agregar a inicio'.");
    }
}

const CONTRASEÑA_ADMIN = "admin123"; 

function ingresarAApp() {
    let nombre = document.getElementById('nombreUsuarioInput').value.trim();
    if (nombre === "") {
        alert("Por favor, introduce un nombre o usuario válido.");
        return;
    }
    usuarioActualGlobal = nombre; 
    let historico = JSON.parse(localStorage.getItem('trafico_usuarios')) || [];
    historico.push({ nombre: nombre, hora: new Date().toLocaleString(), accion: "Ingresó al Portal Principal" });
    localStorage.setItem('trafico_usuarios', JSON.stringify(historico));
    document.getElementById('bloqueo-inicio').style.display = 'none';
}

function accederTrafico() {
    let psw = prompt("SÓLO ADMINISTRADOR: Introduce la contraseña para ver el tráfico y mensajes:");
    if (psw === CONTRASEÑA_ADMIN) {
        mostrarPanelTrafico();
    } else if (psw !== null) {
        alert("Contraseña incorrecta. Acceso denegado.");
    }
}

function mostrarPanelTrafico() {
    let historico = JSON.parse(localStorage.getItem('trafico_usuarios')) || [];
    let mensajes = JSON.parse(localStorage.getItem('mensajes_privados')) || [];
    
    let listaHTML = historico.length === 0 
        ? "<p>No hay registros de ingresos todavía.</p>" 
        : `<ul style="text-align:left; display:inline-block; margin:10px auto; max-height: 200px; overflow-y: auto; width: 100%;">` + 
          historico.map(u => `<li>[${u.hora}] <strong>${u.nombre}</strong> -> <span style="color:var(--azul)">${u.accion}</span></li>`).join('') + 
          `</ul>`;

    let mensajesHTML = mensajes.length === 0
        ? "<p>No hay mensajes privados guardados.</p>"
        : `<ul style="text-align:left; display:inline-block; margin:10px auto; max-height: 200px; overflow-y: auto; width: 100%; background:#fff; padding:10px; border-radius:10px; box-sizing:border-box;">` + 
          mensajes.map(m => `<li>[${m.hora}] <strong>${m.remitente}</strong> (En: ${m.actividad}): <span style="color:#27ae60">${m.mensaje}</span></li>`).join('') + 
          `</ul>`;

    document.getElementById('pantalla').innerHTML = `
        <h2 style="color:var(--azul)">📊 Panel de Tráfico Permanente e Historial</h2>
        <div style="background:#f9f9f9; padding:20px; border-radius:15px; display:inline-block; width: 100%; max-width: 600px; box-sizing:border-box;">
            <p><strong>Total de registros históricos:</strong> ${historico.length}</p>
            ${listaHTML}
            <hr style="border:1px solid #ddd; margin:20px 0;">
            <h4 style="color:#1abc9c; margin:5px 0;">💬 Mensajes Privados Recibidos (Sólo Admin):</h4>
            ${mensajesHTML}
        </div>`;
}

function lanzarSoftware(url, nombre) {
    urlActual = url;
    nombreActual = nombre;
    document.getElementById('titulo-juego-actual').innerText = nombre;
    const iframe = document.getElementById('iframe-software');
    iframe.src = url;
    
    // Cargar contador de Me Gusta
    actualizarContadorLikesPantalla();

    document.getElementById('visor-pro').style.display = 'block';
    document.body.style.overflow = 'hidden'; 

    let historico = JSON.parse(localStorage.getItem('trafico_usuarios')) || [];
    historico.push({ nombre: usuarioActualGlobal, hora: new Date().toLocaleString(), accion: `Abrió la actividad: "${nombre}"` });
    localStorage.setItem('trafico_usuarios', JSON.stringify(historico));
}

/* --- NUEVA LOGICA: REINICIAR ACTIVIDAD --- */
function reiniciarJuego() {
    if (urlActual !== "") {
        const iframe = document.getElementById('iframe-software');
        iframe.src = urlActual; // Recarga el iframe devolviendo al alumno al inicio del juego
    }
}

/* --- NUEVA LOGICA: CONTADOR ME GUSTA --- */
function darMeGusta() {
    let likesData = JSON.parse(localStorage.getItem('matevida_likes')) || {};
    if (!likesData[nombreActual]) {
        likesData[nombreActual] = 0;
    }
    likesData[nombreActual] += 1;
    localStorage.setItem('matevida_likes', JSON.stringify(likesData));
    actualizarContadorLikesPantalla();

    let historico = JSON.parse(localStorage.getItem('trafico_usuarios')) || [];
    historico.push({ nombre: usuarioActualGlobal, hora: new Date().toLocaleString(), accion: `Le dio 'Me Gusta' a: "${nombreActual}"` });
    localStorage.setItem('trafico_usuarios', JSON.stringify(historico));
}

function actualizarContadorLikesPantalla() {
    let likesData = JSON.parse(localStorage.getItem('matevida_likes')) || {};
    let totalLikes = likesData[nombreActual] || 0;
    document.getElementById('txt-megusta').innerText = `ME GUSTA (${totalLikes})`;
}

/* --- NUEVA LOGICA: MENSAJES PRIVADOS --- */
function abrirModalMensaje() {
    document.getElementById('textoMensajePrivado').value = "";
    document.getElementById('modal-mensaje').style.display = 'block';
    document.getElementById('overlay').style.display = 'block';
}

function enviarMensajePrivado() {
    let texto = document.getElementById('textoMensajePrivado').value.trim();
    if (texto === "") {
        alert("Escribe un mensaje antes de enviar.");
        return;
    }
    
    let mensajes = JSON.parse(localStorage.getItem('mensajes_privados')) || [];
    mensajes.push({
        remitente: usuarioActualGlobal,
        actividad: nombreActual,
        hora: new Date().toLocaleString(),
        mensaje: texto
    });
    localStorage.setItem('mensajes_privados', JSON.stringify(mensajes));
    
    alert("💬 Tu mensaje ha sido enviado en privado al Administrador.");
    cerrarTodosModales();
}

function cerrarTodosModales() {
    document.getElementById('modal-qr').style.display = 'none';
    document.getElementById('modal-mensaje').style.display = 'none';
    document.getElementById('overlay').style.display = 'none';
}

/* --- CONTROL DE MUSICA Y APAGADO AUTOMÁTICO AL SALIR --- */
function cerrarSoftware() {
    // 1. Apagar automáticamente la música al salir de la actividad
    const reproductor = document.getElementById('musica-fondo');
    if (!reproductor.paused) {
        reproductor.pause();
    }
    document.getElementById('txt-musica').innerText = "MÚSICA: OFF";
    document.getElementById('btn-musica').style.background = "#9b59b6";

    // 2. Ocultar visor y limpiar iframe
    document.getElementById('visor-pro').style.display = 'none';
    document.getElementById('iframe-software').src = ""; 
    document.body.style.overflow = 'auto';
    urlActual = "";
}

async function compartirJuego() {
    const shareData = { title: nombreActual, text: `¡Mira este juego en MateVida Digital: ${nombreActual}!`, url: urlActual };
    try {
        if (navigator.share) { await navigator.share(shareData); } 
        else { await navigator.clipboard.writeText(urlActual); alert("Enlace copiado al portapapeles"); }
    } catch (err) { console.log("Error al compartir", err); }
}

function mostrarQR() {
    document.getElementById('qrcode').innerHTML = ""; 
    new QRCode(document.getElementById("qrcode"), { text: urlActual, width: 180, height: 180 });
    document.getElementById('modal-qr').style.display = 'block';
    document.getElementById('overlay').style.display = 'block';
}

function buscarContenido() {
    let input = document.getElementById('inputBusqueda').value.toLowerCase();
    let items = document.getElementsByClassName('item-lista');
    for (let i = 0; i < items.length; i++) {
        let texto = items[i].innerText.toLowerCase();
        items[i].style.display = texto.includes(input) ? "flex" : "none";
    }
}

function irInicio() { 
    document.getElementById('pantalla').innerHTML = `
        <h2>Entrena tu Mente, Domina los Números</h2>
        <p>Selecciona una categoría arriba para comenzar a aprender.</p>
        <img src="https://raw.githubusercontent.com/Brimar26/portada/main/portadamate.png" alt="Portada MateVida" style="max-width:100%; border-radius:20px; display: block; margin: 20px auto;">
    `;
}

function alternarMusica() {
    const reproductor = document.getElementById('musica-fondo');
    const botonTexto = document.getElementById('txt-musica');
    const botonContenedor = document.getElementById('btn-musica');
    let historico = JSON.parse(localStorage.getItem('trafico_usuarios')) || [];

    if (reproductor.paused) {
        reproductor.volume = 0.15;
        reproductor.play().then(() => {
            botonTexto.innerText = "MÚSICA: ON";
            botonContenedor.style.background = "#2ecc71";
            historico.push({ nombre: usuarioActualGlobal, hora: new Date().toLocaleString(), accion: "Activó música ambiental" });
            localStorage.setItem('trafico_usuarios', JSON.stringify(historico));
        }).catch(error => console.log("Error de interacción de audio", error));
    } else {
        reproductor.pause();
        botonTexto.innerText = "MÚSICA: OFF";
        botonContenedor.style.background = "#9b59b6";
        historico.push({ nombre: usuarioActualGlobal, hora: new Date().toLocaleString(), accion: "Pausó música ambiental" });
        localStorage.setItem('trafico_usuarios', JSON.stringify(historico));
    }
}

function cargarSeccion(tipo) {
    const pantalla = document.getElementById('pantalla');
    let html = "";

    if (tipo === 'juegos') {
        html = `
            <h2 style="color:var(--verde)">🎮 Panel de Actividades</h2>
            <div class="grid-contenido">
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Carrera-de-Operaciones/', 'Carrera Operaciones')">
                    <div style="font-size:40px">🏎️</div><h3>Carrera Operaciones</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Operaciones-Matem-ticas/', 'Operaciones Matemáticas')">
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
                    <div style="font-size:40px">🛒</div><h3>Compras</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/DADOS-M-GICOS/', 'DADOS')">
                    <div style="font-size:40px">🎮</div><h3>DADOS</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Matecarrera/', 'Matecarrera')">
                    <div style="font-size:40px">🏎</div><h3>Matecarrera</h3>
                </div>
                 <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/La-escuela/', 'La escuela')">
                    <div style="font-size:40px">🏫</div><h3>La escuela</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Ruleta-Tablas-y-DIvisiones/', 'Tablas y Divisiones')">
                    <div style="font-size:40px">🎡</div><h3>Tablas y Divisiones</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Escuela-Matematica-Ruleta/', 'Escuela Mate - Ruleta')">
                    <div style="font-size:40px">🏫</div><h3>Escuela Mate - Ruleta</h3>
                </div>
                 <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Tablas-de-Multiplicar-Pro/', 'Tablas de Multiplicar Pro')">
                    <div style="font-size:40px">🙋‍♂️</div><h3>Tablas de Multiplicar Pro</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Nivel-Pali/', 'NIVEL PALI')">
                    <div style="font-size:40px">🅿️</div><h3>NIVEL PALI</h3>
                </div>
                 <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Mate-Aventura-Espacial-/', 'Mate Aventura Espacial')">
                    <div style="font-size:40px">🚀</div><h3>Mate Aventura Espacial</h3>
                </div>
                 <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/El-Mercado/', 'El Mercado')">
                    <div style="font-size:40px">🛍️</div><h3>El Mercado</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/Desafio-Total/', 'Desafìo Total')">
                    <div style="font-size:40px">🎓</div><h3>Desafìo Total</h3>
                </div>


                <div class="item-lista" onclick="lanzarSoftware('https://brimar26.github.io/tablas-de-multiplicar/', 'MATEBLAS')">
                    <div style="font-size:40px">🤖✖️</div><h3>MATEBLAS</h3>
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
                <div class="item-lista" onclick="lanzarSoftware('https://www.youtube.com/embed/otatgqU8o0w', 'Matemática divertida')">
                    <img src="https://img.youtube.com/vi/otatgqU8o0w/mqdefault.jpg" width="100%" style="border-radius:10px; margin-bottom:10px;">
                    <h3>Matemática divertida</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://www.youtube.com/embed/yyKkL0R59g0', 'Aprende a dividir')">
                    <img src="https://img.youtube.com/vi/yyKkL0R59g0/mqdefault.jpg" width="100%" style="border-radius:10px; margin-bottom:10px;">
                    <h3>Aprende a dividir</h3>
                </div>
                <div class="item-lista" onclick="lanzarSoftware('https://www.youtube.com/embed/WBqXpj1_96g', 'Operaciones')">
                    <img src="https://img.youtube.com/vi/WBqXpj1_96g/mqdefault.jpg" width="100%" style="border-radius:10px; margin-bottom:10px;">
                    <h3>Operaciones</h3>
                </div>
            </div>`;
    }
    else if (tipo === 'fichas') {
        html = `
            <h2 style="color:var(--amarillo)">📚 Fichas e Imprimibles</h2>
            <div class="grid-contenido">
                <a href="https://web.seducoahuila.gob.mx/biblioweb/upload/operaciones-y-problemas-3c2ba-de-primaria%20(1).pdf" target="_blank" class="item-lista" onclick="registrarEnlaceExterno('Ficha: Operaciones y Problemas')">
                    <div style="font-size:40px">🧮</div><h3>Operaciones y Problemas</h3>
                </a>
                <a href="https://www.jica.go.jp/Resource/project/elsalvador/004/materials/ku57pq00003u6zom-att/cuaderno_ejercicios_primaria_05.pdf" target="_blank" class="item-lista" onclick="registrarEnlaceExterno('Ficha: Cuaderno de Ejercicios')">
                    <div style="font-size:40px">📓</div><h3>Cuaderno de Ejercicios</h3>
                </a>
                <a href="https://www.mamutmatematicas.com/ejercicios/tabla-orden-operaciones.php" target="_blank" class="item-lista" onclick="registrarEnlaceExterno('Ficha: Orden de Operaciones')">
                    <div style="font-size:40px">⚖️</div><h3>Orden de Operaciones</h3>
                </a>
                <a href="https://arbolabc.com/juegos-tablas-de-multiplicar/tablas-imprimibles/operaciones-tabla-del-7" target="_blank" class="item-lista" onclick="registrarEnlaceExterno('Ficha: Tablas de Multiplicar')">
                    <div style="font-size:40px">✖️</div><h3>Tablas de Multiplicar</h3>
                </a>
            </div>`;
    }
    else if (tipo === 'recursos') {
        html = `
            <h2 style="color:var(--naranja)">👥 Sección de Recursos</h2>
            <div class="grid-contenido">
                <div class="item-lista">
                    <div style="font-size:40px">🏠</div>
                    <h3>Guía para Padres</h3>
                    <a href='https://gu-a-para-padres.tiiny.site/' target="_blank" style="margin-top:10px; color:var(--azul);" onclick="registrarEnlaceExterno('Menú: Guía para Padres')">Entrar al Menú</a>
                </div>
                <div class="item-lista">
                    <div style="font-size:40px">👤</div>
                    <h3>Guía para Estudiantes</h3>
                    <a href='https://www.pdffiller.com/s/1LObffqZo7' target="_blank" style="margin-top:10px; color:var(--azul);" onclick="registrarEnlaceExterno('Menú: Guía para Estudiantes')">Entrar al Menú</a>
                </div>
                <div class="item-lista">
                    <div style="font-size:40px">🎖️</div>
                    <h3>Guía para Docentes</h3>
                    <a href='https://www.pdffiller.com/s/ULtGifon' target="_blank" style="margin-top:10px; color:var(--azul);" onclick="registrarEnlaceExterno('Menú: Guía para Docentes')">Entrar al Menú</a>
                </div>
            </div>`;
    }
    pantalla.innerHTML = html;
}

function registrarEnlaceExterno(nombreEnlace) {
    let historico = JSON.parse(localStorage.getItem('trafico_usuarios')) || [];
    historico.push({ nombre: usuarioActualGlobal, hora: new Date().toLocaleString(), accion: `Abrió enlace externo: "${nombreEnlace}"` });
    localStorage.setItem('trafico_usuarios', JSON.stringify(historico));
}
</script>
</body>
</html>
