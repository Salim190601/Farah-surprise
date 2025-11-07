
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>For Farah 💖</title>

<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">

<style>
  :root{
    --bg1: #fff7f8;
    --bg2: #fff0f4;
    --accent: #d6336c;
    --accent-dark: #a3244a;
    --muted: #6b6b6b;
    --card: rgba(255,255,255,0.75);
  }

  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0;
    font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    background: radial-gradient(circle at 10% 10%, #fff0f4 0%, #fff7f8 40%, #fffefc 100%);
    color:#333;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:24px;
  }

  .stage{
    width:100%;
    max-width:900px;
    min-height:520px;
    border-radius:18px;
    box-shadow: 0 10px 30px rgba(166,33,108,0.12);
    background: linear-gradient(180deg, rgba(255,255,255,0.85), rgba(255,250,250,0.9));
    overflow:hidden;
    position:relative;
    padding:32px;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
  }

  .frame{
    position:absolute;
    inset:0;
    pointer-events:none;
    background-image: radial-gradient(circle at 10% 10%, rgba(214,51,108,0.04), transparent 10%),
                      linear-gradient(120deg, rgba(214,51,108,0.02), transparent 40%);
  }

  header{
    text-align:center;
    margin-bottom:10px;
  }
  .logo{
    font-family: "Great Vibes", cursive;
    font-size:48px;
    letter-spacing:1px;
    color:var(--accent-dark);
    margin:0;
  }
  .sub{
    margin-top:-6px;
    color:var(--muted);
    font-size:14px;
  }

  .start-screen{
    display:flex;
    gap:18px;
    align-items:center;
    flex-direction:column;
    transition:opacity .45s ease, transform .45s ease;
  }

  .start-btn{
    appearance:none;
    border:0;
    background: linear-gradient(180deg,var(--accent),var(--accent-dark));
    color:white;
    padding:14px 30px;
    border-radius:999px;
    font-weight:600;
    font-size:18px;
    cursor:pointer;
    box-shadow: 0 8px 18px rgba(163,36,86,0.18);
    transform:translateY(0);
    transition:transform .18s ease, box-shadow .18s ease;
  }
  .start-btn:active{ transform:translateY(2px); box-shadow:0 4px 10px rgba(0,0,0,0.08); }

  .hint{
    font-size:13px;
    color:var(--muted);
  }

  .question-card{
    width:100%;
    max-width:680px;
    background:var(--card);
    border-radius:14px;
    padding:28px;
    text-align:center;
    box-shadow: 0 6px 20px rgba(166,33,108,0.06);
    backdrop-filter: blur(6px);
    transform-origin:center;
    transition:transform .45s cubic-bezier(.2,.9,.3,1), opacity .45s ease;
    opacity:0;
    transform:scale(.96);
    pointer-events:none;
  }
  .question-card.show{
    opacity:1;
    transform:scale(1);
    pointer-events:auto;
  }

  .question{
    font-family:"Great Vibes", cursive;
    font-size:42px;
    margin:6px 0 12px;
    color:var(--accent-dark);
  }
  .question small{
    display:block;
    font-family:Inter;
    font-size:14px;
    color:var(--muted);
    margin-top:-4px;
  }

  .options{
    margin-top:18px;
    display:flex;
    gap:14px;
    justify-content:center;
    flex-wrap:wrap;
  }

  button.option{
    appearance:none;
    border:2px solid rgba(163,36,86,0.12);
    background:transparent;
    padding:12px 22px;
    border-radius:999px;
    font-weight:600;
    cursor:pointer;
    min-width:120px;
    transition:transform .16s ease, background .16s ease, color .16s ease;
  }
  button.option:hover{ transform:translateY(-4px); }
  button.option.yes{
    background:linear-gradient(180deg,#ffccd8,#ff9bbf);
    border-color: rgba(163,36,86,0.18);
    color: #7a0836;
    box-shadow: 0 10px 24px rgba(214,51,108,0.12);
  }
  button.option.no{
    background:transparent;
    color:var(--muted);
  }

  .result{
    margin-top:20px;
    font-size:18px;
    color:var(--muted);
    min-height:44px;
  }

  .hearts{
    position:absolute;
    inset:0;
    pointer-events:none;
    overflow:hidden;
  }
  .heart{
    position:absolute;
    width:18px;height:18px;
    transform:translate(-50%,-50%) rotate(45deg);
    background:var(--accent);
    border-radius:4px 4px 0 0;
    opacity:0.9;
    filter: drop-shadow(0 6px 14px rgba(214,51,108,0.06));
    clip-path: polygon(50% 0%, 100% 25%, 75% 100%, 50% 80%, 25% 100%, 0% 25%);
  }

  #confetti {
    position:absolute;
    inset:0;
    width:100%;
    height:100%;
    pointer-events:none;
  }

  .footer-note{
    position:absolute;
    bottom:14px;
    left:18px;
    font-size:12px;
    color:var(--muted);
  }

  @media (max-width:640px){
    .logo{font-size:36px}
    .question{font-size:34px}
    .stage{padding:20px; min-height:520px}
  }

