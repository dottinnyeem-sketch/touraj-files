# touraj-files

<!DOCTYPE html>
<html lang=“en”>
<head>
  <meta charset=“UTF-8” />
  <meta name=“viewport” content=“width=device-width, initial-scale=1.0”/>
  <title>The Touraj Files 👁️</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: radial-gradient(circle at center, #0a0000 0%, #000000 70%);
      color: #ff1a1a;
      font-family: “Courier New”,
monospace;
      text-align: center;
      overflow: hidden;
    }

    /* subtle moving noise effect */
    body::before {
      content: “”;
      position: absolute;
      width: 200%;
      height: 200%;
      background: repeating-linear-gradient(
        0deg,
        rgba(255,0,0,0.03) 0px,
        rgba(255,0,0,0.03) 1px,
        transparent 1px,
        transparent 2px
      );
      animation: scan 8s linear infinite;
      pointer-events: none;
    }@keyframes scan {
      from { transform: translateY(0); }
      to { transform: translateY(-50%); }
    }

    h1 {
      font-size: 3rem;
      margin-bottom: 25px;
      letter-spacing: 4px;
      text-shadow: 0 0 10px #ff0000, 0 0 25px #ff0000;
      animation: flicker 2.5s infinite;
    }#countdown {
      font-size: 4.5rem;
      padding: 25px 50px;
      border: 2px solid #ff0000;
      border-radius: 12px;
      box-shadow: 0 0 20px #ff0000 inset, 0 0 25px #ff0000;
      background: rgba(0, 0, 0, 0.6);
      animation: flicker 3s infinite;
    }

    .finished {
      font-size: 2.8rem;
      color: #ff0000;
      text-shadow: 0 0 15px #ff0000, 0 0 40px #ff0000;
      animation: glitch 0.4s infinite;
    }/* flickering light effect */
    @keyframes flicker {
      0%, 18%, 22%, 25%, 53%, 57%, 100% { opacity: 1; }
      20%, 24%, 55% { opacity: 0.4; }
    }

    /* glitch effect when finished */
    @keyframes glitch {
      0% { transform: translate(0, 0); }
      20% { transform: translate(-2px, 2px); }
      40% { transform: translate(2px, -2px); }
      60% { transform: translate(-2px, -1px); }
      80% { transform: translate(1px, 2px); }
      100% { transform: translate(0, 0); }
    }
  </style>
</head>
<body><h1>THE TOURAJ FILES 👁️</h1>
  <div id=“countdown”>24:00:00</div>

  <script>
    const duration = 24 * 60 * 60 * 1000;
    const endTime = new Date().getTime() + duration;

    const countdownElement = document.getElementById(“countdown”);

    function updateCountdown() {
      const now = new Date().getTime();
      const timeLeft = endTime - now;

      if (timeLeft <= 0) {
        countdownElement.textContent = “FILES OPENED 👁️”;
        countdownElement.classList.add(“finished”);
        clearInterval(timer);
        return;
      }

      const hours = Math.floor(timeLeft / (1000 * 60 * 60));
      const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);countdownElement.textContent =
        String(hours).padStart(2, “0”) + “:” +
        String(minutes).padStart(2, “0”) + “:” +
        String(seconds).padStart(2, “0”);
    }

    updateCountdown();
    const timer = setInterval(updateCountdown, 1000);
  </script>

</body>
</html>
