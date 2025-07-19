# for-you
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Kangen</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: linear-gradient(to right, #ffafbd, #ffc3a0);
      font-family: sans-serif;
    }

    .msg {
      font-size: 2.5rem;
      color: #fff;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.3);
      animation: fade 2s ease-in-out infinite alternate;
      z-index: 2;
    }

    @keyframes fade {
      from {opacity: 0.3; transform: scale(0.95);}
      to {opacity: 1; transform: scale(1.05);}
    }

    .btn {
      margin-top: 30px;
      padding: 12px 24px;
      background-color: #fff;
      color: #ff6f91;
      font-weight: bold;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: transform 0.2s ease;
      z-index: 2;
    }

    .btn:hover {
      transform: scale(1.05);
    }

    .hearts {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      pointer-events: none;
      z-index: 1;
    }

    .heart {
      position: absolute;
      color: #ff6b81;
      font-size: 20px;
      animation: float 6s linear infinite;
      opacity: 0.8;
    }

    @keyframes float {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(100vh) scale(0.5);
        opacity: 0;
      }
    }

    @media (max-width: 600px) {
      .msg {
        font-size: 2rem;
        text-align: center;
        padding: 0 20px;
      }

      .btn {
        padding: 10px 20px;
        font-size: 1rem;
      }
    }
  </style>
</head>
<body>
  <div class="hearts"></div>
  <div class="msg">aku kangen kamu 💌</div>
  <button class="btn" onclick="showReply()">balas ya 💬</button>

  <script>
    function showReply() {
      const reply = prompt("Kamu juga kangen aku? 😊");
      if (reply) {
        alert("Yay! 🥰 Aku senang dengar itu 💖");
      } else {
        alert("Gapapa, aku tetap kangen kok 😌");
      }
    }

    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.innerText = '💖';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.fontSize = (Math.random() * 10 + 15) + 'px';
      heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
      document.querySelector('.hearts').appendChild(heart);
      setTimeout(() => heart.remove(), 7000);
    }

    setInterval(createHeart, 500);
  </script>
</body>
</html>
