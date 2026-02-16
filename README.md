<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nuestra Historia ❤️</title>

<style>
body{
  margin:0;
  font-family: 'Segoe UI', sans-serif;
  background: linear-gradient(to top, #ffe5ec, #fff);
  overflow-x:hidden;
}

/* Pantalla inicial */
.intro{
  position:fixed;
  inset:0;
  background: linear-gradient(135deg,#ff758f,#ffb3c6);
  display:flex;
  align-items:center;
  justify-content:center;
  flex-direction:column;
  color:white;
  z-index:10;
  transition:1s;
}

.intro h1{
  font-size:2rem;
  margin-bottom:20px;
}

.open-btn{
  padding:15px 30px;
  border:none;
  border-radius:50px;
  font-size:1.2rem;
  background:white;
  color:#ff4d6d;
  cursor:pointer;
  box-shadow:0 10px 20px rgba(0,0,0,.2);
  transition:.3s;
}
.open-btn:hover{
  transform:scale(1.1);
}

/* Contenido */
.main{
  opacity:0;
  transition:1.5s;
  text-align:center;
  padding:40px 20px;
}

/* Árbol SVG */
.tree{
  margin:40px auto;
  width:220px;
  height:300px;
}

.leaf{
  fill:#ff4d6d;
  opacity:0;
  animation:grow 1s forwards ease-out;
}

@keyframes grow{
  to{ opacity:1; transform:scale(1.1);}
}

/* Carta */
.letter{
  background:white;
  max-width:600px;
  margin:30px auto;
  padding:25px;
  border-radius:15px;
  box-shadow:0 10px 25px rgba(0,0,0,0.1);
  line-height:1.6;
}

/* Contador */
.counter{
  font-size:1.3rem;
  font-weight:bold;
  color:#c9184a;
  margin-top:15px;
}

/* Corazones flotantes */
.heart{
  position:fixed;
  bottom:-20px;
  font-size:20px;
  animation:float linear forwards;
}
@keyframes float{
  to{
    transform:translateY(-100vh);
    opacity:0;
  }
}
</style>
</head>
<body>

<!-- Intro -->
<div class="intro" id="intro">
  <h1>Tengo algo para ti ❤️</h1>
  <button class="open-btn" onclick="openGift()">Haz clic aquí</button>
</div>

<!-- Contenido -->
<div class="main" id="main">
  <h1>🌳 Nuestra Historia ❤️</h1>

  <!-- Árbol más bonito -->
  <svg class="tree" viewBox="0 0 200 300">
    <!-- Tronco -->
    <rect x="95" y="150" width="10" height="140" fill="#8b5a2b"/>

    <!-- Hojas corazón -->
    <g>
      <path class="leaf" style="animation-delay:1s"
        d="M100 80 C100 60,130 60,130 80 C130 100,100 120,100 120 C100 120,70 100,70 80 C70 60,100 60,100 80Z"/>
      <path class="leaf" style="animation-delay:1.3s"
        d="M60 120 C60 100,90 100,90 120 C90 140,60 160,60 160 C60 160,30 140,30 120 C30 100,60 100,60 120Z"/>
      <path class="leaf" style="animation-delay:1.6s"
        d="M140 120 C140 100,170 100,170 120 C170 140,140 160,140 160 C140 160,110 140,110 120 C110 100,140 100,140 120Z"/>
      <path class="leaf" style="animation-delay:1.9s"
        d="M100 140 C100 120,130 120,130 140 C130 160,100 180,100 180 C100 180,70 160,70 140 C70 120,100 120,100 140Z"/>
    </g>
  </svg>

  <div class="letter">
    <h2>Para ti 💌</h2>
    <p>
      Desde que llegaste a mi vida, todo empezó a florecer.
      Como este árbol, nuestro amor ha crecido con cada momento compartido.
    </p>
    <p>
      Cada hoja es un recuerdo contigo,
      cada raíz nuestra fuerza,
      y cada día una nueva historia juntos.
    </p>
    <p>Te amo infinitamente Yura❤️</p>
  </div>

  <div class="counter" id="counter"></div>
</div>

<script>
// Abrir sorpresa
function openGift(){
  document.getElementById("intro").style.opacity="0";
  document.getElementById("intro").style.pointerEvents="none";
  document.getElementById("main").style.opacity="1";
  startHearts();
}

// Corazones flotantes
function startHearts(){
  setInterval(()=>{
    const heart=document.createElement("div");
    heart.className="heart";
    heart.innerText="❤️";
    heart.style.left=Math.random()*100+"vw";
    heart.style.animationDuration=(4+Math.random()*3)+"s";
    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),7000);
  },600);
}

// Contador de relación
const startDate = new Date("2019-12-21T00:00:00");

function updateCounter(){
  const now=new Date();
  const diff=now-startDate;

  const days=Math.floor(diff/(1000*60*60*24));
  const hours=Math.floor((diff/(1000*60*60))%24);
  const minutes=Math.floor((diff/(1000*60))%60);
  const seconds=Math.floor((diff/1000)%60);

  document.getElementById("counter").innerText=
    `Llevamos ${days} días, ${hours} horas, ${minutes} minutos y ${seconds} segundos juntos ❤️`;
}
setInterval(updateCounter,1000);
updateCounter();
</script>

</body>
</html>
