# iloveyouzara
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>I Love You Zara</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      overflow: hidden;
      background-color: #ffe6f0;
      font-family: 'Courier New', monospace;
    }

    #message {
      position: absolute;
      top: 40%;
      width: 100%;
      text-align: center;
      font-size: 36px;
      color: #d63384;
      z-index: 10;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: fall 5s linear infinite;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: -10px;
      top: 0;
    }

    @keyframes fall {
      0% {
        top: -10%;
        opacity: 1;
      }
      100% {
        top: 110%;
        opacity: 0;
      }
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>
  <div id="message"></div>
  <audio autoplay loop>
    <source src="https://ia802606.us.archive.org/23/items/AndmeshKamaleng-CintaLuarBiasa/Andmesh%20Kamaleng%20-%20Cinta%20Luar%20Biasa.mp3" type="audio/mpeg">
    Browser kamu tidak mendukung audio.
  </audio>

  <script>
    const text = "I Love You Zara";
    let index = 0;

    function typeWriter() {
      if (index < text.length) {
        document.getElementById("message").innerHTML += text.charAt(index);
        index++;
        setTimeout(typeWriter, 150);
      }
    }

    typeWriter();

    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (Math.random() * 2 + 3) + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    setInterval(createHeart, 200);
  </script>
</body>
</html>
