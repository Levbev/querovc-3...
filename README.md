<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <title>Mensagem Especial com Música</title>
  <style>
    /* Reset básico e estilo da página */
    body {
      margin: 0;
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
      overflow: hidden;
      height: 100vh;
      position: relative;
    }

    /* Container da mensagem */
    .container {
      position: absolute;
      top: 45%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: red;
      border: 3px solid white;
      padding: 30px 40px;
      border-radius: 15px;
      text-align: center;
      font-size: 1.5em;
      box-shadow: 0 0 20px red;
      max-width: 90vw;
      user-select: none;
    }

    /* Botão estilizado */
    .btn-musica {
      margin-top: 20px;
      display: inline-block;
      background-color: white;
      color: red;
      padding: 10px 25px;
      border-radius: 10px;
      text-decoration: none;
      font-weight: bold;
      box-shadow: 0 0 10px white;
      transition: all 0.3s ease;
      cursor: pointer;
      font-size: 1.2em;
      border: none;
    }
    .btn-musica:hover {
      background-color: red;
      color: white;
      box-shadow: 0 0 20px red;
    }

    /* Corações animados */
    .heart {
      position: absolute;
      font-size: 24px;
      animation-name: float;
      animation-timing-function: linear;
      animation-iteration-count: infinite;
    }
    @keyframes float {
      0% {
        transform: translateY(100vh);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh);
        opacity: 0;
      }
    }

    /* Opcional: ocultar o player de áudio */
    #musica {
      display: none;
    }
  </style>
</head>
<body>

  <!-- Mensagem com botão -->
  <div class="container">
    ❤️ Quer ser a patrocinadora oficial da minha vida sem rumo? ❤️<br /><br />
    <button class="btn-musica" onclick="tocarMusica()">
      💌 Toque para ouvir
    </button>
  </div>

  <!-- Player de áudio oculto -->
  <audio id="musica" src="Edward Sharpe & The Magnetic Zeros - Home (Official Video).mp3" type="audio/mpeg" loop></audio>

  <script>
    // Função para tocar a música quando clicar no botão
    function tocarMusica() {
      const audio = document.getElementById('musica');
      if (audio.paused) {
        audio.play();
      } else {
        audio.pause();
      }
    }

    // Função que cria os corações flutuantes
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = 3 + Math.random() * 2 + "s";
      heart.innerText = "❤️";
      document.body.appendChild(heart);

      // Remove o coração após 5 segundos para não poluir o DOM
      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    // Cria corações a cada 300ms
    setInterval(createHeart, 300);
  </script>

</body>
</html>
