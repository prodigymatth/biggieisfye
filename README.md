
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Prodigy Math Platform</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
    @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Inter:wght@400;500;600&display=swap');

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        min-height: 100vh;
        background: #0c0c0c;
        color: #f5f5f5;
        font-family: 'Inter', system-ui, sans-serif;
        overflow: hidden;
        position: relative;
    }

    /* Brighter elegant background */
    body::before {
        content: "";
        position: fixed;
        inset: 0;
        background: 
            radial-gradient(circle at 20% 30%, rgba(255,255,255,0.12) 0%, transparent 60%),
            radial-gradient(circle at 80% 70%, rgba(255,255,255,0.09) 0%, transparent 65%);
        z-index: -1;
        animation: bgBreath 28s ease infinite alternate;
    }

    /* Splash Screen */
    #splashScreen {
        position: fixed;
        inset: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        background: rgba(12,12,12,0.98);
        z-index: 1000;
        transition: opacity 1.8s ease;
    }

    .splashContent {
        text-align: center;
    }

    .splashContent h1 {
        font-family: 'Great Vibes', cursive;
        font-size: 92px;
        font-weight: 400;
        letter-spacing: -2px;
        color: #ffffff;
        text-shadow: 0 0 40px rgba(255,255,255,0.4);
        margin-bottom: 12px;
        animation: titleFloat 6s ease infinite alternate;
    }

    .splashContent p {
        font-size: 18px;
        color: #cccccc;
        letter-spacing: 2px;
        opacity: 0;
        animation: fadeInText 2s ease 1s forwards;
    }

    /* Main Menu */
    .container {
        display: none;
        height: 100vh;
        overflow-y: auto;
        padding: 130px 25px 100px;
        text-align: center;
        scrollbar-width: thin;
        scrollbar-color: #777 #1f1f1f;
    }

    .container::-webkit-scrollbar-thumb {
        background: #777;
        border-radius: 10px;
    }

    h2 {
        font-family: 'Great Vibes', cursive;
        font-size: 82px;
        font-weight: 400;
        color: #ffffff;
        margin-bottom: 95px;
        text-shadow: 0 10px 30px rgba(0,0,0,0.6);
        animation: titleFloat 7s ease infinite alternate;
    }

    .buttonContainer {
        display: flex;
        flex-direction: column;
        gap: 22px;
        max-width: 410px;
        margin: 0 auto;
    }

    .gameBtn {
        padding: 21px 34px;
        background: rgba(255,255,255,0.07);
        border: 1px solid rgba(255,255,255,0.22);
        color: #f0f0f0;
        font-size: 17.5px;
        font-weight: 500;
        border-radius: 16px;
        cursor: pointer;
        transition: all 0.5s cubic-bezier(0.23, 1, 0.32, 1);
        box-shadow: 0 10px 30px rgba(0,0,0,0.55);
    }

    .gameBtn:hover {
        background: rgba(255,255,255,0.18);
        border-color: rgba(255,255,255,0.55);
        transform: translateY(-7px);
        box-shadow: 0 22px 50px rgba(0,0,0,0.7);
    }

    #homeBtn {
        position: fixed;
        top: 32px;
        left: 32px;
        padding: 12px 28px;
        font-size: 15px;
        background: rgba(255,255,255,0.06);
        border: 1px solid rgba(255,255,255,0.28);
        border-radius: 12px;
        color: #f0f0f0;
        cursor: pointer;
        display: none;
        z-index: 300;
        transition: all 0.3s ease;
    }

    #homeBtn:hover {
        background: rgba(255,255,255,0.18);
        transform: scale(1.06);
    }

    iframe, embed {
        position: fixed;
        inset: 0;
        width: 100%;
        height: 100%;
        display: none;
        border: none;
        animation: gameEnter 0.8s ease forwards;
    }

    /* Animations */
    @keyframes bgBreath {
        from { opacity: 0.75; }
        to { opacity: 0.95; }
    }

    @keyframes titleFloat {
        from { transform: translateY(-8px); }
        to { transform: translateY(8px); }
    }

    @keyframes fadeInText {
        to { opacity: 1; }
    }

    @keyframes gameEnter {
        from { opacity: 0; transform: scale(1.05); filter: blur(12px); }
        to { opacity: 1; transform: scale(1); filter: blur(0); }
    }
</style>
</head>
<body>

    <!-- Splash Screen -->
    <div id="splashScreen">
        <div class="splashContent">
            <h1>Prodigy</h1>
            <p>Mathematics Reimagined</p>
        </div>
    </div>

    <!-- Home Button -->
    <button id="homeBtn" onclick="goHome()">← Menu</button>

    <!-- Main Menu -->
    <div class="container" id="homeScreen">
        <h2>Prodigy</h2>
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
            <button class="gameBtn" onclick="openGame('agentFrame')">Agent Walker</button>
        </div>
    </div>

    <!-- Games -->
    <iframe id="hoodaFrame" src="https://www.hoodamath.com/"></iframe>
    <iframe id="playFrame" src="https://www.playtropolis.com"></iframe>
    <iframe id="gFrame" src="https://ghub-light.neocities.org/"></iframe>
    <iframe id="minecraftFrame" src="https://eaglercraft.com/"></iframe>
    <embed id="infiniteFrame" src="https://infinite-craft.org/infinite-craft/"></embed>
    <iframe id="soundboardFrame" src="https://www.myinstants.com/en/index/us/"></iframe>
    <iframe id="mathFrame" src="https://www.coolmathgames.com/"></iframe>
    <iframe id="cheeseFrame" src="https://stanthecheeseman.github.io/"></iframe>
    <iframe id="basketFrame" src="https://www.twoplayergames.org/game/basket-random"></iframe>
    <iframe id="buildnowFrame" src="https://buildnow-gg.io/"></iframe>
    <iframe id="hahaFrame" src="https://www.hahagames.com/"></iframe>
    <iframe id="gamaFrame" src="https://playgama.com"></iframe>
    <iframe id="agentFrame" src="https://www.twoplayergames.org/game/agent-walker-vs-skibidi-toilets"></iframe>

<script>
    const correctCode = "I hate math";
    let typed = "";

    // Secret unlock
    document.addEventListener("keydown", function(e) {
        if (e.key.length === 1 || e.key === " ") {
            typed += e.key;
        }

        if (typed.includes(correctCode)) {
            const splash = document.getElementById("splashScreen");
            splash.style.opacity = "0";
            setTimeout(() => {
                splash.style.display = "none";
                document.getElementById("homeScreen").style.display = "block";
                typed = "";
            }, 1700);
        }

        if (typed.length > 40) typed = typed.slice(-40);
    });

    const home = document.getElementById("homeScreen");
    const homeBtn = document.getElementById("homeBtn");
    const frames = document.querySelectorAll("iframe, embed");
    const originalSrcs = Array.from(frames).map(f => f.src);

    function openGame(id) {
        home.style.display = "none";
        frames.forEach(f => f.style.display = "none");
        document.getElementById(id).style.display = "block";
        homeBtn.style.display = "block";
    }

    function goHome() {
        homeBtn.style.display = "none";
        home.style.display = "block";
        frames.forEach((f, i) => {
            f.style.display = "none";
            f.src = originalSrcs[i];
        });
    }

    // Panic button: press \ to open Google Classroom
    document.addEventListener("keydown", e => {
        if (e.key === "\\") {
            window.location.href = "https://classroom.google.com/";
        }
    });
</script>
</body>
</html>
