
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For My Valentine 💜🌹</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #8A2BE2, #DDA0DD);
      color: white;
      text-align: center;
      padding: 20px;
      margin: 0;
      overflow-x: hidden;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    h1, p {
      max-width: 90%;
      word-wrap: break-word;
    }

    button {
      width: 80%;
      max-width: 250px;
      padding: 12px 24px;
      font-size: 1.2rem;
      border: none;
      border-radius: 25px;
      background: #9400D3;
      color: white;
      cursor: pointer;
      margin: 10px;
      transition: 0.3s;
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
    }
    button:hover {
      background: #DA70D6;
    }

    .gift-box {
      font-size: 4rem;
      cursor: pointer;
      margin: 20px 0;
      animation: bounce 2s infinite;
    }

    .hidden-message {
      display: none;
      margin-top: 20px;
      padding: 20px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
    }

    .falling-item {
      font-size: 18px;
      position: fixed;
      top: -50px;
      animation: fall linear infinite;
    }

    @keyframes fall {
      from { transform: translateY(-100px) scale(1); opacity: 1; }
      to { transform: translateY(100vh) scale(0.5); opacity: 0; }
    }

    @media (max-width: 600px) {
      h1 { font-size: 2rem; }
      p { font-size: 1.2rem; }
    }
  </style>
</head>
<body>
  <h1>To My Sweet Valentine 💜🌹</h1>
  <p>You make my world brighter. Happy Valentine’s Day, Tolu! 💖</p>

  <div class="gift-box" onclick="revealMessage()">🎁</div>
  <div id="hiddenMessage" class="hidden-message">
    <p>💜 A Special Note for You, Tolu 💜</p>
    <p>From the first moment I saw you, I knew you were special. Every “no” has never made me feel like giving up—because I believe in something real, something worth waiting for. You’re amazing in ways I can’t describe, and all I want is the chance to make you smile every single day.</p>
    <p>So here I am, once again, asking…</p>
  </div>

  <p>Will you be my Valentine?</p>
  <button onclick="alert('Yay! 💜')">Yes</button>
  <button onclick="alert('Aww, I’ll try harder! 😊')">Not Yet</button>

  <p>Click "Play Music" to enjoy the soundtrack! 🎶</p>
  <button id="playMusic" onclick="playAudio()">Play Music</button>

  <audio id="bg-music" loop>
    <source src="assets/beautiful-things.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <script>
    function playAudio() {
      let audio = document.getElementById("bg-music");
      if (audio.paused) {
        audio.play().then(() => {
          document.getElementById("playMusic").style.display = "none";
        }).catch(error => {
          console.log("Audio play blocked: ", error);
        });
      }
    }

    function revealMessage() {
      let message = document.getElementById("hiddenMessage");
      message.style.display = "block";
      document.querySelector(".gift-box").style.display = "none";
    }

    function createFallingItem() {
      let items = ["💜", "🧸", "🌹"];
      let randomItem = items[Math.floor(Math.random() * items.length)];

      let fallingItem = document.createElement("div");
      fallingItem.innerHTML = randomItem;
      fallingItem.className = "falling-item";
      fallingItem.style.left = Math.random() * 100 + "vw";
      fallingItem.style.animationDuration = Math.random() * 3 + 2 + "s";
      fallingItem.style.position = "fixed";
      fallingItem.style.top = "-50px";
      fallingItem.style.fontSize = Math.random() * 25 + 20 + "px";

      document.body.appendChild(fallingItem);
      
      setTimeout(() => {
        fallingItem.remove();
      }, 5000);
    }
    setInterval(createFallingItem, 300);
  </script>
</body>
</html>