<html lang="en">
<head>
<meta charset="UTF-8">
<title>Prodigy Math Lesson</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',sans-serif}

/* BACKGROUND (GREEN) */
body{
min-height:100vh;
background:linear-gradient(rgba(0,60,0,.7),rgba(0,20,0,.95)),
url('https://media.gettyimages.com/id/881752658/video/journey-through-galaxy.jpg?s=640x640&k=20&c=ITfk5mu21pnyUjb7tTndTm8LMBqpPS4YBMY2Il_nGyQ=') center/cover fixed;
color:#d4ffd4;
overflow-x:hidden;
}

/* ACCESS */
#passwordScreen{
position:fixed;inset:0;
display:flex;
justify-content:center;
align-items:center;
background:rgba(0,50,0,.95);
z-index:999;
}

.passwordBox{
background:rgba(0,80,0,.95);
padding:40px;
border-radius:18px;
text-align:center;
width:320px;
box-shadow:0 0 25px #00ff88;
}

#accessText{font-size:26px}

/* SECRET ZONE */
#secretZone{
position:fixed;
bottom:0;
left:0;
width:80px;
height:80px;
z-index:1000;
}

/* SECRET INPUT */
#secretInput{
position:fixed;
bottom:20px;
left:20px;
padding:10px;
border-radius:8px;
border:none;
outline:none;
display:none;
z-index:1001;
background:#002b00;
color:#00ff88;
box-shadow:0 0 10px #00ff88;
}

/* LOADER */
#loader{
position:fixed;inset:0;
display:flex;
justify-content:center;
align-items:center;
background:#001a00;
color:#00ff88;
font-size:28px;
transform:translateX(-100%);
transition:.25s;
z-index:15;
}
#loader.active{transform:translateX(0)}

/* HOME */
.container{display:none;text-align:center;padding-top:70px}
h1{
font-size:70px;
text-shadow:0 0 20px #00ff88;
}

/* BUTTONS */
.buttonContainer{
display:flex;
flex-direction:column;
gap:12px;
width:280px;
margin:auto;
}

.gameBtn{
padding:14px;
background:#003d00;
color:#00ff88;
border:1px solid #00ff88;
cursor:pointer;
border-radius:10px;
transition:.2s;
box-shadow:0 0 10px #00ff88;
}

.gameBtn:hover{
transform:scale(1.05);
background:#005500;
box-shadow:0 0 20px #00ff88;
}

/* HOME BUTTON */
#homeBtn{
position:fixed;
top:15px;
left:15px;
padding:6px 10px;
font-size:13px;
background:#002b00;
border:1px solid #00ff88;
border-radius:6px;
color:#00ff88;
display:none;
z-index:20;
cursor:pointer;
box-shadow:0 0 10px #00ff88;
}

/* GAME VIEW */
iframe,embed{
position:fixed;inset:0;
width:100%;height:100%;
display:none;
border:0;
}

audio{display:none}
</style>
</head>

<body>

<!-- ACCESS -->
<div id="passwordScreen">
  <div class="passwordBox">
    <h2 id="accessText">not white listed unable to join</h2>
  </div>
</div>

<!-- SECRET -->
<div id="secretZone"></div>
<input id="secretInput" placeholder="enter code..." />

<!-- LOADER -->
<div id="loader">onclu</div>

<!-- HOME BUTTON -->
<button id="homeBtn" onclick="goHome()">home</button>

