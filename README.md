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

* { box-sizing: border-box; }

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

/* Card */
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

/* Text */
h1 {
  font-family: 'Pacifico', cursive;
  color: #ff5fa2;
  font-size: 2.9rem;
  margin-bottom: 5px;
}

.nickname {
  font-family: 'Pacifico', cursive;
  color: #ff8fc8;
  font-size: 1.4rem;
}

p {
  color: #555;
  font-size: 1rem;
  margin: 14px 0;
}

/* Buttons */
button {
  border: none;
  border-radius: 50px;
  padding: 14px 36px;
  font-size: 1rem;
  cursor: pointer;
  margin-top: 18px;
  color: white;
  background: linear-gradient(135deg, #ff7ebc, #ff9fd3);
  box-shadow: 0 18px 35px rgba(255, 140, 190, 0.45);
  transition: transform 0.25s ease;
}

button:hover { transform: scale(1.1); }

.hidden { display: none; }

.final {
  font-family: 'Pacifico', cursive;
  font-size: 1.5rem;
  color: #ff5fa2;
  margin-top: 16px;
}

/* Floating elegance */
.float {
  position: absolute;
  bottom: -40px;
  font-size: 22px;
  animation: floatUp 10s ease-in infinite;
  opacity: 0.65;
  pointer-events: none;
}

@keyframes floatUp {
  0% {
    transform: translateY(0) scale(0.9);
    opacity: 0;
  }
  20% { opacity: 0.6; }
  100% {
    transform: translateY(-120vh) scale(1.15);
    opacity: 0;
  }
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>
</head>

<body>

<audio id="music" loop>
  <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_9f9e5b9db6.mp3" type="audio/mpeg">
</audio>

<div class="card">
  <h1>Bangaramm 💗</h1>
  <div class="nickname">my Chinmin 🧸</div>

  <p>soft reminder…</p>
  <p>someone incredibly precious has a birthday coming soon ✨</p>

  <button onclick="openMagic()">open gently 💗</button>

  <div id="magic" class="hidden">
    <p>✨ advance happy birthday ✨</p>

    <p>you feel like baby pink.</p>
    <p>warm. gentle. beautiful.</p>

    <p>when I say <b>Chinmin</b>,  
    my heart smiles first 💕</p>

    <p class="final">
      stay just like this…  
      soft and loved 🌸
    </p>
  </div>
</div>

<script>
function openMagic() {
  document.getElementById("magic").classList.remove("hidden");
  document.getElementById("music").play();
  startFloating();
}

function startFloating() {
  setInterval(() => {
    const f = document.createElement("div");
    f.className = "float";
    f.innerHTML = Math.random() > 0.5 ? "💗" : "😘";
    f.style.left = (10 + Math.random() * 80) + "vw";
    f.style.fontSize = (18 + Math.random() * 18) + "px";
    document.body.appendChild(f);
    setTimeout(() => f.remove(), 10000);
  }, 700);
}
</script>

</body>
</html>
