
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
      padding: 50px;
      margin: 0;
      overflow: hidden;
      position: relative;
    }

    h1 {
      font-size: 3rem;
      animation: fadeIn 2s, glow 2s infinite alternate;
    }

    p {
      font-size: 1.5rem;
      animation: slideIn 2s;
    }

    .gallery {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 20px;
    }
    .gallery img {
      width: 150px;
      height: 150px;
      object-fit: cover;
      border-radius: 10px;
      transition: transform 0.3s;
    }
    .gallery img:hover {
      transform: scale(1.1);
    }

    video {
      margin-top: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    button {
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

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes slideIn {
      from { transform: translateY(50px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #fff; }
      to { text-shadow: 0 0 20px #ff66b2; }
    }

    /* Gift Box */
    .gift-box {
      font-size: 4rem;
      cursor: pointer;
      margin: 20px 0;
      animation: bounce 2s infinite;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    .hidden-message {
      display: none;
      margin-top: 20px;
      padding: 20px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
      animation: fadeIn 1s;
    }

    /* Falling Items */
    .falling-item {
      position: fixed;
      top: -50px;
      animation: fall linear infinite;
    }

    @keyframes fall {
      from { transform: translateY(-100px) scale(1); opacity: 1; }
      to { transform: translateY(100vh) scale(0.5); opacity: 0; }
    }

    /* Confetti Effect */
    .confetti {
      position: absolute;
      width: 8px;
      height: 8px;
      background: pink;
      opacity: 0.7;
      animation: confetti-fall 3s infinite linear;
    }

    @keyframes confetti-fall {
      0% { transform: translateY(0) rotate(0); }
      100% { transform: translateY(100vh) rotate(360deg); }
    }

    /* Responsive Design */
    @media (max-width: 600px) {
      h1 { font-size: 2rem; }
      p { font-size: 1.2rem; }
      video { width: 100%; height: auto; }
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

  <div class="gallery">
    <img src="assets/IMG-20250212-WA0041.jpg" alt="Memory 1">
    <img src="assets/IMG-20250212-WA0040.jpg" alt="Memory 2">
  </div>

  <video width="320" height="240" controls autoplay loop>
    <source src="assets/VID-20250212-WA0035.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>

  <p>Click "Play Music" to enjoy the soundtrack! 🎶</p>
  <button id="playMusic" onclick="playAudio()">Play Music</button>

  <audio id="bg-music" loop>
    <source src="assets/beautiful-things.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <script>
    function playAudio() {
      let audio = document.getElementById("bg-music");
      audio.play();
      document.getElementById("playMusic").style.display = "none";
    }

    function revealMessage() {
      let message = document.getElementById("hiddenMessage");
      message.style.display = "block";
      document.querySelector(".gift-box").style.display = "none"; // Hide the gift box after clicking
    }

    document.addEventListener("DOMContentLoaded", function() {
      let audio = document.getElementById("bg-music");
      let playPromise = audio.play();
      
      if (playPromise !== undefined) {
        playPromise.then(() => {
          document.getElementById("playMusic").style.display = "none";
        }).catch(() => {
          console.log("Autoplay blocked, user must click play button.");
        });
      }
    });

    // Falling Elements (Hearts, Teddy Bears, Roses)
    function createFallingItem() {
      let items = ["💜", "🧸", "🌹"]; // Purple Heart, Teddy Bear, Rose
      let randomItem = items[Math.floor(Math.random() * items.length)];

      let fallingItem = document.createElement("div");
      fallingItem.innerHTML = randomItem;
      fallingItem.className = "falling-item";
      fallingItem.style.left = Math.random() * 100 + "vw";
      fallingItem.style.animationDuration = Math.random() * 3 + 2 + "s"; // Random speed
      fallingItem.style.position = "fixed";
      fallingItem.style.top = "-50px"; // Start above screen
      fallingItem.style.fontSize = Math.random() * 25 + 20 + "px"; // Random sizes

      document.body.appendChild(fallingItem);
      
      setTimeout(() => {
        fallingItem.remove();
      }, 5000);
    }
    setInterval(createFallingItem, 300); // Items appear every 0.3s

    // Confetti Effect
    function createConfetti() {
      let confetti = document.createElement("div");
      confetti.className = "confetti";
      confetti.style.left = Math.random() * 100 + "vw";
      confetti.style.backgroundColor = ["#FF69B4", "#FFD700", "#FF4500"][Math.floor(Math.random() * 3)];
      confetti.style.animationDuration = Math.random() * 2 + 2 + "s"; // Random speed
      document.body.appendChild(confetti);
      
      setTimeout(() => {
        confetti.remove();
      }, 3000);
    }
    setInterval(createConfetti, 200);
  </script>
</body>
</html>