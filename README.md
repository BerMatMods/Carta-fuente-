
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
  <title>Te amo Con Todo Mi Corazon</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.2/css/bootstrap.min.css">
  <link href="https://fonts.googleapis.com/css?family=Fredericka+the+Great|Lovers+Quarrel" rel="stylesheet">
  <style>
    /* Fondo general con más saturación */
    body {
      background-color: #ffecf9;
      margin: 0;
      overflow: hidden;
      font-family: 'Lovers Quarrel', cursive;
      animation: beat-back 0.8s infinite alternate;
      user-select: none;
    }

    @keyframes beat-back {
      0% { background-color: #ffecf9; }
      100% { background-color: #ffb6d9; }
    }

    /* --- PANTALLA DE BLOQUEO --- */
    #lockScreen {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #ffd6e7, #ffb6c1);
      z-index: 9999;
      display: flex;
      justify-content: center;
      align-items: center;
      animation: fadeIn 0.9s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .lock-box {
      background: white;
      width: 88%;
      max-width: 480px;
      padding: 35px;
      border-radius: 30px;
      box-shadow: 0 12px 35px rgba(230, 0, 115, 0.5);
      text-align: center;
      position: relative;
      border: 5px solid #e60073;
      animation: popIn 0.7s ease-out;
      transform: scale(1);
      transition: transform 0.2s;
    }

    .lock-box:hover {
      transform: scale(1.02);
    }

    @keyframes popIn {
      0% { transform: scale(0.8); opacity: 0; }
      70% { transform: scale(1.08); }
      100% { transform: scale(1); opacity: 1; }
    }

    /* Fuente normal en bloqueo */
    .lock-box h2,
    .lock-box p,
    .btn-follow {
      font-family: 'Segoe UI', Arial, sans-serif;
      color: #c00;
    }

    .lock-box h2 {
      font-size: 1.9rem;
      margin-bottom: 18px;
      font-weight: bold;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.1);
    }

    .lock-box p {
      font-size: 1.25rem;
      color: #99004d;
      margin: 15px 0;
      line-height: 1.6;
    }

    .tiktok-link {
      color: #e60073;
      font-weight: bold;
      text-decoration: underline;
      font-size: 1.3rem;
    }

    .btn-follow {
      margin-top: 22px;
      padding: 14px 30px;
      background: linear-gradient(45deg, #d6006f, #ff3399);
      color: white;
      border: none;
      border-radius: 35px;
      font-size: 1.4rem;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 6px 15px rgba(0,0,0,0.3);
      transition: all 0.3s;
      letter-spacing: 0.5px;
    }

    .btn-follow:hover {
      transform: scale(1.08);
      box-shadow: 0 8px 20px rgba(0,0,0,0.4);
      background: linear-gradient(45deg, #cc0066, #ff0080);
    }

    .close-btn {
      position: absolute;
      top: 15px;
      right: 15px;
      font-size: 1.9rem;
      color: #e60073;
      cursor: pointer;
      font-weight: bold;
      transition: all 0.3s;
      background: white;
      width: 36px;
      height: 36px;
      border-radius: 50%;
      line-height: 36px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.2);
    }

    .close-btn:hover {
      background: #ffe6f2;
      transform: rotate(90deg);
      color: #99004d;
    }

    /* --- MENSAJE DE ADVERTENCIA --- */
    #warningScreen {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.85);
      z-index: 10000;
      justify-content: center;
      align-items: center;
    }

    .warning-box {
      background: white;
      padding: 30px;
      border-radius: 25px;
      max-width: 430px;
      text-align: center;
      box-shadow: 0 12px 35px rgba(255, 0, 0, 0.4);
      border: 4px solid #ff3366;
    }

    .warning-box p {
      color: #c00;
      font-size: 1.2rem;
      margin-bottom: 25px;
      font-weight: bold;
      line-height: 1.5;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
    }

    /* --- CONTENIDO PRINCIPAL --- */
    #mainContent {
      display: none;
      opacity: 0;
      transition: opacity 2s ease;
    }

    #mainContent.show {
      display: block;
      opacity: 1;
    }

    .back {
      text-align: center;
      padding-top: 60px;
    }

    .topic {
      margin: 10px 0;
      font-family: 'Fredericka the Great', cursive;
      font-size: 3.4rem;
      color: #d6006f;
      text-shadow: 3px 3px 6px rgba(230, 0, 115, 0.6);
      letter-spacing: 1.5px;
      animation: pulse 1.5s infinite alternate;
    }

    @keyframes pulse {
      from { transform: scale(1); }
      to { transform: scale(1.05); }
    }

    .content-1,
    .content-2 {
      font-family: 'Lovers Quarrel', cursive;
      font-size: 2.5rem;
      margin: 22px 0;
      color: #c4005b;
      text-shadow: 2px 2px 5px rgba(255, 105, 180, 0.5);
    }

    .footer {
      margin: 65px 0 12px;
      font-family: 'Fredericka the Great', cursive;
      font-size: 3rem;
      color: #d6006f;
      text-shadow: 3px 3px 8px rgba(230, 0, 115, 0.7);
    }

    .love-box {
      display: inline-block;
      max-width: 520px;
      width: 88%;
      margin: 25px auto;
      padding: 25px;
      background: linear-gradient(145deg, #fff0f6, #ffd6eb);
      border: 4px solid #e60073;
      border-radius: 30px;
      box-shadow: 0 10px 25px rgba(230, 0, 115, 0.35);
      font-family: 'Lovers Quarrel', cursive;
      font-size: 1.6rem;
      color: #99004d;
      text-align: center;
      line-height: 1.7;
      position: relative;
      z-index: 2;
      animation: glow 2s infinite alternate;
    }

    @keyframes glow {
      from { box-shadow: 0 10px 25px rgba(230, 0, 115, 0.35); }
      to { box-shadow: 0 10px 35px rgba(230, 0, 115, 0.6); }
    }

    .love-box::before {
      content: "💬";
      position: absolute;
      top: -18px;
      left: 15px;
      font-size: 1.8rem;
    }

    .love-box::after {
      content: "💌";
      position: absolute;
      top: -18px;
      right: 15px;
      font-size: 1.8rem;
    }

    /* Corazón principal */
    .heart {
      margin: 35px auto;
      background-color: #ff3399;
      height: 110px;
      width: 110px;
      transform: rotate(-45deg);
      animation: beat 0.7s infinite alternate;
      border-radius: 6px;
      box-shadow: 0 0 25px rgba(255, 51, 153, 0.8);
    }

    .heart:after, .heart:before {
      content: "";
      position: absolute;
      width: 110px;
      height: 110px;
      background: #ff3399;
      border-radius: 50%;
      z-index: -1;
    }

    .heart:before { top: -55px; left: 0; }
    .heart:after { top: 0; left: 55px; }

    .heart:hover {
      transform: scale(1.35) rotate(-45deg);
      box-shadow: 0 0 35px rgba(255, 51, 153, 0.9);
    }

    @keyframes beat {
      0% { transform: scale(1) rotate(-45deg); }
      100% { transform: scale(0.85) rotate(-45deg); }
    }

    /* --- LLUVIA DE PALABRAS --- */
    .falling-word {
      position: absolute;
      top: -50px;
      pointer-events: none;
      z-index: 0;
      opacity: 0.95;
      font-weight: bold;
      text-shadow: 0 1px 4px rgba(0,0,0,0.4);
      animation: fall linear forwards;
    }

    @keyframes fall {
      0% { transform: translateY(-50px); opacity: 0; }
      10% { opacity: 1; }
      90% { opacity: 1; }
      100% { transform: translateY(110vh); opacity: 0; }
    }

    /* --- EXPLOSIONES DE CORAZONES --- */
    .heart-explosion {
      position: absolute;
      pointer-events: none;
      font-size: 20px;
      z-index: 100;
    }

    /* --- CRÉDITOS: más centrado y más pequeño --- */
    .credits-container {
      text-align: center;
      margin-top: 40px;
      width: 100%;
      display: flex;
      justify-content: center;
    }

    .credits-box {
      display: inline-block;
      background: linear-gradient(45deg, #ffe6f2, #ffccdd);
      padding: 8px 16px;
      border-radius: 18px;
      border: 2px solid #e60073;
      box-shadow: 0 3px 10px rgba(230, 0, 115, 0.3);
      font-family: 'Segoe UI', Arial, sans-serif;
      font-size: 0.95rem;
      color: #99004d;
      font-weight: bold;
      letter-spacing: 0.5px;
      animation: float 1.5s ease-in-out infinite alternate;
    }

    @keyframes float {
      0% { transform: translateY(0) scale(1); opacity: 0.9; }
      100% { transform: translateY(-5px) scale(1.02); opacity: 1; }
    }

    .credits-box::before, .credits-box::after {
      content: "✨";
      margin: 0 5px;
      font-size: 0.9em;
    }
  </style>
</head>
<body>

  <!-- === PANTALLA DE BLOQUEO === -->
  <div id="lockScreen">
    <div class="lock-box">
      <div class="close-btn" id="closeLock">×</div>
      <h2>🔒 ¡ACCESO RESTRINGIDO!</h2>
      <p>Para ver esta sorpresa romántica, debes seguir al creador en TikTok.</p>
      <p>Sigue a <a href="https://www.tiktok.com/@bermat_mods?_t=ZS-8zW8OhOQqOb&_r=1" target="_blank" class="tiktok-link">@bermat_mods</a></p>
      <button class="btn-follow" id="btnFollow">SEGUIR EN TIKTOK →</button>
    </div>
  </div>

  <!-- === PANTALLA DE ADVERTENCIA === -->
  <div id="warningScreen">
    <div class="warning-box">
      <p>⚠️ ADVERTENCIA<br>El sistema detectó que no siguió la cuenta de TikTok.<br>Por favor intenta más tarde.</p>
      <button class="btn-follow" id="btnFollowWarning">SEGUIR AHORA →</button>
    </div>
  </div>

  <!-- === CONTENIDO PRINCIPAL === -->
  <div id="mainContent">
    <!-- Botón de menú (tres rayitas) con enlace a WhatsApp -->
    <a href="https://wa.me/51930569195" target="_blank" class="menu-toggle" title="Escríbeme en WhatsApp">
      <span></span>
      <span></span>
      <span></span>
    </a>

    <div class="back text-center">
      <h1 class="topic">PARA MI MUJER<br>Mi Reina</h1>
      <p class="content-1">Que Afortunado soy de tenerte en mi vida</p>
      <p class="content-2">Me haces muy feliz mi amor</p>  
      <div class="heart"></div>
      <p class="footer">TE AMO CON TODO MI <br>CORAZON</p>
      <div class="love-box" id="loveMessage"></div>
    </div>

    <!-- Créditos mejorados -->
    <div class="credits-container">
      <div class="credits-box">
        by AnthZz Berrocal BerMatMods
      </div>
    </div>
  </div>

  <!-- Scripts corregidos -->
  <script>
    // Elementos del DOM
    const lockScreen = document.getElementById("lockScreen");
    const warningScreen = document.getElementById("warningScreen");
    const mainContent = document.getElementById("mainContent");
    const closeLock = document.getElementById("closeLock");
    const btnFollow = document.getElementById("btnFollow");
    const btnFollowWarning = document.getElementById("btnFollowWarning");

    // ✅ Corrección: Asegurar que la pantalla de bloqueo se muestre al cargar
    window.addEventListener("load", function () {
      if (localStorage.getItem("followedTikTok") === "true") {
        showMainContent();
      } else {
        lockScreen.style.display = "flex"; // Aseguramos que sea 'flex'
      }
    });

    // Función para seguir y desbloquear
    function followAndUnlock() {
      // Abre tu perfil de TikTok
      window.open("https://www.tiktok.com/@bermat_mods?_t=ZS-8zW8OhOQqOb&_r=1", "_blank");
      // Simulamos que siguió
      localStorage.setItem("followedTikTok", "true");
      // Mostramos el contenido después de regresar
      setTimeout(showMainContent, 600);
    }

    // ✅ Ambos botones "Seguir" funcionan
    btnFollow.addEventListener("click", followAndUnlock);
    btnFollowWarning.addEventListener("click", followAndUnlock);

    // ✅ Botón "X": cierra y muestra advertencia
    closeLock.addEventListener("click", function () {
      lockScreen.style.display = "none";
      warningScreen.style.display = "flex"; // Mostramos advertencia
    });

    // Mensaje de amor
    const longMessage = `Desde el primer momento en que te vi, supe que mi vida cambiaría para siempre 💖 Eres la luz que ilumina mis días más oscuros, el abrazo que necesito al final del día, el sueño que no quiero despertar 🌙 Cada sonrisa tuya es un regalo, cada palabra una melodía que acaricia mi alma 🎶 Te amo no solo por cómo eres, sino por cómo me haces sentir: completo, amado, en paz 💞 Eres mi refugio, mi motivación, mi razón de respirar ❤️ Prometo cuidarte, respetarte y amarte cada día más, porque contigo descubrí lo que es amar de verdad… eternamente 💍 Eres mi todo, mi amor, mi vida, mi universo entero 🌌`;

    const loveMessageElement = document.getElementById("loveMessage");

    function typeWriter() {
      let i = 0;
      const timer = setInterval(() => {
        if (i < longMessage.length) {
          loveMessageElement.innerHTML += longMessage.charAt(i);
          i++;
        } else {
          clearInterval(timer);
        }
      }, 30);
    }

    // Mostrar contenido principal
    function showMainContent() {
      lockScreen.style.display = "none";
      warningScreen.style.display = "none";
      mainContent.classList.add("show");
      setTimeout(() => {
        typeWriter();
        startFallingWords();
      }, 800);
    }

    // Lluvia de palabras románticas
    function startFallingWords() {
      const words = ['Amor', 'Eterno', 'Corazón', 'Alma', 'Mi Todo', 'Contigo', 'Nunca Sueltes', 'Siempre Tuyo', 'Te Amo', 'Sueño', 'Verdad', 'Magia', 'Destino'];
      const colors = ['#d6006f', '#ff3399', '#e60073', '#ff0080', '#cc0066'];

      setInterval(() => {
        const word = document.createElement('div');
        word.classList.add('falling-word');
        word.innerText = words[Math.floor(Math.random() * words.length)];
        word.style.left = Math.random() * 90 + 5 + 'vw';
        word.style.fontSize = (Math.random() * 25 + 22) + 'px';
        word.style.color = colors[Math.floor(Math.random() * colors.length)];
        word.style.fontFamily = "'Lovers Quarrel', cursive";
        word.style.animationDuration = (Math.random() * 6 + 4) + 's';
        document.body.appendChild(word);
        setTimeout(() => word.remove(), 7000);
      }, 450);
    }

    // Explosión de corazones al tocar
    document.body.addEventListener('click', function(e) {
      createHeartExplosion(e.clientX, e.clientY);
    });

    document.body.addEventListener('touchstart', function(e) {
      for (let i = 0; i < e.touches.length; i++) {
        const touch = e.touches[i];
        createHeartExplosion(touch.clientX, touch.clientY);
      }
    });

    function createHeartExplosion(x, y) {
      const hearts = ['❤️', '💕', '💖', '💗', '💘', '💓', '💝', '💞', '🧡', '💛', '🖤', '🥰'];
      for (let i = 0; i < 18; i++) {
        const heart = document.createElement('div');
        heart.classList.add('heart-explosion');
        heart.innerText = hearts[Math.floor(Math.random() * hearts.length)];
        heart.style.left = x + 'px';
        heart.style.top = y + 'px';
        heart.style.position = 'absolute';
        heart.style.transform = 'translate(-50%, -50%)';
        
        const angle = Math.random() * 360;
        const r = Math.random() * 120 + 60;
        const tx = r * Math.cos(angle * Math.PI / 180);
        const ty = r * Math.sin(angle * Math.PI / 180);

        heart.style.transition = 'transform 0.9s ease-out, opacity 0.9s ease';
        document.body.appendChild(heart);

        setTimeout(() => {
          heart.style.transform = `translate(-50%, -50%) translate(${tx}px, ${ty}px) rotate(${angle}deg)`;
          heart.style.opacity = 0;
        }, 10);

        setTimeout(() => heart.remove(), 900);
      }
    }
  </script>

</body>
</html>
