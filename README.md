index.html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kerusso TV - Tu Fe en Movimiento</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
  <style>
    body { font-family: 'Montserrat', sans-serif; background:#0A1628; color:white; margin:0; }
    .text-gradient { background: linear-gradient(135deg, #D4AF37 0%, #FFF 50%, #D4AF37 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .glass-effect { background: rgba(15,31,56,0.7); backdrop-filter: blur(12px); border:1px solid rgba(212,175,55,0.2); padding:1rem; border-radius:1rem; }
    #video-en-vivo { width:100%; max-width:800px; border-radius:10px; margin-top:1rem; }
    .section { padding:4rem 2rem; }
    a { text-decoration:none; color:inherit; }
    nav { position:fixed; top:0; width:100%; background:rgba(10,22,40,0.85); backdrop-filter:blur(8px); z-index:50; padding:1rem 2rem; display:flex; justify-content:space-between; align-items:center; }
    nav a { margin-left:1rem; color:white; font-weight:500; }
    footer { padding:2rem; background:#0F1F38; text-align:center; margin-top:2rem; font-size:0.9rem; color:#aaa; }
  </style>
</head>
<body>

  <!-- Navbar -->
  <nav>
    <div class="logo font-serif text-2xl font-bold text-gradient">Kerusso TV</div>
    <div>
      <a href="#inicio">Inicio</a>
      <a href="#envivo">En Vivo</a>
      <a href="#programas">Programas</a>
      <a href="#horarios">Horarios</a>
      <a href="#nosotros">Nosotros</a>
    </div>
  </nav>

  <!-- Hero Section -->
  <section id="inicio" class="section text-center">
    <h1 class="text-5xl md:text-7xl font-serif font-bold">Tu Fe en <span class="text-gradient italic">Movimiento</span></h1>
    <p class="mt-4 text-gray-300">Transmisión cristiana las 24 horas. Mensajes de esperanza, alabanza y palabra viva.</p>
    <a href="#envivo" class="mt-6 inline-block bg-gradient-to-r from-gold-500 to-gold-600 text-navy-900 px-8 py-4 rounded-full font-bold">Ver Transmisión</a>
  </section>

  <!-- En Vivo -->
  <section id="envivo" class="section text-center">
    <h2 class="text-4xl font-serif font-bold mb-4">Canal <span class="text-gold-400">En Vivo</span></h2>
    <div class="glass-effect mx-auto max-w-3xl">
      <video id="video-en-vivo" controls autoplay></video>
    </div>
  </section>

  <!-- Programas -->
  <section id="programas" class="section">
    <h2 class="text-3xl font-bold mb-4 text-center">Nuestra Programación</h2>
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-4">
      <div class="glass-effect">Despertar con Dios - 6:00 AM</div>
      <div class="glass-effect">Alabanza Sin Fin - 9:00 AM</div>
      <div class="glass-effect">Familia en Cristo - 11:00 AM</div>
      <div class="glass-effect">Jóvenes de Impacto - 3:00 PM</div>
      <div class="glass-effect">Estudio Profundo - 6:00 PM</div>
      <div class="glass-effect">Noche de Milagros - 9:00 PM</div>
    </div>
  </section>

  <!-- Horarios -->
  <section id="horarios" class="section text-center">
    <h2 class="text-3xl font-bold mb-4">Horarios de Transmisión</h2>
    <p>Planifica tu día espiritual con nuestra programación</p>
  </section>

  <!-- Footer -->
  <footer>
    &copy; 2024 Kerusso TV - Todos los derechos reservados.
  </footer>

  <!-- HLS JS -->
  <script>
    const video = document.getElementById('video-en-vivo');
    const streamURL = "https://s.emisoras.tv:8081/kerussotv/index.m3u8";

    if(Hls.isSupported()) {
      const hls = new Hls();
      hls.loadSource(streamURL);
      hls.attachMedia(video);
      hls.on(Hls.Events.MANIFEST_PARSED, () => { video.play(); });
    } else if(video.canPlayType('application/vnd.apple.mpegurl')) {
      video.src = streamURL;
      video.addEventListener('loadedmetadata', () => { video.play(); });
    } else {
      alert("Tu navegador no soporta este stream HLS.");
    }
  </script>

</body>
</html>

