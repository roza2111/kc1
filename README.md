<!DOCTYPE html>
<html lang="pl">
<head>
<meta charset="UTF-8">
<title>Dla Ciebie ❤️</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ffd1dc,#fff0f5);
    font-family:'Segoe UI',sans-serif;
    overflow:hidden;
}

.container{
    text-align:center;
    z-index:2;
}

h1{
    color:#ff4d88;
    font-size:3em;
    margin-bottom:20px;
    animation:pulse 2s infinite;
}

button{
    border:none;
    border-radius:30px;
    padding:15px 35px;
    font-size:22px;
    cursor:pointer;
    margin:10px;
    transition:0.3s;
}

#yes{
    background:#ff5c9d;
    color:white;
}

#no{
    background:white;
    color:#666;
}

.heart{
    position:absolute;
    color:white;
    animation:float 10s linear infinite;
}

@keyframes float{
    from{
        transform:translateY(100vh);
        opacity:0;
    }
    20%{
        opacity:1;
    }
    to{
        transform:translateY(-120px);
        opacity:0;
    }
}

@keyframes pulse{
    50%{
        transform:scale(1.05);
    }
}
</style>
</head>
<body>

<div class="container">
    <h1>❤️ Czy do mnie wrócisz? ❤️</h1>

    <button id="yes">Tak ❤️</button>
    <button id="no">Nie</button>
</div>

<script>
const noBtn = document.getElementById("no");
const yesBtn = document.getElementById("yes");

const texts = [
    "Na pewno nie? 🥺",
    "Pomyśl jeszcze ❤️",
    "Tęsknię... 💌",
    "Naprawdę? 😢",
    "Może jednak? 🌹",
    "Daj szansę losowi ✨"
];

let count = 0;
let size = 22;

noBtn.onclick = () => {
    if(count < texts.length){
        noBtn.innerText = texts[count];
        count++;
    }

    size += 8;
    yesBtn.style.fontSize = size + "px";
};

yesBtn.onclick = () => {
    document.body.innerHTML = `
    <div style="text-align:center">
        <h1 style="font-size:4em;color:#ff4d88">
            ❤️ To najszczęśliwszy dzień ❤️
        </h1>
        <p style="font-size:1.5em;color:#666">
            Obiecuję, że będzie warto. 💖
        </p>
    </div>
    `;
};

for(let i=0;i<40;i++){
    const heart=document.createElement("div");
    heart.className="heart";
    heart.innerHTML="❤";
    heart.style.left=Math.random()*100+"vw";
    heart.style.fontSize=(15+Math.random()*35)+"px";
    heart.style.animationDelay=Math.random()*10+"s";
    document.body.appendChild(heart);
}
</script>

</body>
</html>
