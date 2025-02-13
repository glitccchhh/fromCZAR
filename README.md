
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
      min-height: 100vh; /* Ensures full height */
      overflow-x: hidden; /* Prevents horizontal scroll */
    }

    h1 {
      font-size: 2rem;
      animation: fadeIn 2s, glow 1.5s infinite alternate ease-in-out;
      text-shadow: 0 0 10px #fff, 0 0 20px #ff66b2;
    }

    p {
      font-size: 1.2rem;
      animation: slideIn 2s;
    }

    button {
      padding: 12px;
      font-size: 1rem;
      border: none;
      border-radius: 25px;
      background: #9400D3;
      color: white;
      cursor: pointer;
      margin: 10px;
      width: 90%;
      max-width: 250px;
      box-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
    }

    button:hover {
      background: #DA70D6;
    }

    /* Glowing effect */
    @keyframes glow {
      from { text-shadow: 0 0 5px #fff, 0 0 10px #ff66b2; }
      to { text-shadow: 0 0 20px #fff, 0 0 30px #ff1493; }
    }

    /* Gift Box - Shake & Bounce */
    .gift-box {
      font-size: 3rem;
      cursor: pointer;
      margin: 20px 0;
      animation: bounce 2s infinite, shake 0.5s infinite alternate ease-in-out;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    @keyframes shake {
      0% { transform: translateX(0); }
      25% { transform: translateX(-5px) rotate(-2deg); }
      50% { transform: translateX(5px) rotate(2deg); }
      75% { transform: translateX(-3px) rotate(-1deg); }
      100% { transform: translateX(0); }
    }

    .hidden-message {
      display: none;
      margin-top: 20px;
      padding: 15px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
      animation: fadeIn 1s;
    }

    /* Falling Items */
    .falling-item {
      position: absolute;
      top: -50px;
      left: 50%;
      font-size: 2rem;
      animation: fall linear infinite;
    }

    @keyframes fall {
      from { transform: translateY(-100px) scale(1); opacity: 1; }
      to { transform: translateY(100vh) scale(0.5); opacity: 0; }
    }

    /* Responsive Design */
    @media (max-width: 600px) {
      body {
        padding: 15px;
      }

      h1 {
        font-size: 1.8rem;
        margin-bottom: 10px;
      }

      p {
        font-size: 1rem;
      }

      .gift-box {
        font-size: 2.5rem;
      }

      button {
        font-size: 1rem;
        padding: 10px 15px;
      }
    }

  </style>
</head>
<body>
  <h1>To My Sweet Valentine 💜🌹</h1>
  <p>You make my world brighter. Happy Valentine’s Day, Tolu! 💖</p>

  <!-- Gift Box and Hidden Message -->
  <div class="gift-box" onclick="revealMessage()">🎁</div>
  <div id="hiddenMessage" class="hidden-message">
    <p>💜 A Special Note for You, Tolu 💜</p>
    <p>From the first moment I saw you, I knew you were special. Every “no” has never made me feel like giving up—because I believe in something real, something worth waiting for. You’re amazing in ways I can’t describe, and all I want is the chance to make you smile every single day.</p>
    <p>So here I am, once again, asking…</p>
  </div>

  <p>Will you be my Valentine?</p>
  <button onclick="alert('Yay! 💜')">Yes</button>
  <button onclick="alert('Aww, I’ll try harder! 😊')">Not Yet</button>

  <!-- Music Section -->
  <p>Click "Play Music" to enjoy the soundtrack! 🎶</p>
  <button id="playMusic" onclick="playAudio()">Play Music</button>

  <audio id="bg-music" loop>
    <source src="beautiful-things.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <script>
    function playAudio() {
      let audio = document.getElementById("bg-music");
      audio.play().then(() => {
        document.getElementById("playMusic").style.display = "none";
      }).catch(err => {
        console.log("Autoplay blocked, user must click play button.");
      });
    }

    function revealMessage() {
      let message = document.getElementById("hiddenMessage");
      message.style.display = "block";
      document.querySelector(".gift-box").style.display = "none"; // Hide the gift box after clicking
    }

    // Falling Elements (Hearts, Teddy Bears, Roses)
    function createFallingItem() {
      let items = ["💜", "🧸", "🌹"];
      let randomItem = items[Math.floor(Math.random() * items.length)];

      let fallingItem = document.createElement("div");
      fallingItem.innerHTML = randomItem;
      fallingItem.className = "falling-item";
      fallingItem.style.left = Math.random() * 100 + "vw";
      fallingItem.style.animationDuration = Math.random() * 3 + 2 + "s";
      fallingItem.style.position = "absolute";
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