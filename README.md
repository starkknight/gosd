<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For My Special One</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0;
      padding: 0;
      background: linear-gradient(to bottom right, #ffcccb, #ffe4e1);
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      overflow: hidden;
    }
    h1 {
      color: #ff69b4;
      font-size: 2.5rem;
    }
    p {
      color: #ff1493;
      font-size: 1.5rem;
    }
    #magicButton {
      background-color: #ff69b4;
      color: white;
      border: none;
      border-radius: 20px;
      padding: 15px 30px;
      font-size: 1.2rem;
      cursor: pointer;
      position: absolute;
      transition: all 0.2s ease;
    }
    #magicButton:hover {
      transform: scale(1.1);
    }
  </style>
</head>
<body>
  <h1>We are friends but </h1>
  <p>But you can't click this button 😉</p>
  <button id="magicButton">Catch Me!</button>

  <script>
    const button = document.getElementById("magicButton");

    document.addEventListener("mousemove", (event) => {
      const x = Math.random() * window.innerWidth;
      const y = Math.random() * window.innerHeight;

      const buttonBounds = button.getBoundingClientRect();
      const distance = Math.sqrt(
        Math.pow(event.clientX - (buttonBounds.left + buttonBounds.width / 2), 2) +
        Math.pow(event.clientY - (buttonBounds.top + buttonBounds.height / 2), 2)
      );

      // If mouse is too close to the button, move it
      if (distance < 150) {
        button.style.left = `${x}px`;
        button.style.top = `${y}px`;
      }
    });

    // Initial position
    button.style.left = "50%";
    button.style.top = "50%";
    button.style.transform = "translate(-50%, -50%)";
  </script>
</body>
</html>

