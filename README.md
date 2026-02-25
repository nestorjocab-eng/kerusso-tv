docs/index.html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Luz Eterna TV - En Vivo</title>
<script src="https://cdn.tailwindcss.com"></script>
<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
<style>
body { font-family: 'Montserrat', sans-serif; background-color:#0A1628; color:white; margin:0;}
.text-gradient { background: linear-gradient(135deg, #D4AF37 0%, #FFF 50%, #D4AF37 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent;}
.hero-bg { background: linear-gradient(135deg, #0A1628 0%, #162B4D 50%, #0F1F38 100%); min-height:100vh; display:flex; align-items:center; justify-content:center; flex-direction:column; padding-top:80px; }
.video-container { position:relative; width:100%; max-width:800px; aspect-ratio:16/9; background:#000; border-radius:1rem; overflow:hidden; margin:auto;}
video { width:100%; height:100%; object-fit:cover; border-radius:1rem;}
button { cursor:pointer; }
</style>
</head>
<body>

<!-- Hero -->
<section class="hero-bg text-center">
  <h1 class="text-5xl md:text-7xl font-bold mb-4 font-serif">Tu Fe en <span class="text-gradient italic">Movimiento</span></h1>
  <p class="text-gray-300 mb-8 text-xl max-w-2xl mx-auto">Transmisión cristiana 24 horas. Mensajes de esperanza y alabanza.</p>
  <a href="#envivo" class="bg-gradient-to-r from-yellow-500 to-yellow-600 text-navy-900 px-8 py-4 rounded-full font-bold text-lg hover:shadow-xl">Ver Transmisión</a>
</section>

<!-- En Vivo -->
<section id="envivo" class="py-20 bg-navy-800 text-center">
  <h2 class="text-4xl md:text-5xl font-bold mb-6 font-serif">Transmisión <span class="text-yellow-400">En Vivo</span></h2>
  <p class="text-gray-400 mb-8">Únete a nuestra comunidad en este momento. La palabra de Dios no tiene horario.</p>
  
  <div class="video-container mb-6">
    <video id="video" controls autoplay muted></video>
  </div>

  <h3 class="text-xl font-bold">Alabanza y Adoración Matutina</h3>
  <p class="text-gray-300">Con el Pastor Roberto Mendoza • 6:00 AM - 9:00 AM</p>
</section>

<!-- Footer -->
<footer class="bg-navy-900 border-t border-yellow-500/20 pt-8 pb-4 text-center text-gray-400">
  &copy; 2026 Luz Eterna TV. Todos los derechos reservados.
</footer>

<script>
const video = document.getElementById('video');
const videoSrc = 'https://s.emisoras.tv:8081/kerussotv/index.m3u8';

if(Hls.isSupported()) {
  const hls = new Hls();
  hls.loadSource(videoSrc);
  hls.attachMedia(video);
  hls.on(Hls.Events.MANIFEST_PARSED, function() {
    video.play();
  });
} else if (video.canPlayType('application/vnd.apple.mpegurl')) {
  video.src = videoSrc;
  video.addEventListener('loadedmetadata', function() {
    video.play();
  });
}
</script>

</body>
</html>