<!-- HOME -->
<div class="container" id="homeScreen">
  <h1>onclu</h1>
  <div class="buttonContainer">

    <button class="gameBtn" onclick="openGame('hoodaFrame')">HoodaMath</button>
    <button class="gameBtn" onclick="openGame('playFrame')">Playtropolis</button>
    <button class="gameBtn" onclick="openGame('gFrame')">GHub</button>
    <button class="gameBtn" onclick="openGame('minecraftFrame')">Minecraft</button>
    <button class="gameBtn" onclick="openGame('infiniteFrame')">Infinite Craft</button>
    <button class="gameBtn" onclick="openGame('soundboardFrame')">Soundboard</button>
    <button class="gameBtn" onclick="openGame('mathFrame')">Coolmath Games</button>
    <button class="gameBtn" onclick="openGame('cheeseFrame')">Stan The Cheese Man</button>
    <button class="gameBtn" onclick="openGame('basketFrame')">Basket Random</button>
    <button class="gameBtn" onclick="openGame('buildnowFrame')">Build Now GG</button>
    <button class="gameBtn" onclick="openGame('hahaFrame')">Haha Games</button>
    <button class="gameBtn" onclick="openGame('gamaFrame')">Play Gama</button>
    <button class="gameBtn" onclick="openGame('agentFrame')">For Khalil</button>

  </div>
</div>

<!-- GAMES -->
<iframe id="hoodaFrame" src="https://www.hoodamath.com/"></iframe>
<iframe id="playFrame" src="https://www.playtropolis.com"></iframe>
<iframe id="gFrame" src="https://ghub-light.neocities.org/"></iframe>
<iframe id="minecraftFrame" src="https://eaglercraft.com/"></iframe>
<embed id="infiniteFrame" src="https://infinite-craft.org/infinite-craft/">
<iframe id="soundboardFrame" src="https://www.myinstants.com/en/index/us/"></iframe>
<iframe id="mathFrame" src="https://www.coolmathgames.com/"></iframe>
<iframe id="cheeseFrame" src="https://stanthecheeseman.github.io/"></iframe>
<iframe id="basketFrame" src="https://www.twoplayergames.org/game/basket-random"></iframe>
<iframe id="buildnowFrame" src="https://buildnow-gg.io/"></iframe>
<iframe id="hahaFrame" src="https://www.hahagames.com/"></iframe>
<iframe id="gamaFrame" src="https://playgama.com"></iframe>
<iframe id="agentFrame" src="https://www.twoplayergames.org/game/agent-walker-vs-skibidi-toilets"></iframe>

<audio id="lofi" src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" loop></audio>

<script>
let wl = localStorage.getItem("wl")==="1";

const screen = document.getElementById("passwordScreen");
const home = document.getElementById("homeScreen");
const loader = document.getElementById("loader");
const homeBtn = document.getElementById("homeBtn");
const audio = document.getElementById("lofi");
const input = document.getElementById("secretInput");
const zone = document.getElementById("secretZone");

/* LOAD */
window.onload=()=>{
  if(wl){
    zone.remove(); // disable trigger permanently
    enter();
  }
};

/* ENTER */
function enter(){
  loader.classList.add("active");
  setTimeout(()=>{
    screen.style.display="none";
    input.style.display="none";
    zone.remove(); // remove after success
    loader.classList.remove("active");
    home.style.display="block";
    audio.volume=.2;
    audio.play();
  },1200);
}

/* SECRET CLICK */
zone.onclick=()=>{
  input.style.display="block";
  input.focus();
};

/* CHECK CODE */
input.addEventListener("keydown",e=>{
  if(e.key==="Enter"){
    if(input.value==="biggieisfye"){
      localStorage.setItem("wl","1");
      enter();
    } else {
      input.value="";
    }
  }
});

/* OPEN GAME */
function openGame(id){
  loader.classList.add("active");
  setTimeout(()=>{
    home.style.display="none";
    document.querySelectorAll("iframe,embed").forEach(e=>e.style.display="none");
    document.getElementById(id).style.display="block";
    homeBtn.style.display="block";
    loader.classList.remove("active");
  },400);
}

/* HOME */
function goHome(){
  document.querySelectorAll("iframe,embed").forEach(e=>e.style.display="none");
  home.style.display="block";
  homeBtn.style.display="none";
}
</script>

</body>
</html>
