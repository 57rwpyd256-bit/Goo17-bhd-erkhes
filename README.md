<!doctype html>
<html lang="mn">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Goomarald — Special</title>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&family=Parisienne&display=swap" rel="stylesheet">
<style>
:root{
  --bg1:#f7d9e6;
  --bg2:#e8d9ff;
  --accent:#ff6fa6;
  --muted: rgba(255,255,255,0.85);
  --panel: rgba(255,255,255,0.06);
}
*{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%}
body{
  font-family: "Poppins", system-ui, -apple-system, "Segoe UI", Roboto, Arial;
  background: linear-gradient(135deg,var(--bg2),#fbe8f0 60%);
  color:#111;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:28px;
}
/* Main card */
.card{
  width: min(980px,96vw);
  height: 82vh;
  min-height:560px;
  border-radius:20px;
  padding:20px;
  display:flex;
  gap:18px;
  position:relative;
  overflow:hidden;
  box-shadow: 0 18px 60px rgba(80,40,70,0.12);
  background: linear-gradient(180deg, rgba(255,255,255,0.65), rgba(255,255,255,0.42));
  backdrop-filter: blur(6px) saturate(1.05);
}
/* Left column (menu) */
.left {
  width: 34%;
  min-width:260px;
  display:flex;
  flex-direction:column;
  gap:14px;
  align-items:flex-start;
  padding:18px;
}
.brand {
  display:flex;
  align-items:center;
  gap:12px;
}
.logo {
  width:56px;height:56px;border-radius:12px;background:linear-gradient(180deg,var(--accent),#ffb3d0);
  display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:20px;font-family: "Parisienne", cursive;
  box-shadow: 0 8px 24px rgba(255,100,150,0.12);
}
h1{font-size:1.35rem;color:#3b2b3b}
.subtitle{font-size:0.9rem;color:rgba(40,30,40,0.6)}
.menu {
  margin-top:8px;
  display:flex;
  flex-direction:column;
  gap:12px;
  width:100%;
}
.pill {
  display:inline-flex;
  align-items:center;
  gap:8px;
  padding:10px 14px;
  border-radius:999px;
  background:linear-gradient(180deg, rgba(255,255,255,0.85), rgba(255,255,255,0.85));
  box-shadow: 0 6px 22px rgba(0,0,0,0.06);
  cursor:pointer;
  font-weight:700;
  color:#6b3b4f;
  user-select:none;
}
.small-note{font-size:12px;color:rgba(0,0,0,0.45);margin-top:10px}
/* Right panel */
.right { flex:1; position:relative; display:flex; align-items:center; justify-content:center; padding:10px; }
.panel {
  width:100%; height:100%; border-radius:14px; position:relative; overflow:hidden;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  box-shadow: inset 0 0 40px rgba(255,255,255,0.02);
  padding:18px;
  display:flex;
  align-items:center;
  justify-content:center;
}
/* background photo */
.bg-photo {
  position:absolute; inset:0; background-position:center; background-size:cover; filter: blur(6px) saturate(.95) brightness(.72);
  z-index:0;
  transform: scale(1.03);
}
.bg-overlay{ position:absolute; inset:0; background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,200,230,0.02)); z-index:1; }
/* content area */
.content {
  position:relative; z-index:3; width:100%; max-width:760px; text-align:center; display:flex; flex-direction:column; align-items:center; gap:12px;
}
.main-card {
  width:100%; border-radius:12px; padding:18px; background: rgba(255,255,255,0.95); box-shadow: 0 12px 40px rgba(60,20,40,0.06);
}
/* image preview and thumbs */
.img-wrap{ position:relative; display:flex; flex-direction:column; align-items:center; gap:10px }
.main-img { width:auto; max-width:520px; max-height:52vh; border-radius:12px; box-shadow: 0 18px 48px rgba(80,40,70,0.08); cursor:pointer; display:block;
           opacity:0; transition: opacity .28s ease; }
.main-img.visible { opacity:1; }
.thumbs { display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin-top:6px }
.thumbs img { width:64px;height:64px;object-fit:cover;border-radius:8px;border:2px solid transparent; cursor:pointer; opacity:0.6 }
.thumbs img.active{ border-color: rgba(180,120,150,0.18); transform: scale(1.03); opacity:1 }
/* message card */
.msg-card { margin-top:12px; text-align:left; padding:12px 14px; border-radius:12px; background: linear-gradient(180deg, #fff, #fff); color:#3b2b3b; }
.msg-text{ 
  white-space:pre-wrap; max-height:26vh; overflow:auto; line-height:1.5; font-size:1rem; 
  opacity:0; transform: translateY(15px); transition: opacity 0.8s ease, transform 0.8s ease; 
}
.msg-text.visible{ opacity:1; transform:translateY(0); }
.controls-row { display:flex; gap:10px; justify-content:center; margin-top:12px }
.btn-ghost { padding:8px 12px; border-radius:999px; border:1px solid rgba(0,0,0,0.06); background:transparent; cursor:pointer }
.btn-primary { padding:10px 14px; border-radius:999px; background:linear-gradient(180deg,var(--accent),#ff9fc3); color:#fff; border:none; cursor:pointer; font-weight:700 }
/* lock overlay */
.lock-overlay{
  position:fixed; inset:0; display:flex; align-items:center; justify-content:center; z-index:60; background: linear-gradient(180deg, rgba(10,8,12,0.65), rgba(30,14,28,0.6));
}
.lock-box{ width:min(520px,92vw); background:linear-gradient(180deg, #fff, #fff); border-radius:12px; padding:22px; box-shadow: 0 40px 100px rgba(10,10,12,0.6); text-align:center; }
.lock-box h2{ font-size:1.25rem; margin-bottom:8px; color:#3b2b3b }
.lock-input{ width:100%; padding:12px 14px; border-radius:10px; border:1px solid rgba(0,0,0,0.08); margin-top:10px; font-size:1rem }
.lock-actions{ display:flex; gap:10px; margin-top:12px; justify-content:center }
/* small helpers */
.note-small{ font-size:12px; color:rgba(0,0,0,0.45) }
.badge { display:inline-block; padding:6px 10px; border-radius:999px; background:linear-gradient(180deg,#fff,#ffe6f0); color:#4b2b3b; box-shadow: 0 6px 18px rgba(255,105,180,0.06); font-weight:700; }
/* responsive */
@media (max-width:820px){
  .card{flex-direction:column;height:92vh}
  .left{width:100%;flex-direction:row;justify-content:space-between;padding:12px}
  .main-img{max-width:88vw; max-height:40vh}
  .msg-text{max-height:22vh}
  .thumbs img{width:52px;height:52px}
}
</style>
</head>
<body>

<div class="card" role="main" aria-live="polite">
  <div class="left">
    <div class="brand">
      <div class="logo">G</div>
      <div>
        <h1>Goomarald</h1>
        <div class="subtitle">0412 — Special Access</div>
      </div>
    </div>

    <div class="menu" aria-hidden="false">
      <div class="pill" id="openPic">1. Зураг (дарж үзэх)</div>
      <div class="pill" id="openMsg">2. Захиа (дарж үзэх)</div>
      <div class="pill" id="openGift">3. Бэлэг</div>
      <div class="small-note">Контентыг үзэхэд нэвтрэх код шаардлагатай — код оруулсан үед та бүх зүйлийг үзэж засварлах боломжтой.</div>
    </div>
  </div>

  <div class="right">
    <div class="panel" id="panel" aria-hidden="true">
      <div class="bg-photo" id="bgPhoto" style="background-image:url('https://i.postimg.cc/qMHmSt38/IMG-0216.png');"></div>
      <div class="bg-overlay"></div>

      <div class="content" id="contentArea" aria-hidden="true">
        <div class="main-card" id="mainCard">
          <div class="img-wrap" id="imgWrap">
            <img id="mainImg" class="main-img" src="" alt="Preview image (click for hearts/fireworks)" />
            <div class="thumbs" id="thumbs">
              <img data-src="https://i.postimg.cc/qMHmSt38/IMG-0216.png" src="https://i.postimg.cc/qMHmSt38/IMG-0216.png" alt="1">
              <img data-src="https://i.postimg.cc/gJfMYjBF/IMG-0214.png" src="https://i.postimg.cc/gJfMYjBF/IMG-0214.png" alt="2">
              <img data-src="https://i.postimg.cc/pL2sVgkN/IMG-7896.jpg" src="https://i.postimg.cc/pL2sVgkN/IMG-7896.jpg" alt="3">
              <img data-src="https://i.postimg.cc/8ztt7tnM/IMG-8600.jpg" src="https://i.postimg.cc/8ztt7tnM/IMG-8600.jpg" alt="4">
            </div>
          </div>

          <div class="msg-card" id="msgCard">
            <div class="msg-text" id="msgText">
Сайн уу Гоо маань өнөөдөр Гоогийн маань 17 насны төрсөн өдөр. Том анай болж байна даа яаана вэ надаас эгч болчихож байгаа юм байна шд хха.

2лаа танилцаад 7 сар өнгөрчээ бас л их худан явсан байгаа шүү тийнмээ?

4 сарын 12 нд чи бид 2-ын анх бие биенээ харсан, танилцасан өдөр санаж байна уу? Тэр өдөр тэр газар анх очоод л хаалгаар орох үед чи зогсож байсан. (har jeans har ungiin tgd make it gsn bichигtei tsamts tgd polito) өмсчихсөн байсан. Тэр үед хараад уаав ямар хөөрхөн охин бэ? Гээд дотроо бодож билээ тэгээд л шууд инста-г нь олоод дагах гэсэн ичээд л байж байсан чинь гэнэт намайг дагахаар нь барлаж билээ. Тэр үеийн 16 тай охин 17 хүрлээ дээ. Чи үргэлж гэрэлтээсэй үргэлж жаргалтай байгаарай. Гэж би үргэлж хүсэх болно оо. Гомдоож гуниглуулж байсан бол уучлаарай.

Заа төрсөн өдрийн баярын мэнд хүргье❤️ 🍀🍰🫂
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</div>

<div class="lock-overlay" id="lockOverlay">
  <div class="lock-box">
    <h2>Нэвтрэх код оруулна уу</h2>
    <input type="text" id="lockInput" class="lock-input" placeholder="Код" />
    <div class="lock-actions">
      <button class="btn-primary" id="submitCode">Нэвтрэх</button>
    </div>
    <div class="note-small">Зөв код: <span style="font-weight:700;">0412</span></div>
  </div>
</div>

<script>
// Lock logic
const lockOverlay = document.getElementById('lockOverlay');
const lockInput = document.getElementById('lockInput');
const submitCode = document.getElementById('submitCode');
let unlocked = false;

submitCode.addEventListener('click', ()=>{
  if(lockInput.value==='0412'){
    unlocked=true;
    lockOverlay.style.display='none';
    document.getElementById('panel').setAttribute('aria-hidden','false');
  } else { alert('Зөв код оруулна уу'); }
});

// Image gallery
const mainImg = document.getElementById('mainImg');
const thumbs = document.querySelectorAll('#thumbs img');

thumbs.forEach(t=>{
  t.addEventListener('click', ()=> {
    mainImg.src = t.dataset.src;
    mainImg.classList.add('visible');
    thumbs.forEach(tt=>tt.classList.remove('active'));
    t.classList.add('active');
  });
});

// auto-select first
mainImg.src=thumbs[0].dataset.src;
mainImg.classList.add('visible');
thumbs[0].classList.add('active');

// Motion message
const msgText = document.getElementById('msgText');
document.getElementById('openMsg').addEventListener('click', ()=>{
  if(!unlocked){ alert('Нэвтэрнэ үү (код шаардлагатай)'); return; }
  msgText.classList.add('visible');
  msgText.scrollIntoView({behavior:'smooth', block:'center'});
});

// Gift button (Google Form)
document.getElementById('openGift').addEventListener('click', ()=>{
  if(!unlocked){ alert('Нэвтэрнэ үү (код шаардлагатай)'); return; }
  window.open('https://docs.google.com/forms/d/1ONQ9O-NbaSf92reybNlX4E9tRMW9tlOR8wshCYAAYp8/viewform','_blank');
});

// Image click confetti/heart effect
mainImg.addEventListener('click',()=>{
  spawnConfetti(60);
});
function spawnConfetti(amount){
  for(let i=0;i<amount;i++){
    const div=document.createElement('div');
    div.style.position='fixed';
    div.style.width='10px'; div.style.height='10px';
    div.style.background=['#ff6fa6','#ffe6f0','#ff9fc3','#ffa6d2'][Math.floor(Math.random()*4)];
    div.style.borderRadius='50%';
    div.style.left=(Math.random()*window.innerWidth)+'px';
    div.style.top=(Math.random()*window.innerHeight)+'px';
    div.style.opacity=1;
    div.style.zIndex=9999;
    div.style.pointerEvents='none';
    document.body.appendChild(div);
    let t=0;
    const id=setInterval(()=>{
      t+=1;
      div.style.top = parseFloat(div.style.top) + 2 + 'px';
      div.style.opacity = 1 - t/80;
      if(t>80){ div.remove(); clearInterval(id); }
    },10);
  }
}
</script>

</body>
</html>
