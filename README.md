<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Menú de Juego</title>
  <style>
    /* Reset total para que no aparezca nada de Blogger */
    html, body {
      margin: 0 !important;
      padding: 0 !important;
      width: 100% !important;
      height: 100% !important;
      overflow: hidden !important;
      font-family: Arial, sans-serif;
      background: black;
    }
    header, footer, nav, .post, .post-body, .post-title, .entry-title,
    .comments, #comments, .comment-form, .blog-feeds, .search,
    .PopularPosts, .related-posts, .sidebar, .blog-pager, .date-header {
      display: none !important;
    }

    /* Fondo de video */
    .video-background {
      position: fixed;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      overflow: hidden;
    }
    .video-background iframe {
      width: 100%;
      height: 100%;
      border: none;
    }

    /* Menú superior */
    .menu {
      position: absolute;
      top: 15px;
      left: 0;
      width: 100%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0 20px;
    }
    .titulo {
      font-size: 22px;
      font-weight: bold;
      color: white;
      text-shadow: 2px 2px 5px black;
    }

    /* Botones */
    .btn {
      padding: 14px 18px;
      border: none;
      border-radius: 50%; /* redondos */
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      text-decoration: none;
      color: white;
      transition: 0.3s;
      display: inline-flex;
      justify-content: center;
      align-items: center;
      width: 60px;
      height: 60px;
      text-align: center;
    }
    .btn:hover { transform: scale(1.1); }

    /* Colores */
    .tienda { background: #e91e63; }
    .whatsapp { background: #4caf50; }
    .sonido { background: #ff9800; }
    .b { background: #2196f3; }
    .c { background: #9c27b0; }
    .p { background: #009688; }
    .d { background: #3f51b5; }
    .jugar { background: #f44336; }

    /* Menú inferior */
    .menu-bottom {
      position: absolute;
      bottom: 20px;
      width: 100%;
      display: flex;
      justify-content: space-around;
      align-items: center;
    }

    /* Globo de diálogo */
    .bubble {
      position: absolute;
      bottom: 120px;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(255, 255, 255, 0.85);
      padding: 10px 18px;
      border-radius: 25px;
      font-size: 18px;
      font-weight: bold;
      color: #333;
      max-width: 80%;
      text-align: center;
      box-shadow: 0px 4px 10px rgba(0,0,0,0.3);
      opacity: 0;
      transition: opacity 1s ease;
    }
    .bubble.show { opacity: 1; }
  </style>
</head>
<body>

  <!-- Fondo de video Vimeo -->
  <div class="video-background">
    <iframe 
      src="https://player.vimeo.com/video/1121989438?autoplay=1&loop=1&muted=1&background=1" 
      frameborder="0" 
      allow="autoplay; fullscreen" 
      title="Fondo animado">
    </iframe>
  </div>

  <!-- Globo de diálogo del bebé -->
  <div id="bubble" class="bubble">¡Hola mami!</div>

  <!-- Menú superior -->
  <div class="menu">
    <a href="https://www.tiktok.com/@iaveleztati" target="_blank" class="btn tienda">🛒</a>
    <div class="titulo">Miguel Ángel</div>
    <a href="https://wa.me/ais/896235743051286?s=5" target="_blank" class="btn whatsapp">💬</a>
    <button class="btn sonido" onclick="playSonido()">🔊</button>
  </div>

  <!-- Botones inferiores -->
  <div class="menu-bottom">
    <a href="https://adcdavavavvsv.blogspot.com/2025/09/bano.html" target="_blank" class="btn b">B</a>
    <a href="https://adcdavavavvsv.blogspot.com/2025/09/cosina.html" target="_blank" class="btn c">C</a>
    <a href="https://adcdavavavvsv.blogspot.com/2025/09/patio.html" target="_blank" class="btn p">P</a>
    <a href="https://adcdavavavvsv.blogspot.com/2025/09/dormitorio.html" target="_blank" class="btn d">D</a>
    <a href="https://2559730.playcode.io" target="_blank" class="btn jugar">🎮</a>
  </div>

  <!-- Audio -->
  <audio id="musica">
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  </audio>

  <script>
    // Sonido
    function playSonido() {
      const musica = document.getElementById("musica");
      musica.play();
    }

    // Frases del bebé
    const frases = [
      "¡Hola mami!",
      "¿Jugamos un rato?",
      "Tengo hambre 😋",
      "Quiero dormir 💤",
      "¿Dónde está mi osito?",
      "¡Vamos al patio! 🌳",
      "Mami, te quiero ❤️",
      "¿Me lees un cuento?",
      "¡Cucú tras! 🙈",
      "Vamos a la cocina 🍪",
      "Quiero bañarme 🛁",
      "Mami, dame un abrazo 🤗",
      "Estoy feliz 🎉",
      "Quiero cantar 🎶",
      "¡Soy un campeón! 🏆"
    ];

    let index = 0;
    const bubble = document.getElementById("bubble");

    function mostrarFrase() {
      bubble.classList.remove("show");
      setTimeout(() => {
        bubble.textContent = frases[index];
        bubble.classList.add("show");
        index = (index + 1) % frases.length;
      }, 500);
    }

    setInterval(mostrarFrase, 4000);
    mostrarFrase(); // primera frase al inicio
  </script>
</body>
</html>

