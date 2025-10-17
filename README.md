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

/* Card */
.card{
  width:min(980px,96vw);
  height:82vh;
  min-height:560px;
  border-radius:20px;
  display:flex;
  gap:18px;
  position:relative;
  overflow:hidden;
  box-shadow:0 18px 60px rgba(80,40,70,0.12);
  background:linear-gradient(180deg, rgba(255,255,255,0.65), rgba(255,255,255,0.42));
  backdrop-filter:blur(6px) saturate(1.05);
}

/* Left menu */
.left{ width:34%; min-width:260px; display:flex; flex-direction:column; gap:14px; padding:18px;}
.brand{ display:flex; align-items:center; gap:12px; }
.logo{ width:56px;height:56px;border-radius:12px;background:linear-gradient(180deg,var(--accent),#ffb3d0);
display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:20px;font-family:"Parisienne",cursive;
box-shadow:0 8px 24px rgba(255,100,150,0.12);}
h1{font-size:1.35rem;color:#3b2b3b}
.subtitle{font-size:0.9rem;color:rgba(40,30,40,0.6)}
.menu{margin-top:8px; display:flex; flex-direction:column; gap:12px; width:100%}
.pill{display:inline-flex; align-items:center; gap:8px; padding:10px 14px; border-radius:999px; background:linear-gradient(180deg, rgba(255,255,255,0.85), rgba(255,255,255,0.85)); box-shadow:0 6px 22px rgba(0,0,0,0.06); cursor:pointer; font-weight:700; color:#6b3b4f; user-select:none;}
.small-note{font-size:12px;color:rgba(0,0,0,0.45);margin-top:10px}

/* Right panel */
.right{ flex:1; position:relative; display:flex; align-items:center; justify-content:center; padding:10px;}
.panel{width:100%; height:100%; border-radius:14px; position:relative; overflow:hidden; padding:18px; display:flex; align-items:center; justify-content:center; background:rgba(255,255,255,0.05);}

/* Motion background */
.bg-photo{ position:absolute; inset:0; background-position:center; background-size:cover; filter: blur(6px) saturate(.95) brightness(.72); z-index:0; transform: scale(1.03);}
.bg-overlay{ position:absolute; inset:0; z-index:1; background:linear-gradient(45deg, rgba(255,200,230,0.06), rgba(255,255,255,0.02)); background-size:200% 200%; animation: flowBG 20s linear infinite;}

@keyframes flowBG{
  0%{ background-position:0% 0%;}
  50%{ background-position:100% 100%;}
  100%{ background-position:0% 0%;}
}

/* Content */
.content{ position:relative; z-index:3; width:100%; max-width:760px; text-align:center; display:flex; flex-direction:column; align-items:center; gap:12px;}
.main-card{ width:100%; border-radius:12px; padding:18px; background: rgba(255,255,255,0.95); box-shadow:0 12px 40px rgba(60,20,40,0.06); }

/* Images */
.img-wrap{ position:relative; display:flex; flex-direction:column; align-items:center; gap:10px}
.main-img{ width:auto; max-width:520px; max-height:52vh; border-radius:12px; box-shadow:0 18px 48px rgba(80,40,70,0.08); cursor:pointer; display:block; opacity:0; transition:opacity .28s ease;}
.main-img.visible{ opacity:1; }
.thumbs{ display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin-top:6px}
.thumbs img{ width:64px;height:64px; object-fit:cover; border-radius:8px; border:2px solid transparent; cursor:pointer; opacity:0.6}
.thumbs img.active{ border-color: rgba(180,120,150,0.18); transform: scale(1.03); opacity:1; }

/* Message */
.msg-card{ margin-top:12px; text-align:left; padding:12px 14px; border-radius:12px; background: linear-gradient(180deg, #fff, #fff); color:#3b2b3b; }
.msg-text{ white-space:pre-wrap; max-height:26vh; overflow:auto; line-height:1.5; font-size:1rem; display:none}
.msg-text.visible{ display:block}
.controls-row{ display:flex; gap:10px; justify-content:center; margin-top:12px }
.btn-ghost{ padding:8px 12px; border-radius:999px; border:1px solid rgba(0,0,0,0.06); background:transparent; cursor:pointer}
.btn-primary{ padding:10px 14px; border-radius:999px; background:linear-gradient(180deg,var(--accent),#ff9fc3); color:#fff; border:none; cursor:pointer; font-weight:700 }

/* Hearts / sparkles layer */
#heartsLayer, #sparkles{ position:absolute; inset:0; z-index:17; pointer-events:none; }

/* Responsive */
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
    <div class="menu">
      <div class="pill" id="openPic">1. Зураг (дарж үзэх)</div>
      <div class="pill" id="openMsg">2. Захиа (дарж үзэх)</div>
      <div class="pill" id="openGift">3. Бэлэг</div>
      <div class="small-note">Контентыг үзэхэд нэвтрэх код шаардлагатай.</div>
    </div>
  </div>

  <div class="right">
    <div class="panel" id="panel">
      <div class="bg-photo" id="bgPhoto" style="background-image:url('https://i.postimg.cc/qMHmSt38/IMG-0216.png');"></div>
      <div class="bg-overlay"></div>
      <div class="content" id="contentArea">
        <div class="main-card" id="mainCard">
          <div class="img-wrap" id="imgWrap">
            <img id="mainImg" class="main-img" src="" alt="Preview image"/>
            <div class="thumbs" id="thumbs">
              <img data-src="https://i.postimg.cc/qMHmSt38/IMG-0216.png" src="https://i.postimg.cc/qMHmSt38/IMG-0216.png" alt="1">
              <img data-src="https://i.postimg.cc/gJfMYjBF/IMG-0214.png" src="https://i.postimg.cc/gJfMYjBF/IMG-0214.png" alt="2">
              <img data-src="https://i.postimg.cc/pL2sVgkN/IMG-7896.jpg" src="https://i.postimg.cc/pL2sVgkN/IMG-7896.jpg" alt="3">
              <img data-src="https://i.postimg.cc/8ztt7tnM/IMG-8600.jpg" src="https://i.postimg.cc/8ztt7tnM/IMG-8600.jpg" alt="4">
            </div>
            <div class="note-small" style="margin-top:6px">Зураг харахын тулд "1. Зураг" дээр дарна.</div>
          </div>

          <div class="msg-card" id="msgCard">
            <div style="display:flex;justify-content:space-between;align-items:center">
              <div style="display:flex;gap:8px;align-items:center">
                <div class="badge">Message</div>
                <div class="note-small">"2. Захиа" дээр дарж захиаг үзнэ үү.</div>
              </div>
              <div>
                <button class="btn-ghost" id="editMsgBtn">Edit</button>
              </div>
            </div>
            <div class="msg-text" id="msgText">Сайн уу Гоо маань өнөөдөр Гоогийн маань 17 насны төрсөн өдөр. Том анай болж байна даа яаана вэ надаас эгч болчихож байгаа юм байна шд хха.<br><br>2лаа танилцаад 7 сар өнгөрчээ бас л их худан явсан байгаа шүү тийнмээ?<br><br>4 сарын 12 нд чи бид 2-ын анх бие биенээ харсан, танилцасан өдөр санаж байна уу? Тэр өдөр тэр газар анх очоод л хаалгаар орох үед чи зогсож байсан. (  har jeans har ungiin tgd make it gsn bichигtei tsamts tgd polito )өмсчихсөн байсан. Тэр үед хараад уаав ямар хөөрхөн охин бэ? Гээд дотроо бодож билээ тэгээд л шууд инста-г нь олоод дагах гэсэн ичээд л байж байсан чинь гэнэт намайг дагахаар нь барлаж билээ. Тэр үеийн 16 тай охин 17 хүрлээ дээ. Чи үргэлж гэрэлтээсэй үргэлж жаргалтай байгаарай. Гэж би үргэлж хүсэх болно оо. Гомдоож гуниглуулж байсан бол уучлаарай.<br><br>Заа төрсөн өдрийн баярын мэнд хүргье❤️ 🍀🍰🫂</div>
          </div>

          <div class="controls-row">
            <button class="btn-primary" id="openGiftBtn">🎀 Бэлэг авах</button>
            <button class="btn-ghost" id="muteBtn">🔊 Music: Off</button>
          </div>
        </div>
      </div>

      <!-- Canvas layers for effects -->
      <canvas id="fxCanvas" style="position:absolute;inset:0;z-index:20;pointer-events:none"></canvas>
      <div id="heartsLayer"></div>
      <div id="sparkles"></div>
    </div>
  </div>
</div>

<!-- Lock overlay -->
<div class="lock-overlay" id="lockOverlay">
  <div class="lock-box">
    <p>Нэвтрэх код оруулна уу:</p>
    <input type="text" id="lockInput" placeholder="код оруулна уу">
    <button id="lockBtn">Нээх</button>
    <p id="lockMsg" style="color:red;font-size:0.85rem;margin-top:6px;"></p>
  </div>
</div>

<script>
// Lock system
const code="0412";
const lockOverlay=document.createElement("div");
lockOverlay.id="lockOverlay";
document.body.appendChild(lockOverlay);
lockOverlay.innerHTML=`<div style="position:fixed;inset:0;background:#0009;display:flex;align-items:center;justify-content:center;z-index:99">
<div style="background:#fff;padding:20px;border-radius:14px;text-align:center">
<p>Нэвтрэх код оруулна уу:</p>
<input type="text" id="lockInput">
<button id="lockBtn">Нээх</button>
<p id="lockMsg" style="color:red;margin-top:6px;font-size:14px"></p>
</div></div>`;
const lockInput=document.getElementById("lockInput");
const lockBtn=document.getElementById("lockBtn");
const lockMsg=document.getElementById("lockMsg");
lockBtn.addEventListener("click",()=>{
  if(lockInput.value===code){
    lockOverlay.style.display="none";
  }else{
    lockMsg.textContent="Код буруу байна. Дахин оролдоно уу.";
  }
});

// Image gallery
const mainImg=document.getElementById("mainImg");
const thumbs=document.querySelectorAll(".thumbs img");
thumbs.forEach(t=>{
  t.addEventListener("click",()=>{ 
    mainImg.src=t.dataset.src;
    mainImg.classList.add("visible");
    thumbs.forEach(x=>x.classList.remove("active"));
    t.classList.add("active");
  })
})

// Message toggle
const msgText=document.getElementById("msgText");
document.getElementById("openMsg").addEventListener("click",()=>{msgText.classList.toggle("visible");});

// Gift button
document.getElementById("openGiftBtn").addEventListener("click",()=>{window.open("https://docs.google.com/forms/d/1ONQ9O-NbaSf92reybNlX4E9tRMW9tlOR8wshCYAAYp8/viewform","_blank")})

// Hearts + sparkles effect
function createHeart(){ 
  const heart=document.createElement("div");
  heart.textContent="❤️"; 
  heart.style.position="absolute";
  heart.style.fontSize=Math.random()*32+12+"px";
  heart.style.left=Math.random()*window.innerWidth+"px";
  heart.style.top=window.innerHeight+"px";
  heart.style.opacity=Math.random();
  heart.style.pointerEvents="none";
  document.getElementById("heartsLayer").appendChild(heart);
  let top=parseFloat(heart.style.top);
  const id=setInterval(()=>{
    top-=1+Math.random()*2; 
    heart.style.top=top+"px";
    if(top< -50){ heart.remove(); clearInterval(id);}
  },20)
}
setInterval(createHeart,250)

// Sparkles
function createSparkle(){
  const sparkle=document.createElement("div");
  sparkle.style.position="absolute";
  sparkle.style.width=sparkle.style.height="4px";
  sparkle.style.borderRadius="50%";
  sparkle.style.background="rgba(255,255,255,0.8)";
  sparkle.style.left=Math.random()*window.innerWidth+"px";
  sparkle.style.top=Math.random()*window.innerHeight+"px";
  sparkle.style.opacity=Math.random();
  document.getElementById("sparkles").appendChild(sparkle);
  setTimeout(()=>{sparkle.remove()},4000);
}
setInterval(createSparkle,120);

// Optional: music toggle
let musicOn=false;
document.getElementById("muteBtn").addEventListener("click",()=>{
  musicOn=!musicOn;
  document.getElementById("muteBtn").textContent=musicOn?"🔊 Music: On":"🔇 Music: Off";
})
</script>
</body>
</html>
