<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Vogelgeluiden</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      margin: 0;
    }

    h1 {
      margin-bottom: 2rem;
      color: #2d4a2d;
      font-size: 1.8rem;
    }

    .buttons {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    button {
      padding: 1rem 2rem;
      font-size: 1.1rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #4a7c4a;
      color: white;
      width: 240px;
    }

    button:hover { background: #3a6a3a; }
    button:active { background: #2d5a2d; }
  </style>
</head>
<body>

  <h1>🐦 Vogelgeluiden</h1>

  <div class="buttons">
    <button onclick="speel('houtduif')">🕊️ Houtduif</button>
    <button onclick="speel('merel')">🖤 Merel</button>
    <button onclick="speel('roodborstje')">🔴 Roodborstje</button>
  </div>

  <!--
    Echte vogelgeluiden van xeno-canto.org (CC licentie, vrij te gebruiken)
    Houtduif:     XC364566 - Columba palumbus - Jarek Matusiak
    Merel:        XC584296 - Turdus merula    - Jarek Matusiak
    Roodborstje:  XC469937 - Erithacus rubecula - Jarek Matusiak
  -->
  <audio id="houtduif"    src="https://xeno-canto.org/364566/download"></audio>
  <audio id="merel"       src="https://xeno-canto.org/584296/download"></audio>
  <audio id="roodborstje" src="https://xeno-canto.org/469937/download"></audio>

  <script>
    let huidig = null;

    function speel(vogel) {
      if (huidig) {
        huidig.pause();
        huidig.currentTime = 0;
      }
      const audio = document.getElementById(vogel);
      huidig = audio;
      audio.play();
    }
  </script>

</body>
</html>
