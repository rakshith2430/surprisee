# surprisee
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Valentine 💘</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ffe6f0, #fff);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      font-family: "Georgia", serif;
      overflow: hidden;
      text-align: center;
    }

    h1 {
      font-size: 3rem;
      color: #c9184a;
      animation: blink 1.3s infinite;
    }

    @keyframes blink {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    .buttons {
      margin-top: 20px;
      position: relative;
    }

    button {
      padding: 12px 26px;
      font-size: 18px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      margin: 10px;
      transition: 0.3s;
    }

    #yes {
      background: #ff4d6d;
      color: white;
    }

    #yes:hover {
      transform: scale(1.1);
    }

    #no {
      background: #adb5bd;
      position: absolute;
    }

    #message {
      margin-top: 25px;
      font-size: 1.3rem;
      color: #6a040f;
    }

    /* Floating hearts */
    .heart {
      position: fixed;
      bottom: -20px;
      font-size: 24px;
      animation: floatUp linear forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) scale(1);
        opacity: 0;
      }
      10% { opacity: 1; }
      100% {
        transform: translateY(-110vh) scale(1.8);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <h1>Will you be my Valentine Anshupie? 💘</h1>

  <div class="buttons">
    <button id="yes">YES 💖</button>
    <button id="no">NO 😏</button>
  </div>

  <div id="message"></div>

  <script>
    // YES button action
    document.getElementById("yes").onclick = () => {
      document.getElementById("message").innerHTML =
        "I knew it 😌💖<br>You’re stuck with me forever Anshu baby 💍";
    };

    // NO button runs away
    const noBtn = document.getElementById("no");
    noBtn.onmouseover = () => {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 100);
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    };

    // Floating hearts generator
    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerText = Math.random() > 0.5 ? "💖" : "💘";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (Math.random() * 3 + 4) + "s";
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 7000);
    }

    setInterval(createHeart, 300);
  </script>

</body>
</html>

