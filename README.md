# love
joguinho
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>💖 Um pedido especial 💖</title>

<style>
body {
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  font-family: 'Comic Sans MS', cursive;
  text-align: center;
  color: white;
  padding: 30px;
}

.container {
  background: rgba(255,255,255,0.2);
  border-radius: 20px;
  padding: 30px;
  display: inline-block;
}

h1 { font-size: 2.5em; }
p { font-size: 1.3em; }

button {
  font-size: 1.2em;
  padding: 12px 20px;
  margin: 15px;
  border-radius: 10px;
  border: none;
  cursor: pointer;
}

#sim {
  background-color: #ff4d6d;
  color: white;
}

#nao {
  background-color: gray;
  position: absolute;
}

/* Slideshow */
.slideshow {
  width: 250px;
  height: 250px;
  margin: 20px auto;
  border-radius: 20px;
  overflow: hidden;
}

.slideshow img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Corações */
.heart {
  position: fixed;
  font-size: 20px;
  animation: subir 4s linear infinite;
}

@keyframes subir {
  from { transform: translateY(100vh); }
  to { transform: translateY(-10vh); }
}

</style>
</head>

<body>

<!-- 🎵 MÚSICA -->
<audio autoplay loop>
  <source src="musica.mp3" type="audio/mpeg">
</audio>

<div class="container">

  <h1>💖 Ei, você 💖</h1>

  <!-- 🖼️ SLIDESHOW -->
  <div class="slideshow">
    <img id="foto" src="foto1.jpg">
  </div>

  <p>Desde que você entrou na minha vida... tudo ficou mais bonito 💕</p>

  <h2>Quer namorar comigo? 🥺💌</h2>

  <button id="sim" onclick="respostaSim()">SIM 💖</button>
  <button id="nao" onmouseover="foge()">NÃO 😢</button>

</div>

<script>
// 📸 FOTOS (troque pelos seus arquivos)
let imagens = ["foto1.jpg", "foto2.jpg", "foto3.jpg"];
let i = 0;

setInterval(() => {
  i = (i + 1) % imagens.length;
  document.getElementById("foto").src = imagens[i];
}, 2000);

// 💖 BOTÃO SIM
function respostaSim() {
  document.body.innerHTML = `
    <h1>💖 AAAAAA 💖</h1>
    <p>Eu vou te fazer muito feliz!!! 🥺💞</p>
  `;
}

// 😆 BOTÃO NÃO FUGINDO
function foge() {
  const btn = document.getElementById("nao");
  btn.style.left = Math.random() * window.innerWidth + "px";
  btn.style.top = Math.random() * window.innerHeight + "px";
}

// 💕 CORAÇÕES
setInterval(() => {
  let heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "💖";
  heart.style.left = Math.random() * 100 + "vw";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 4000);
}, 300);
</script>

</body>
</html>
