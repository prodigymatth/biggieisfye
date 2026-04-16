<html lang="en">
<head>
<meta charset="UTF-8">
<title>Prodigy Math Lesson</title>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',sans-serif}

/* BACKGROUND */
body{
min-height:100vh;
background:linear-gradient(rgba(30,0,70,.7),rgba(10,0,30,.9)),
url('https://media.gettyimages.com/id/881752658/video/journey-through-galaxy.jpg?s=640x640&k=20&c=ITfk5mu21pnyUjb7tTndTm8LMBqpPS4YBMY2Il_nGyQ=') center/cover fixed;
color:white;
overflow-x:hidden;
}

/* ACCESS */
#passwordScreen{
position:fixed;inset:0;
display:flex;
justify-content:center;
align-items:center;
background:rgba(40,0,80,.95);
z-index:999;
}

.passwordBox{
background:rgba(60,0,110,.95);
padding:40px;
border-radius:18px;
text-align:center;
width:320px;
}

#accessText{font-size:26px}

/* SECRET */
#secretClick{
position:fixed;top:0;right:0;
width:100px;height:100px;
z-index:1000;
}

#whitelistBtn{
position:fixed;top:15px;right:15px;
padding:8px 12px;
background:#7c3aed;
color:white;
border:0;
border-radius:8px;
display:none;
z-index:1001;
cursor:pointer;
}

/* LOADER */
#loader{
position:fixed;inset:0;
display:flex;
justify-content:center;
align-items:center;
background:#2e0255;
color:white;
font-size:28px;
transform:translateX(-100%);
transition:.25s;
z-index:15;
}
#loader.active{transform:translateX(0)}

/* HOME */
.container{display:none;text-align:center;padding-top:70px}
h1{font-size:70px}

.buttonContainer{
display:flex;
flex-direction:column;
gap:10px;
width:280px;
margin:auto;
}

.gameBtn{
padding:13px;
background:#5a00a5;
color:white;
border:0;
cursor:pointer;
}

/* HOME BUTTON (RESTORED EXACT STYLE) */
#homeBtn{
position:fixed;
top:15px;
left:15px;
padding:6px 10px;
font-size:13px;
background:rgba(255,255,255,.08);
border:1px solid rgba(0,0,0,.2);
border-radius:4px;
color:#ccc;
display:none;
z-index:20;
cursor:pointer;
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
    <h2 id="accessText">Checking Access...</h2>
  </div>
</div>

<!-- SECRET -->
<div id="secretClick"></div>
<button id="whitelistBtn">wi</button>

<!-- LOADER -->
<div id="loader">onclu</div>

<!-- HOME BUTTON -->
<button id="homeBtn" onclick="goHome()">home</button>

<!-- HOME MENU -->
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

<!-- ALL IFRAME GAMES -->
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
let clicks = 0;

const screen = document.getElementById("passwordScreen");
const home = document.getElementById("homeScreen");
const loader = document.getElementById("loader");
const btn = document.getElementById("whitelistBtn");
const homeBtn = document.getElementById("homeBtn");
const audio = document.getElementById("lofi");

/* CHECK ACCESS */
window.onload=()=>{
  if(wl) enter();
  else document.getElementById("accessText").innerText="not white listed unable to join";
};

/* ENTER */
function enter(){
  loader.classList.add("active");
  setTimeout(()=>{
    screen.style.display="none";
    loader.classList.remove("active");
    home.style.display="block";
    audio.volume=.2;
    audio.play();
  },1200);
}

/* SECRET CLICK (9 taps) */
document.getElementById("secretClick").onclick=()=>{
  if(++clicks===9) btn.style.display="block";
};

/* WI BUTTON (DISAPPEARS AFTER CLICK) */
btn.onclick=()=>{
  localStorage.setItem("wl","1");
  btn.style.display="none";
  enter();
};

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

/* HOME BUTTON (RESTORED EXACT BEHAVIOR) */
function goHome(){
  document.querySelectorAll("iframe,embed").forEach(e=>e.style.display="none");
  home.style.display="block";
  homeBtn.style.display="none";
}
</script>

</body>
</html>
