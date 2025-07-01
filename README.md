
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Felipe - Hacker Profile</title>
  <style>
    /* Reset básico */
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      font-family: 'Courier New', Courier, monospace;
      color: #00ff00;
      background: #000;
    }

    body {
      background: #000;
      overflow-x: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      padding: 2rem;
    }

    /* Glitch texto principal */
    .glitch {
      position: relative;
      font-size: 3.5rem;
      font-weight: bold;
      letter-spacing: 0.15em;
      color: #0f0;
      animation: flicker 1.5s infinite;
      text-transform: uppercase;
    }
    .glitch::before,
    .glitch::after {
      content: attr(data-text);
      position: absolute;
      left: 0; top: 0;
      width: 100%; height: 100%;
      opacity: 0.8;
      clip: rect(0, 900px, 0, 0);
    }
    .glitch::before {
      left: 2px;
      text-shadow: -2px 0 red;
      animation: glitch-anim-1 2s infinite linear alternate-reverse;
    }
    .glitch::after {
      left: -2px;
      text-shadow: -2px 0 blue;
      animation: glitch-anim-2 3s infinite linear alternate-reverse;
    }

    @keyframes glitch-anim-1 {
      0% {
        clip: rect(0, 900px, 20px, 0);
        transform: translate(0);
      }
      20% {
        clip: rect(30px, 900px, 50px, 0);
        transform: translate(-3px, 2px);
      }
      40% {
        clip: rect(50px, 900px, 70px, 0);
        transform: translate(3px, -2px);
      }
      60% {
        clip: rect(20px, 900px, 40px, 0);
        transform: translate(-3px, 2px);
      }
      80% {
        clip: rect(40px, 900px, 60px, 0);
        transform: translate(3px, -2px);
      }
      100% {
        clip: rect(0, 900px, 20px, 0);
        transform: translate(0);
      }
    }
    @keyframes glitch-anim-2 {
      0% {
        clip: rect(10px, 900px, 30px, 0);
        transform: translate(0);
      }
      25% {
        clip: rect(40px, 900px, 60px, 0);
        transform: translate(2px, -3px);
      }
      50% {
        clip: rect(20px, 900px, 40px, 0);
        transform: translate(-2px, 3px);
      }
      75% {
        clip: rect(50px, 900px, 70px, 0);
        transform: translate(2px, -3px);
      }
      100% {
        clip: rect(10px, 900px, 30px, 0);
        transform: translate(0);
      }
    }

    /* Flicker */
    @keyframes flicker {
      0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
        opacity: 1;
      }
      20%, 22%, 24%, 55% {
        opacity: 0.4;
      }
    }

    /* Digitando (typing) efeito no nome */
    .typing {
      font-size: 2.5rem;
      border-right: 4px solid #0f0;
      white-space: nowrap;
      overflow: hidden;
      width: 0;
      animation:
        typing 3s steps(15) forwards,
        blink 0.75s step-end infinite;
      margin-top: 1rem;
      max-width: 20ch;
    }
    @keyframes typing {
      from { width: 0 }
      to { width: 15ch }
    }
    @keyframes blink {
      50% { border-color: transparent; }
    }

    /* Container dos skills */
    .skills {
      margin-top: 3rem;
      width: 90vw;
      max-width: 600px;
    }

    /* Skill bar geral */
    .skill {
      margin-bottom: 1.5rem;
    }

    .skill-name {
      font-size: 1.2rem;
      margin-bottom: 0.5rem;
    }

    /* Barra de progresso */
    .progress-bar {
      background: #111;
      border: 1px solid #0f0;
      height: 20px;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: inset 0 0 5px #0f0;
    }

    .progress-bar-fill {
      height: 100%;
      background: linear-gradient(90deg, #00ff00, #007700);
      width: 0;
      animation: fillBar 2.5s forwards;
    }
    .progress-bar-fill.python {
      animation-delay: 0.5s;
    }
    .progress-bar-fill.linux {
      animation-delay: 1.0s;
    }
    .progress-bar-fill.hacking {
      animation-delay: 1.5s;
    }
    .progress-bar-fill.tryhackme {
      animation-delay: 2.0s;
    }

    @keyframes fillBar {
      to { width: var(--progress); }
    }

    /* Footer com efeito scanlines */
    footer {
      margin-top: 4rem;
      color: #0f0;
      font-size: 0.8rem;
      position: relative;
      width: 100%;
      text-align: center;
      letter-spacing: 0.15em;
      user-select: none;
    }
    footer::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      background: repeating-linear-gradient(
        to bottom,
        rgba(0, 255, 0, 0.1) 0px,
        rgba(0, 255, 0, 0.1) 1px,
        transparent 2px,
        transparent 3px
      );
      pointer-events: none;
      z-index: 0;
    }

  </style>
</head>
<body>

  <h1 class="glitch" data-text="FELIPE">FELIPE</h1>
  <div class="typing">ethical hacker | python dev | linux user</div>

  <section class="skills" aria-label="Minhas habilidades">
    <div class="skill">
      <div class="skill-name">Python</div>
      <div class="progress-bar">
        <div class="progress-bar-fill python" style="--progress: 90%;"></div>
      </div>
    </div>
    <div class="skill">
      <div class="skill-name">Linux (Debian & Arch)</div>
      <div class="progress-bar">
        <div class="progress-bar-fill linux" style="--progress: 85%;"></div>
      </div>
    </div>
    <div class="skill">
      <div class="skill-name">Ethical Hacking</div>
      <div class="progress-bar">
        <div class="progress-bar-fill hacking" style="--progress: 80%;"></div>
      </div>
    </div>
    <div class="skill">
      <div class="skill-name">TryHackMe & PortSwigger</div>
      <div class="progress-bar">
        <div class="progress-bar-fill tryhackme" style="--progress: 75%;"></div>
      </div>
    </div>
  </section>

  <footer>
    &copy; 2025 Felipe — "Hack the planet. Control the system."
  </footer>

</body>
</html>
