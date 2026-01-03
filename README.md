# akshitha-s-birthday
birthday
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chinmin 💗</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;500&display=swap');

body {
  margin: 0;
  height: 100vh;
  background: radial-gradient(circle at top, #ffe3f1, #fff7fb);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Poppins', sans-serif;
  overflow: hidden;
}

.card {
  background: #ffffffee;
  backdrop-filter: blur(8px);
  border-radius: 40px;
  padding: 40px;
  width: 92%;
  max-width: 460px;
  text-align: center;
  box-shadow: 0 40px 90px rgba(255, 150, 200, 0.45);
  animation: fadeIn 1.2s ease;
}

h1 {
  font-family: 'Pacifico', cursive;
  color: #ff5fa2;
  font-size: 2.9rem;
}

.nickname {
  font-family: 'Pacifico', cursive;
  color: #ff8fc8;
  font-size: 1.4rem;
}

p {
  color: #555;
  margin: 14px 0;
}

button {
  border: none;
  border-radius: 50px;
  padding: 14px 36px;
  font-size: 1rem;
  cursor: pointer;
  margin-top: 16px;
  color: white;
  background: linear-gradient(135deg, #ff7ebc, #ff9fd3);
  box-shadow: 0 18px 35px rgba(255, 140, 190, 0.45);
  transition: transform 0.25s ease;
}

button:hover { transform: scale(1.08); }

.hidden { display: none; }

.final {
  font-family: 'Pacifico', cursive;
  font-size: 1.5rem;
  color: #ff5fa2;
  margin-top: 16px;
}

.float {
  position: absolute;
  bottom: -40px;
  font-size: 22px;
  animation: floatUp 9s ease-in infinite;
  opacity: 0.65;
  pointer-events: none;
}

@keyframes floatUp {
  0% { transform: translateY(0); opacity: 0; }
  20% { opacity: 0.6; }
  100% { transform: translateY(-120vh); opacity: 0; }
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(25px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>
</head>

<body>

<audio id="music" loop>
  <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_9f9e5b9db6.mp3">
</audio>

<div class="card">
  <h1>Bangaramm 💗</h1>
  <div class="nickname">my Chinmin 🧸</div>

  <p>someone very precious has a birthday coming soon ✨</p>

  <button onclick="openMagic()">open gently 💗</button>

  <div id="magic" class="hidden">
    <p>✨ advance happy birthday ✨</p>
    <p>you feel like baby pink.</p>
    <p>soft. warm. beautiful.</p>

    <p class="final">stay just like this… loved 🌸</p>

    <button onclick="sendKiss()">send me a kiss 😘</button>
    <p id="kissText" class="hidden">kiss received 😘💗  
    saving it forever.</p>
  </div>
</div>

<script>
let floatingStarted = false;

function openMagic() {
  document.getElementById("magic").classList.remove("hidden");
  document.getElementById("music").play();

  if (!floatingStarted) {
    floatingStarted = true;
    startFloating();
  }
}

function sendKiss() {
  document.getElementById("kissText").classList.remove("hidden");

  for (let i = 0; i < 6; i++) {
    createFloat("😘");
  }
}

function startFloating() {
  setInterval(() => {
    createFloat(Math.random() > 0.5 ? "💗" : "😘");
  }, 900);
}

function createFloat(symbol) {
  const f = document.createElement("div");
  f.className = "float";
  f.innerHTML = symbol;
  f.style.left = (10 + Math.random() * 80) + "vw";
  f.style.fontSize = (18 + Math.random() * 18) + "px";
  document.body.appendChild(f);
  setTimeout(() => f.remove(), 9000);
}
</script>

</body>
</html>
