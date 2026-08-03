<!DOCTYPE html>
<html>
<head>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Press+Start+2P&display=swap');
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      background: #0a0a0f;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      font-family: 'Orbitron', monospace;
      overflow-x: hidden;
    }
    
    .container {
      max-width: 900px;
      padding: 40px 20px;
      text-align: center;
      position: relative;
    }
    
    /* EFEITO DE BRILHO NEON NO FUNDO */
    .glow-effect {
      position: absolute;
      top: -100px;
      left: 50%;
      transform: translateX(-50%);
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(123,47,190,0.15) 0%, rgba(0,212,255,0.05) 50%, transparent 70%);
      border-radius: 50%;
      filter: blur(60px);
      animation: pulseGlow 3s ease-in-out infinite;
      pointer-events: none;
      z-index: 0;
    }
    
    @keyframes pulseGlow {
      0%, 100% { opacity: 0.5; transform: translateX(-50%) scale(1); }
      50% { opacity: 1; transform: translateX(-50%) scale(1.2); }
    }
    
    /* TÍTULO PRINCIPAL */
    .title {
      font-size: 3.5rem;
      font-weight: 900;
      background: linear-gradient(135deg, #00D4FF 0%, #7B2FBE 50%, #00D4FF 100%);
      background-size: 300% 300%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: neonMove 4s ease-in-out infinite;
      text-shadow: 0 0 40px rgba(0,212,255,0.3);
      position: relative;
      z-index: 1;
      letter-spacing: 4px;
      margin-bottom: 10px;
    }
    
    @keyframes neonMove {
      0%, 100% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
    }
    
    .subtitle {
      font-family: 'Press Start 2P', monospace;
      font-size: 0.8rem;
      color: #00D4FF;
      opacity: 0.7;
      letter-spacing: 2px;
      margin-bottom: 30px;
      position: relative;
      z-index: 1;
      animation: blinkText 2s step-end infinite;
    }
    
    @keyframes blinkText {
      0%, 100% { opacity: 0.7; }
      50% { opacity: 0.2; }
    }
    
    /* BORDA DECORATIVA */
    .border-neon {
      border: 2px solid rgba(0,212,255,0.2);
      border-radius: 20px;
      padding: 30px;
      position: relative;
      z-index: 1;
      background: rgba(10,10,15,0.8);
      backdrop-filter: blur(10px);
      box-shadow: 
        0 0 30px rgba(123,47,190,0.2),
        inset 0 0 30px rgba(0,212,255,0.05);
      margin-bottom: 30px;
    }
    
    /* SATURNO ASCII ART - VERSÃO DETALHADA */
    .saturn-container {
      position: relative;
      display: inline-block;
      margin: 20px 0;
      animation: floatSaturn 6s ease-in-out infinite;
    }
    
    @keyframes floatSaturn {
      0%, 100% { transform: translateY(0px) rotate(0deg); }
      50% { transform: translateY(-15px) rotate(5deg); }
    }
    
    .saturn-art {
      font-family: 'Courier New', monospace;
      font-size: 14px;
      line-height: 1.1;
      color: #7B2FBE;
      text-shadow: 0 0 20px rgba(123,47,190,0.5);
      white-space: pre;
      display: inline-block;
      animation: saturnGlow 3s ease-in-out infinite;
      letter-spacing: 1px;
    }
    
    .saturn-art .ring {
      color: #00D4FF;
      text-shadow: 0 0 30px rgba(0,212,255,0.6);
    }
    
    .saturn-art .planet {
      color: #FF6B35;
      text-shadow: 0 0 30px rgba(255,107,53,0.5);
    }
    
    .saturn-art .star {
      color: #FFD700;
      text-shadow: 0 0 20px rgba(255,215,0,0.4);
      animation: twinkle 2s ease-in-out infinite;
    }
    
    @keyframes saturnGlow {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.8; }
    }
    
    @keyframes twinkle {
      0%, 100% { opacity: 0.3; }
      50% { opacity: 1; }
    }
    
    /* LOGO PIXELADO */
    .pixel-logo {
      display: inline-block;
      font-family: 'Press Start 2P', monospace;
      font-size: 1.2rem;
      color: #00D4FF;
      background: rgba(0,212,255,0.05);
      border: 3px solid #7B2FBE;
      padding: 15px 30px;
      margin: 20px 0;
      image-rendering: pixelated;
      box-shadow: 
        0 0 20px rgba(123,47,190,0.3),
        inset 0 0 20px rgba(0,212,255,0.1);
      animation: pixelBorder 2s step-end infinite;
      border-radius: 8px;
    }
    
    @keyframes pixelBorder {
      0%, 100% { border-color: #7B2FBE; }
      50% { border-color: #00D4FF; }
    }
    
    .pixel-logo span {
      color: #FF6B35;
    }
    
    .pixel-logo .dot {
      color: #FFD700;
      animation: blinkDot 1s step-end infinite;
    }
    
    @keyframes blinkDot {
      0%, 100% { opacity: 1; }
      50% { opacity: 0; }
    }
    
    /* BOTÕES DE CONTATO */
    .contact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 15px;
      margin: 30px 0;
      position: relative;
      z-index: 1;
    }
    
    .contact-card {
      background: rgba(123,47,190,0.1);
      border: 2px solid rgba(0,212,255,0.2);
      padding: 18px 12px;
      border-radius: 12px;
      text-decoration: none;
      color: #fff;
      font-family: 'Orbitron', monospace;
      font-size: 0.8rem;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
      backdrop-filter: blur(5px);
    }
    
    .contact-card::before {
      content: '';
      position: absolute;
      top: -2px;
      left: -2px;
      right: -2px;
      bottom: -2px;
      background: linear-gradient(45deg, #7B2FBE, #00D4FF, #7B2FBE);
      background-size: 300% 300%;
      border-radius: 14px;
      z-index: -1;
      opacity: 0;
      transition: opacity 0.3s ease;
    }
    
    .contact-card:hover::before {
      opacity: 1;
      animation: borderGlow 2s ease infinite;
    }
    
    @keyframes borderGlow {
      0%, 100% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
    }
    
    .contact-card:hover {
      transform: translateY(-5px) scale(1.02);
      box-shadow: 0 10px 40px rgba(123,47,190,0.3);
      border-color: transparent;
    }
    
    .contact-card .icon {
      font-size: 1.8rem;
      display: block;
      margin-bottom: 5px;
    }
    
    .contact-card .label {
      font-size: 0.6rem;
      opacity: 0.6;
      margin-top: 3px;
    }
    
    .contact-card.instagram:hover { border-color: #E4405F; }
    .contact-card.email:hover { border-color: #D14836; }
    .contact-card.whatsapp:hover { border-color: #25D366; }
    
    /* FRASE DE EFEITO */
    .tagline {
      font-family: 'Press Start 2P', monospace;
      font-size: 0.7rem;
      color: rgba(255,255,255,0.6);
      margin: 25px 0;
      line-height: 1.8;
      letter-spacing: 1px;
      position: relative;
      z-index: 1;
    }
    
    .tagline strong {
      background: linear-gradient(135deg, #00D4FF, #7B2FBE);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    
    /* ESTRELINHAS DECORATIVAS */
    .stars {
      position: fixed;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      pointer-events: none;
      z-index: -1;
      overflow: hidden;
    }
    
    .star {
      position: absolute;
      width: 2px;
      height: 2px;
      background: white;
      border-radius: 50%;
      animation: twinkleStar 3s ease-in-out infinite;
    }
    
    @keyframes twinkleStar {
      0%, 100% { opacity: 0.2; }
      50% { opacity: 1; }
    }
    
    /* RESPONSIVO */
    @media (max-width: 600px) {
      .title { font-size: 2rem; }
      .saturn-art { font-size: 10px; }
      .pixel-logo { font-size: 0.8rem; padding: 10px 20px; }
      .contact-grid { grid-template-columns: 1fr; }
      .border-neon { padding: 15px; }
    }
  </style>
</head>
<body>
  
  <!-- ESTRELAS DE FUNDO -->
  <div class="stars" id="stars"></div>
  
  <!-- EFEITO DE BRILHO -->
  <div class="glow-effect"></div>
  
  <div class="container">
    
    <div class="border-neon">
      
      <!-- TÍTULO -->
      <h1 class="title">ROMNETT STUDIOS</h1>
      <div class="subtitle">✦ PIXEL · SPACE · FUTURE ✦</div>
      
      <!-- LOGO PIXELADO -->
      <div class="pixel-logo">
        <span>R</span>O<span>M</span>N<span>E</span>T<span>T</span> <span class="dot">✦</span> <span>S</span>T<span>U</span>D<span>I</span>O<span>S</span>
      </div>
      
      <!-- SATURNO DETALHADO -->
      <div class="saturn-container">
        <pre class="saturn-art">
              <span class="star">✧</span>         <span class="star">✧</span>         <span class="star">✧</span>
                    <span class="ring">     .--..--.     </span>
                   <span class="ring">  .-'      '-.  </span>
                  <span class="ring">.'            '. </span>
          <span class="star">✧</span>    <span class="ring">/    .--..--.    \</span>    <span class="star">✧</span>
               <span class="ring">|   /  .-.  \   |</span>
               <span class="ring">|  |  |   |  |  |</span>
               <span class="ring">|   \  '-'  /   |</span>
          <span class="star">✧</span>    <span class="ring">\    '--'    /</span>    <span class="star">✧</span>
                  <span class="ring"> '.          .'</span>
                   <span class="ring">  '-.____.-'</span>
                    <span class="ring">     '--'     </span>
              <span class="star">✧</span>         <span class="star">✧</span>         <span class="star">✧</span>
        </pre>
      </div>
      
      <!-- FRASE -->
      <div class="tagline">
        <strong>Criando experiências digitais</strong><br>
        que unem design, tecnologia e performance.
      </div>
      
    </div>
    
    <!-- CONTATOS -->
    <div class="contact-grid">
      <a href="https://www.instagram.com/romnettstudios/" target="_blank" class="contact-card instagram">
        <span class="icon">📸</span>
        @romnettstudios
        <span class="label">Instagram</span>
      </a>
      
      <a href="mailto:romnettstudios@gmail.com" class="contact-card email">
        <span class="icon">✉️</span>
        romnettstudios@gmail.com
        <span class="label">Email</span>
      </a>
      
      <a href="https://wa.me/5515997920703" target="_blank" class="contact-card whatsapp">
        <span class="icon">💬</span>
        (15) 99792-0703
        <span class="label">WhatsApp</span>
      </a>
    </div>
    
    <!-- RODAPÉ -->
    <div style="margin-top: 30px; font-size: 0.6rem; opacity: 0.3; font-family: 'Courier New', monospace;">
      ⚡ ROMNETT STUDIOS · 2026 · FEITO COM PIXELS E NEON ⚡
    </div>
    
  </div>
  
  <script>
    // CRIA ESTRELAS DE FUNDO
    const starsContainer = document.getElementById('stars');
    for (let i = 0; i < 80; i++) {
      const star = document.createElement('div');
      star.className = 'star';
      star.style.left = Math.random() * 100 + '%';
      star.style.top = Math.random() * 100 + '%';
      star.style.animationDelay = Math.random() * 5 + 's';
      star.style.animationDuration = (2 + Math.random() * 4) + 's';
      star.style.width = (1 + Math.random() * 3) + 'px';
      star.style.height = star.style.width;
      starsContainer.appendChild(star);
    }
  </script>
  
</body>
</html>
