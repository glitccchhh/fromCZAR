
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For My Crush ❤️</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      color: white;
      text-align: center;
      padding: 50px;
      margin: 0;
    }
    h1 {
      font-size: 3rem;
      animation: fadeIn 2s;
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
      padding: 10px 20px;
      font-size: 1.2rem;
      border: none;
      border-radius: 5px;
      background: #ff6f61;
      color: white;
      cursor: pointer;
      margin: 10px;
    }
    button:hover {
      background: #ff3b2f;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes slideIn {
      from { transform: translateY(50px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
  </style>
</head>
<body>
  <h1>To Tolu ❤️</h1>
  <p>You mean the world to me. Happy Valentine's Day in Addy!</p>
  <p>Will you be my Valentine?</p>
  <button onclick="alert('Yay! ❤️')">Yes</button>
  <button onclick="alert('Aww, I’ll try harder! 😊')">Not Yet</button>

  <div class="gallery">
    <img src="IMG-20250212-WA0041.jpg" alt="Memory 1">
    <img src="IMG-20250212-WA0040.jpg" alt="Memory 2">
  </div>

  <video width="320" height="240" controls autoplay loop>
    <source src="VID-20250212-WA0035.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>

  <audio controls autoplay loop muted>
    <source src="beautiful-things.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>
</body>
</html>