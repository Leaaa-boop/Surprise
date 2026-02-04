# Surprise
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Veux-tu être mon Valentin ? ❤️</title>
  <style>
    body {
      font-family: "Poppins", sans-serif;
      background-color: #ffe4e1;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      text-align: center;
      color: #333;
    }

    h1 {
      color: #ff1493;
      font-size: 2.5em;
      margin-bottom: 20px;
    }

    button {
      padding: 15px 30px;
      margin: 15px;
      font-size: 1.2em;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      font-weight: bold;
      transition: 0.2s;
    }

    #oui {
      background-color: #ff69b4;
      color: white;
    }

    #oui:hover {
      background-color: #ff1493;
    }

    #non {
      background-color: #f0c0c0;
      color: #333;
    }

    #non:hover {
      background-color: #e99695;
    }

    #messageFinal {
      display: none;
      font-size: 1.3em;
      margin-top: 30px;
      color: #ff1493;
    }

    #messageNon {
      font-size: 1.2em;
      color: #ff69b4;
      margin-top: 20px;
      min-height: 1.5em; /* espace pour le message */
    }

    img {
      max-width: 300px;
      margin-top: 20px;
      border-radius: 20px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>

  <h1>Veux-tu être mon Valentin ? ❤️</h1>

  <!-- Boutons OUI/NON -->
  <div id="choix">
    <button id="oui">OUI 💖</button>
    <button id="non">NON 😅</button>
    <div id="messageNon"></div>
  </div>

  <!-- Message final -->
  <div id="messageFinal">
    <p>Merci d’avoir dit OUI 😍 !</p>
    <p>Deen, je t’aime plus que tout 💗 Tu es mon Valentin et je suis tellement heureuse qu’on soit ensemble ❤️</p>
    <img src="couverture.png" alt="Couverture">
  </div>

  <script>
    const ouiBtn = document.getElementById('oui');
    const nonBtn = document.getElementById('non');
    const message = document.getElementById('messageFinal');
    const choix = document.getElementById('choix');
    const messageNon = document.getElementById('messageNon');

    let nonClickCount = 0; // compteur de clics sur NON
    let ouiSize = 1.2; // taille initiale du bouton OUI en em

    // messages successifs pour NON
    const nonMessages = [
      "Ah bon, t'es sûr ? 😏",
      "Vraiment, vraiment sûr ? 😅",
      "Hmm, ça se peut pas quand même… 😜",
      "Tu es certain ? 💖",
      "Allez, clique OUI 😍"
    ];

    ouiBtn.addEventListener('click', () => {
      choix.style.display = 'none';
      message.style.display = 'block';
    });

    nonBtn.addEventListener('click', () => {
      if(nonClickCount < nonMessages.length){
        messageNon.textContent = nonMessages[nonClickCount];
      } else {
        messageNon.textContent = "😏 Je savais que tu finirais par dire OUI !";
      }
      nonClickCount++;
      ouiSize += 0.2; // augmenter la taille du bouton OUI
      ouiBtn.style.fontSize = ouiSize + "em";
    });
  </script>

</body>
</html>
