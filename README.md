# Minha gatinha 💝

<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mensagem para Vida</title>
<style>
  html, body {
    margin: 0;
    padding: 0;
    height: 100%;
    overflow: hidden;
    font-family: Arial, sans-serif;
    scroll-behavior: smooth;
    background: pink;
    color: white;
  }

  /* Fundo animado de corações */
  .heart {
    position: absolute;
    width: 30px;
    height: 30px;
    background: red;
    transform: rotate(-45deg);
    animation: float 4s infinite ease-in-out;
  }
  .heart::before,
  .heart::after {
    content: '';
    position: absolute;
    width: 30px;
    height: 30px;
    background: red;
    border-radius: 50%;
  }
  .heart::before { top: -15px; left: 0; }
  .heart::after { left: 15px; top: 0; }

  @keyframes float {
    0% { transform: translateY(0) rotate(-45deg); }
    50% { transform: translateY(-50px) rotate(-45deg); }
    100% { transform: translateY(0) rotate(-45deg); }
  }

  section {
    position: relative;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    z-index: 1;
    padding: 20px;
    box-sizing: border-box;
    background-size: cover;
    background-position: center;
  }

  .text-section {
    position: relative;
    z-index: 2;
    max-width: 80%;
    font-size: 1.8rem;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.7);
  }

  .arrow {
    position: absolute;
    bottom: 20px;
    font-size: 3rem;
    animation: bounce 1.5s infinite;
    z-index: 2;
  }

  @keyframes bounce {
    0%,100% { transform: translateY(0);}
    50% { transform: translateY(-15px);}
  }
</style>
</head>
<body>

<!-- Fundo de corações -->
<div id="hearts"></div>

<!-- Seção 1 -->
<section>
  <div class="text-section">
    Vida eu sei que não está sendo fácil para você, mas tudo isso vai passar e só é uma fase. Eu sei que você não está nada bem, mas com o tempo você vai melhorar. Eu te amo muito ⬇️
  </div>
  <div class="arrow">⬇️</div>
</section>

<!-- Seção 2 -->
<section>
  <div class="text-section">
    Não é justo vocês estar comigo nos momentos bons e ruins e eu estar com você só nos bons e nos ruins eu te deixar sozinha. Agente é um casal e vamos passar tudo isso junto, minha princesa. Eu te amo muito e esse site é pra você ver uma pequena demonstração do meu amor.
  </div>
</section>

<!-- Seção 3 (imagem) -->
<section style="background-image: url('https://i.imgur.com/mO81FM5.jpg');">
</section>

<!-- Seção 4 (imagem) -->
<section style="background-image: url('https://i.imgur.com/XOvhPMq.jpg');">
</section>

<!-- Seção 5 (imagem) -->
<section style="background-image: url('https://i.imgur.com/Eh4WKpM.jpg');">
</section>

<script>
  // Criar corações animados
  const totalHearts = 30;
  for(let i=0;i<totalHearts;i++){
    const heart = document.createElement('div');
    heart.classList.add('heart');
    heart.style.left = Math.random() * window.innerWidth + 'px';
    heart.style.top = Math.random() * window.innerHeight + 'px';
    heart.style.animationDuration = (3 + Math.random() * 3) + 's';
    heart.style.opacity = Math.random();
    document.body.appendChild(heart);
  }

  // Scroll entre seções
  const sections = document.querySelectorAll('section');
  let currentIndex = 0;
  window.addEventListener('wheel', function(event){
    if(event.deltaY > 0){
      currentIndex = Math.min(currentIndex + 1, sections.length - 1);
    } else if(event.deltaY < 0){
      currentIndex = Math.max(currentIndex - 1, 0);
    }
    sections[currentIndex].scrollIntoView({behavior:'smooth'});
  });
</script>

</body>
</html>
