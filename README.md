<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Mensagem Especial</title>
  <style>
    body {
      margin: 0;
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
      overflow: hidden;
    }

    .container {
      position: absolute;
      top: 45%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: red;
      border: 3px solid white;
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      font-size: 1.5em;
      box-shadow: 0 0 20px red;
    }

    .heart {
      position: absolute;
      font-size: 24px;
      animation: float 5s linear infinite;
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

    .btn-musica {
      margin-top: 20px;
      display: inline-block;
      background-color: white;
      color: red;
      padding: 10px 20px;
      border-radius: 10px;
      text-decoration: none;
      font-weight: bold;
      box-shadow: 0 0 10px white;
      transition: all 0.3s ease;
      cursor: pointer;
    }

    .btn-musica:hover {
      background-color: red;
      color: white;
      box-shadow: 0 0 20px red;
    }
  </style>
</head>
<body>

  <!-- MENSAGEM -->
  <div class="container">
    ❤️ Quer ser a patrocinadora oficial da minha vida sem rumo? ❤️<br><br>
    <button class="btn-musica" onclick="tocarMusica()">
      💌 Toque para ouvir
    </button>
  </div>

  <!-- CORAÇÕES SUBINDO -->
  <script>
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = 3 + Math.random() * 2 + "s";
      heart.innerText = "❤️";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    setInterval(createHeart, 300);
  </script>

  <!-- ÁUDIO -->
  <audio id="musica" src="<audio controls>
  <source src="Edward Sharpe & The Magnetic Zeros - Home (Official Video).mp3" type="audio/mpeg" />
</audio>
" type="audio/mpeg" loop></audio>

  <script>
    function tocarMusica() {
      const audio = document.getElementById('musica');
      audio.play();
    }
  </script>

</body>
</html>