</style>
</head>
<body>
  <div class="stage" role="main" aria-labelledby="title">
    <div class="frame" aria-hidden="true"></div>
    <canvas id="confetti" aria-hidden="true"></canvas>

    <header>
      <h1 id="title" class="logo">For Farah 💖</h1>
      <div class="sub">A little question from my heart, just for you</div>
    </header>

    <div id="startScreen" class="start-screen" aria-hidden="false">
      <p style="max-width:70ch; text-align:center; font-size:16px; color:var(--muted); margin:0 6px 6px;">
        Hey Farah, I have something special to ask you — click Start when you’re ready. 💌
      </p>
      <button id="startBtn" class="start-btn" aria-label="Click to start">Start</button>
      <div class="hint">Made with love, from Salim ❤️</div>
    </div>

    <div id="questionCard" class="question-card" role="dialog" aria-modal="true" aria-hidden="true">
      <div class="question">Farah, will you be my girlfriend? <small>— please say yes 🥹</small></div>

      <div class="options" role="group" aria-label="Answers">
        <button id="yesBtn" class="option yes" aria-pressed="false">Yes 💖</button>
        <button id="noBtn" class="option no" aria-pressed="false">No 😢</button>
      </div>

      <div id="result" class="result" aria-live="polite"></div>
    </div>

    <div class="hearts" aria-hidden="true"></div>

    <div class="footer-note">Made with ❤️ by Salim</div>
  </div>

<script>
const startBtn = document.getElementById('startBtn');
const startScreen = document.getElementById('startScreen');
const questionCard = document.getElementById('questionCard');
const yesBtn = document.getElementById('yesBtn');
const noBtn = document.getElementById('noBtn');
const result = document.getElementById('result');
const heartsContainer = document.querySelector('.hearts');
const confettiCanvas = document.getElementById('confetti');

startBtn.addEventListener('click', () => {
  startScreen.style.opacity = 0;
  startScreen.style.transform = 'translateY(-8px)';
  startScreen.setAttribute('aria-hidden','true');
  setTimeout(() => {
    questionCard.classList.add('show');
    questionCard.setAttribute('aria-hidden','false');
    yesBtn.focus();
    spawnHearts(8);
  }, 300);
});

yesBtn.addEventListener('click', async () => {
  yesBtn.setAttribute('aria-pressed','true');
  noBtn.setAttribute('aria-pressed','false');
  result.textContent = "Nhebek Farouhti! 🥰 I’m so happy!";
  triggerConfetti();
  revealSweetMessages();
});

noBtn.addEventListener('click', () => {
  noBtn.setAttribute('aria-pressed','true');
  yesBtn.setAttribute('aria-pressed','false');
  result.innerHTML = "Aww, that’s okay 💔<br>I’ll always wish you happiness, Farah ❤️";
  spawnHearts(6,true);
});

function spawnHearts(count, muted=false){
  for(let i=0;i<count;i++){
    const h = document.createElement('div');
    h.className = 'heart';
    const x = 20 + Math.random()*60;
    const y = 20 + Math.random()*60;
    h.style.left = x + '%';
    h.style.top = y + '%';
    h.style.opacity = 0;
    heartsContainer.appendChild(h);
    const dx = (Math.random()*120 - 60);
    const dy = -60 - Math.random()*80;
    const dur = 2200 + Math.random()*1800;
    requestAnimationFrame(()=> {
      h.style.transition = `transform ${dur}ms cubic-bezier(.2,.9,.3,1), opacity 800ms ease`;
      h.style.transform = `translate(${dx}px, ${dy}px) rotate(${(Math.random()*40-20)}deg)`;
      h.style.opacity = muted ? 0.5 : 1;
    });
    setTimeout(()=> h.remove(), dur + 600);
  }
}

function triggerConfetti(){
  const ctx = confettiCanvas.getContext('2d');
  resizeCanvas();
  let particles = [];
  const W = confettiCanvas.width;
  const H = confettiCanvas.height;
  const colors = ["#ff6b9a","#ffd1dc","#ff9bbf","#f6a7c1","#ffdde6","#d6336c"];
  for(let i=0;i<120;i++){
    particles.push({
      x: W/2 + (Math.random()-0.5)*200,
      y: H/2 + (Math.random()-0.5)*80,
      vx: (Math.random()-0.5)*8,
      vy: -8 - Math.random()*6,
      size: 6 + Math.random()*8,
      rot: Math.random()*360,
      vr: (Math.random()-0.5)*12,
      color: colors[Math.floor(Math.random()*colors.length)],
      life: 80 + Math.random()*40
    });
  }
  let t = 0;
  const anim = () => {
    t++;
    ctx.clearRect(0,0,W,H);
    for(let i = particles.length-1; i>=0; i--){
      const p = particles[i];
      p.vy += 0.3;
      p.x += p.vx;
      p.y += p.vy;
      p.rot += p.vr;
      p.life--;
      ctx.save();
      ctx.translate(p.x,p.y);
      ctx.rotate(p.rot * Math.PI / 180);
      ctx.fillStyle = p.color;
      ctx.fillRect(-p.size/2, -p.size/2, p.size, p.size*0.65);
      ctx.restore();
      if(p.life <= 0 || p.y > H + 50) particles.splice(i,1);
    }
    if(particles.length>0 && t < 500){
      requestAnimationFrame(anim);
    } else {
      ctx.clearRect(0,0,W,H);
    }
  };
  anim();
}

function resizeCanvas(){
  confettiCanvas.width = confettiCanvas.clientWidth * devicePixelRatio;
  confettiCanvas.height = confettiCanvas.clientHeight * devicePixelRatio;
  const ctx = confettiCanvas.getContext('2d');
  ctx.setTransform(devicePixelRatio,0,0,devicePixelRatio,0,0);
}
window.addEventListener('resize', resizeCanvas);

function revealSweetMessages(){
  setTimeout(()=> {
    result.innerHTML = "You make my heart smile, Farouhti 🌸";
    spawnHearts(12);
  }, 900);
  setTimeout(()=> {
    result.innerHTML = "Farouhti, I’ve loved you from the moment I saw you. 💞<br>Let’s make memories and dream together. <br><br><strong>— Love, Salim ❤️</strong>";
    spawnHearts(16);
  }, 2200);
}

resizeCanvas();
</script>
</body>
</html>
