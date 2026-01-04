# akshitha-s-birthday
birthday
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Chinmin 💗</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500&family=Pacifico&display=swap');

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Poppins', sans-serif;
}

body{
  background: linear-gradient(135deg,#ffd1e8,#ffeaf4);
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  overflow:hidden;
}

.container{
  background:#fff5fb;
  width:90%;
  max-width:420px;
  border-radius:30px;
  padding:25px;
  text-align:center;
  box-shadow:0 25px 50px rgba(255,105,180,0.25);
  z-index:2;
}

h1{
  font-family:'Pacifico', cursive;
  color:#ff5fa2;
}

.timer{
  color:#ff5fa2;
  margin:10px 0;
  font-size:1.1rem;
}

button{
  background:#ff8fc7;
  border:none;
  color:white;
  padding:10px 22px;
  border-radius:25px;
  margin-top:12px;
  cursor:pointer;
}

.letter{
  display:none;
  margin-top:20px;
  text-align:left;
  color:#555;
  line-height:1.7;
  font-size:0.95rem;
  animation: fadeIn 2s ease forwards;
}

.nextBtn{
  display:none;
}

.slideshow{
  display:none;
  margin-top:15px;
}

.slideshow img{
  width:100%;
  height:300px;
  object-fit:cover;
  border-radius:20px;
}

.caption{
  margin-top:10px;
  color:#666;
  font-size:0.9rem;
  min-height:45px;
}

canvas{
  position:fixed;
  top:0;
  left:0;
  pointer-events:none;
  z-index:1;
}

@keyframes fadeIn{
  from{opacity:0; transform:translateY(10px);}
  to{opacity:1; transform:translateY(0);}
}
</style>
</head>

<body>

<canvas id="fireworks"></canvas>

<div class="container">
  <h1 id="title">Hey Chinmin 💗</h1>
  <div class="timer" id="countdown">Almost your day…</div>

  <button onclick="playMusic()">▶️ Play music</button>

  <div class="letter" id="letter">
    <p><strong>Happy Birthday, Chinmin 🤍</strong></p>
    <p>
      I don’t know if words will ever be enough,  
      but tonight I wanted to try.
    </p>
    <p>
      You are gentle in ways you don’t even realize,  
      strong even when you feel tired,  
      and beautiful in the quiet moments no one sees.
    </p>
    <p>
      We may not always be perfect,  
      but my heart never doubts one thing —  
      you matter to me, deeply.
    </p>
    <p>
      On your birthday, I just want you to feel loved,  
      chosen, and safe in knowing  
      that someone truly cares about your smile.
    </p>
    <p>
      Today is yours, Chinmin.  
      And I hope this year gives you  
      all the softness and happiness you deserve 💗
    </p>
  </div>

  <button class="nextBtn" id="nextBtn" onclick="startSlideshow()">
    There’s something more… 🎀
  </button>

  <div class="slideshow" id="slideshow">
    <img id="slide" src="img1.jpg">
    <div class="caption" id="caption"></div>
  </div>
</div>

<audio id="music" src="song.mp3" loop></audio>

<script>
// MUSIC
function playMusic(){
  document.getElementById("music").play();
}

// DATE — JAN 5
const now = new Date();
let birthday = new Date(now.getFullYear(),0,5,0,0,0);
if(now > birthday) birthday = new Date(now.getFullYear()+1,0,5,0,0,0);

const countdownEl = document.getElementById("countdown");
const title = document.getElementById("title");
const letter = document.getElementById("letter");
const nextBtn = document.getElementById("nextBtn");

function updateCountdown(){
  const diff = birthday - new Date();
  if(diff <= 0){
    countdownEl.style.display = "none";
    title.innerText = "Happy Birthday Chinmin 💗";
    letter.style.display = "block";
    nextBtn.style.display = "inline-block";
    startFireworks();
    return;
  }
  const m = Math.floor(diff/60000);
  const s = Math.floor((diff%60000)/1000);
  countdownEl.innerText = `⏳ ${m}m ${s}s`;
}
setInterval(updateCountdown,1000);
updateCountdown();

// SLIDESHOW
const images = ["img1.jpg","img2.jpg","img3.jpg","img4.jpg","img5.jpg"];
const captions = [
  "This smile melts me 💗",
  "Some moments stay forever",
  "My favorite memories have you in them",
  "Thank you for being you",
  "This day belongs to you 🎂"
];

let index = 0;
const slide = document.getElementById("slide");
const caption = document.getElementById("caption");

function startSlideshow(){
  letter.style.display = "none";
  nextBtn.style.display = "none";
  document.getElementById("slideshow").style.display = "block";
  caption.innerText = captions[0];
  setInterval(()=>{
    index = (index + 1) % images.length;
    slide.src = images[index];
    caption.innerText = captions[index];
  },4000);
}

// FIREWORKS
const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");
canvas.width = innerWidth;
canvas.height = innerHeight;

let particles=[];
function startFireworks(){
  setInterval(()=>{
    for(let i=0;i<70;i++){
      particles.push({
        x:canvas.width/2,
        y:canvas.height/2,
        dx:(Math.random()-0.5)*8,
        dy:(Math.random()-0.5)*8,
        life:100,
        color:`hsl(${Math.random()*360},100%,70%)`
      });
    }
  },600);
}

function animate(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  particles.forEach((p,i)=>{
    p.x+=p.dx;
    p.y+=p.dy;
    p.life--;
    ctx.fillStyle=p.color;
    ctx.beginPath();
    ctx.arc(p.x,p.y,3,0,Math.PI*2);
    ctx.fill();
    if(p.life<=0) particles.splice(i,1);
  });
  requestAnimationFrame(animate);
}
animate();
</script>

</body>
</html>
