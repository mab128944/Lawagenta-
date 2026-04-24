cat > /mnt/user-data/outputs/index.html << 'HTMLEOF'
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LawAgenta — Pakistan's Free AI Legal Assistant</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --cream:#FAF8F3;--cream2:#F3EDE0;--cream3:#E8DCC8;
  --gold:#9A7212;--gold2:#B8900F;--gold3:#D4AE40;--gold-light:#FBF3D5;
  --ink:#120F08;--ink2:#1E1A0F;--ink3:#2C2614;
  --muted:#6B5E42;--muted2:#A09070;
  --border:rgba(154,114,18,0.18);--border2:rgba(154,114,18,0.38);
  --green:#15803D;--green2:#DCFCE7;
}
html{scroll-behavior:smooth}
body{font-family:'Outfit',sans-serif;background:var(--cream);color:var(--ink);overflow-x:hidden}
nav{position:fixed;top:0;left:0;right:0;z-index:500;padding:1.2rem 3rem;display:flex;align-items:center;justify-content:space-between;background:rgba(250,248,243,0.97);backdrop-filter:blur(16px);border-bottom:1px solid var(--border)}
.logo{font-family:'Cormorant Garamond',serif;font-size:1.6rem;font-weight:600;color:var(--ink);text-decoration:none;letter-spacing:0.03em}
.logo span{color:var(--gold)}
.nav-ul{display:flex;gap:2rem;list-style:none}
.nav-ul a{color:var(--muted);text-decoration:none;font-size:0.8rem;letter-spacing:0.06em;text-transform:uppercase;transition:color 0.2s}
.nav-ul a:hover{color:var(--gold)}
.nav-free{background:var(--green);color:#fff;border:none;padding:0.55rem 1.4rem;font-family:'Outfit',sans-serif;font-size:0.78rem;font-weight:500;cursor:pointer;transition:all 0.2s;border-radius:3px}
.nav-free:hover{background:#166534}
.hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;padding:6rem 3rem 4rem;position:relative;overflow:hidden;background:linear-gradient(160deg,#FFFEF9 0%,var(--cream) 40%,#F0E8D0 100%)}
.hero-dots{position:absolute;inset:0;background-image:radial-gradient(circle,rgba(154,114,18,0.06) 1px,transparent 1px);background-size:24px 24px;pointer-events:none}
.hero-glow{position:absolute;right:-5%;top:20%;width:500px;height:500px;border-radius:50%;background:radial-gradient(circle,rgba(212,174,64,0.14) 0%,transparent 65%);pointer-events:none}
.free-badge{display:inline-flex;align-items:center;gap:0.6rem;background:var(--green2);border:1px solid rgba(21,128,61,0.25);padding:0.4rem 1rem;border-radius:20px;margin-bottom:2rem;opacity:0;animation:up 0.6s 0.1s forwards}
.free-dot{width:7px;height:7px;background:var(--green);border-radius:50%;animation:blink 2s infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0.3}}
.free-txt{font-size:0.72rem;color:var(--green);font-weight:600;letter-spacing:0.08em;text-transform:uppercase}
.hero h1{font-family:'Cormorant Garamond',serif;font-size:clamp(2.8rem,5.5vw,5.8rem);font-weight:300;line-height:1.05;max-width:750px;margin-bottom:1.8rem;opacity:0;animation:up 0.7s 0.2s forwards}
.hero h1 em{font-style:italic;color:var(--gold)}
.hero h1 strong{font-weight:600}
.hero-sub{font-size:1rem;color:var(--muted);line-height:1.85;max-width:520px;margin-bottom:2.5rem;font-weight:300;opacity:0;animation:up 0.7s 0.35s forwards}
.hero-btns{display:flex;gap:1rem;flex-wrap:wrap;margin-bottom:3rem;opacity:0;animation:up 0.7s 0.5s forwards}
.btn-primary{background:var(--gold);color:#fff;border:none;padding:0.95rem 2.4rem;font-family:'Outfit',sans-serif;font-size:0.86rem;font-weight:500;cursor:pointer;transition:all 0.25s;border-radius:3px;box-shadow:0 4px 18px rgba(154,114,18,0.28)}
.btn-primary:hover{background:var(--gold2);transform:translateY(-2px)}
.btn-ghost{background:transparent;color:var(--ink);border:1.5px solid var(--border2);padding:0.95rem 2rem;font-family:'Outfit',sans-serif;font-size:0.86rem;cursor:pointer;transition:all 0.25s;border-radius:3px}
.btn-ghost:hover{background:var(--gold-light);border-color:var(--gold)}
.trust-row{display:flex;flex-wrap:wrap;gap:0.8rem;opacity:0;animation:up 0.7s 0.65s forwards}
.trust-badge{display:flex;align-items:center;gap:0.5rem;background:#fff;border:1px solid var(--cream3);padding:0.5rem 0.9rem;border-radius:20px;font-size:0.73rem;color:var(--muted)}
@keyframes up{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}
.mq{background:var(--ink2);padding:0.9rem 0;overflow:hidden;border-top:2px solid var(--gold3)}
.mq-track{display:flex;white-space:nowrap;animation:mq 22s linear infinite}
.mq-i{display:inline-flex;align-items:center;gap:1.8rem;padding:0 2rem;font-size:0.68rem;letter-spacing:0.14em;text-transform:uppercase;color:rgba(255,255,255,0.45)}
.mq-d{color:var(--gold3)}
@keyframes mq{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.trust-sec{background:#fff;border-bottom:1px solid var(--cream3);padding:5rem 3rem}
.trust-inner{max-width:1100px;margin:0 auto}
.trust-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.8rem;margin-top:3rem}
.trust-card{background:var(--cream);border:1px solid var(--cream3);padding:2rem;border-radius:6px;transition:all 0.3s;text-align:center}
.trust-card:hover{border-color:var(--border2);box-shadow:0 6px 24px rgba(154,114,18,0.08);transform:translateY(-3px)}
.tc-icon{font-size:2rem;margin-bottom:0.8rem;display:block}
.trust-card h3{font-family:'Cormorant Garamond',serif;font-size:1.25rem;font-weight:400;margin-bottom:0.5rem}
.trust-card p{font-size:0.82rem;color:var(--muted);line-height:1.7;font-weight:300}
.sec{max-width:1100px;margin:0 auto;padding:6rem 3rem}
.tag{display:inline-flex;align-items:center;gap:0.6rem;margin-bottom:1rem}
.tl{width:20px;height:1.5px;background:var(--gold)}
.tt{font-size:0.67rem;letter-spacing:0.16em;text-transform:uppercase;color:var(--gold);font-weight:600}
h2{font-family:'Cormorant Garamond',serif;font-size:clamp(2rem,3.5vw,3.2rem);font-weight:300;line-height:1.12;margin-bottom:1rem}
h2 em{font-style:italic;color:var(--gold)}
.srv-bg{background:var(--cream2);border-top:1px solid var(--cream3);border-bottom:1px solid var(--cream3)}
.srv-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:0;border:1px solid var(--cream3);background:var(--cream3);margin-top:3rem}
.srv{background:#fff;padding:2.2rem 1.8rem;border-right:1px solid var(--cream3);border-bottom:1px solid var(--cream3);transition:background 0.25s;position:relative;overflow:hidden}
.srv:nth-child(3n){border-right:none}
.srv:nth-last-child(-n+3){border-bottom:none}
.srv::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--gold);transform:scaleX(0);transition:transform 0.3s;transform-origin:left}
.srv:hover::after{transform:scaleX(1)}
.srv:hover{background:var(--gold-light)}
.srv-ic{font-size:1.5rem;margin-bottom:0.8rem;display:block}
.srv h3{font-size:0.95rem;font-weight:500;margin-bottom:0.4rem}
.srv p{font-size:0.8rem;color:var(--muted);line-height:1.7;font-weight:300}
.srv-free{display:inline-block;background:var(--green2);color:var(--green);font-size:0.6rem;font-weight:600;padding:0.15rem 0.5rem;border-radius:10px;margin-top:0.7rem;letter-spacing:0.06em;text-transform:uppercase}
.stats-band{background:var(--ink2);border-top:2px solid var(--gold3)}
.stats-row{max-width:1100px;margin:0 auto;padding:0 3rem;display:grid;grid-template-columns:repeat(4,1fr)}
.sbox{padding:2.5rem 1.5rem;text-align:center;border-right:1px solid rgba(255,255,255,0.07)}
.sbox:last-child{border-right:none}
.sn{font-family:'Cormorant Garamond',serif;font-size:2.8rem;font-weight:300;color:var(--gold3);display:block;line-height:1}
.sl{font-size:0.68rem;letter-spacing:0.1em;text-transform:uppercase;color:rgba(255,255,255,0.38);margin-top:0.4rem;display:block}
.chat-section{background:#fff;border-bottom:1px solid var(--cream3)}
.chat-outer{max-width:1100px;margin:0 auto;padding:6rem 3rem;display:grid;grid-template-columns:1fr 1.35fr;gap:5rem;align-items:start}
.chat-box{background:var(--cream);border:1px solid var(--cream3);border-radius:10px;overflow:hidden;box-shadow:0 12px 48px rgba(154,114,18,0.1);position:sticky;top:6rem}
.chat-head{background:linear-gradient(135deg,var(--ink2),var(--ink3));padding:1.1rem 1.4rem;display:flex;align-items:center;gap:0.9rem}
.chat-av{width:38px;height:38px;background:linear-gradient(135deg,var(--gold),var(--gold2));border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:0.7rem;font-weight:700;color:#fff;flex-shrink:0}
.chat-meta h5{font-size:0.86rem;color:#fff;font-weight:500}
.chat-meta p{font-size:0.65rem;color:rgba(255,255,255,0.45)}
.online-pill{background:rgba(74,222,128,0.15);border:1px solid rgba(74,222,128,0.3);color:#4ADE80;font-size:0.6rem;padding:0.18rem 0.6rem;border-radius:20px;display:flex;align-items:center;gap:0.35rem}
.on-dot{width:5px;height:5px;border-radius:50%;background:#4ADE80;animation:blink 2s infinite}
.free-tag-chat{background:rgba(21,128,61,0.25);color:#4ADE80;font-size:0.58rem;font-weight:600;padding:0.15rem 0.5rem;border-radius:8px;letter-spacing:0.06em}
.chat-msgs{padding:1rem;display:flex;flex-direction:column;gap:0.8rem;height:340px;overflow-y:auto;scroll-behavior:smooth}
.chat-msgs::-webkit-scrollbar{width:4px}
.chat-msgs::-webkit-scrollbar-thumb{background:var(--cream3);border-radius:2px}
.msg-u{align-self:flex-end;max-width:82%}
.msg-a{max-width:92%}
.bubble{padding:0.75rem 0.95rem;font-size:0.81rem;line-height:1.65;border-radius:6px}
.msg-u .bubble{background:var(--gold);color:#fff;border-radius:6px 6px 2px 6px}
.msg-a .bubble{background:#fff;border:1px solid var(--cream3);color:var(--ink2);border-radius:6px 6px 6px 2px}
.mlb{font-size:0.59rem;color:var(--muted2);margin-bottom:0.2rem;letter-spacing:0.05em}
.msg-u .mlb{text-align:right}
.hl{color:var(--gold2);font-weight:600}
.typing-bubble{background:#fff;border:1px solid var(--cream3);padding:0.75rem 0.95rem;border-radius:6px;display:flex;gap:4px;align-items:center;width:fit-content}
.td{width:7px;height:7px;background:var(--muted2);border-radius:50%;animation:bounce 1.2s infinite}
.td:nth-child(2){animation-delay:0.18s}.td:nth-child(3){animation-delay:0.36s}
@keyframes bounce{0%,60%,100%{transform:translateY(0)}30%{transform:translateY(-7px)}}
.upload-preview{display:none;align-items:center;gap:0.5rem;background:var(--gold-light);border:1px solid var(--border);padding:0.45rem 0.8rem;border-radius:4px;margin:0 0.8rem}
.up-name{font-size:0.73rem;color:var(--ink2);flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.up-remove{background:none;border:none;color:var(--muted);cursor:pointer;font-size:0.85rem}
.chat-footer{border-top:1px solid var(--cream3);padding:0.75rem}
.chat-input-row{display:flex;gap:0.5rem;align-items:flex-end}
.chat-input{flex:1;border:1px solid var(--cream3);background:#fff;color:var(--ink);font-family:'Outfit',sans-serif;font-size:0.83rem;padding:0.65rem 0.85rem;border-radius:6px;outline:none;resize:none;min-height:38px;max-height:100px;transition:border 0.2s;line-height:1.5}
.chat-input:focus{border-color:var(--gold)}
.btn-send{background:var(--gold);color:#fff;border:none;width:38px;height:38px;border-radius:6px;font-size:0.95rem;cursor:pointer;transition:background 0.2s;flex-shrink:0;display:flex;align-items:center;justify-content:center}
.btn-send:hover{background:var(--gold2)}
.btn-attach{background:var(--cream2);color:var(--muted);border:1px solid var(--cream3);width:38px;height:38px;border-radius:6px;font-size:0.95rem;cursor:pointer;transition:all 0.2s;flex-shrink:0;display:flex;align-items:center;justify-content:center}
.btn-attach:hover{background:var(--gold-light);border-color:var(--border)}
.chat-hint{font-size:0.65rem;color:var(--muted2);margin-top:0.45rem;text-align:center}
.chat-info h3{font-family:'Cormorant Garamond',serif;font-size:2rem;font-weight:300;margin-bottom:1rem}
.chat-info p{font-size:0.88rem;color:var(--muted);line-height:1.8;font-weight:300;margin-bottom:1.8rem}
.cap-list{display:flex;flex-direction:column;gap:0.8rem}
.cap{display:flex;align-items:flex-start;gap:0.8rem;padding:1rem 1.1rem;background:var(--cream);border:1px solid var(--cream3);border-radius:6px;transition:all 0.2s}
.cap:hover{border-color:var(--border);background:var(--gold-light)}
.cap-ic{font-size:1.1rem;flex-shrink:0;margin-top:0.1rem}
.cap h4{font-size:0.86rem;font-weight:500;margin-bottom:0.15rem}
.cap p{font-size:0.78rem;color:var(--muted);line-height:1.5;font-weight:300}
.about-sec{background:var(--cream2);border-bottom:1px solid var(--cream3)}
.about-inner{max-width:1100px;margin:0 auto;padding:6rem 3rem;display:grid;grid-template-columns:1fr 1fr;gap:5rem;align-items:center}
.ap-list{display:flex;flex-direction:column;gap:1rem;margin-top:2rem}
.ap{display:flex;gap:0.9rem;align-items:flex-start;padding:1.1rem;background:#fff;border:1px solid var(--cream3);border-radius:6px}
.ap-ic{width:38px;height:38px;background:var(--gold-light);border:1px solid var(--border);border-radius:4px;display:flex;align-items:center;justify-content:center;font-size:1rem;flex-shrink:0}
.ap h4{font-size:0.88rem;font-weight:500;margin-bottom:0.15rem}
.ap p{font-size:0.78rem;color:var(--muted);line-height:1.6;font-weight:300}
.contact-bg{background:#fff;border-top:1px solid var(--cream3)}
.contact-inner{max-width:1100px;margin:0 auto;padding:6rem 3rem;display:grid;grid-template-columns:1fr 1fr;gap:6rem;align-items:start}
.privacy-box{background:var(--cream2);border:1px solid var(--cream3);border-radius:6px;padding:1.4rem;margin-top:2rem}
.priv-title{font-size:0.68rem;letter-spacing:0.1em;text-transform:uppercase;color:var(--gold);font-weight:600;margin-bottom:0.8rem}
.priv-item{display:flex;align-items:center;gap:0.55rem;padding:0.5rem 0;border-bottom:1px solid var(--cream3);font-size:0.78rem;color:var(--muted)}
.priv-item:last-child{border-bottom:none}
.form-wrap{display:flex;flex-direction:column;gap:0.9rem}
.frow{display:grid;grid-template-columns:1fr 1fr;gap:0.9rem}
.fg{display:flex;flex-direction:column;gap:0.35rem}
.fg label{font-size:0.65rem;letter-spacing:0.1em;text-transform:uppercase;color:var(--muted)}
.fg input,.fg select,.fg textarea{background:var(--cream);border:1px solid var(--cream3);color:var(--ink);font-family:'Outfit',sans-serif;font-size:0.85rem;padding:0.78rem 0.9rem;outline:none;transition:border 0.2s;width:100%;border-radius:4px}
.fg input:focus,.fg select:focus,.fg textarea:focus{border-color:var(--gold);background:#fff}
.fg input::placeholder,.fg textarea::placeholder{color:var(--muted2)}
.fg textarea{resize:vertical;min-height:80px}
.btn-sub{background:var(--gold);color:#fff;border:none;padding:0.95rem;font-family:'Outfit',sans-serif;font-size:0.84rem;font-weight:500;cursor:pointer;transition:all 0.25s;width:100%;border-radius:4px;box-shadow:0 4px 16px rgba(154,114,18,0.25)}
.btn-sub:hover{background:var(--gold2)}
.btn-sub:disabled{opacity:0.6;cursor:not-allowed}
.suc{display:none;background:var(--green2);border:1px solid rgba(21,128,61,0.25);padding:1.3rem;border-radius:6px;text-align:center}
.suc p{font-size:0.86rem;color:var(--green);line-height:1.7}
.fn-note{font-size:0.68rem;color:var(--muted2);text-align:center;line-height:1.6}
.wa-float{position:fixed;bottom:2rem;right:2rem;z-index:400;background:#25D366;width:56px;height:56px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;box-shadow:0 4px 20px rgba(37,211,102,0.4);animation:waf 3s ease-in-out infinite;transition:transform 0.2s}
.wa-float:hover{transform:scale(1.1)!important;animation:none}
.wa-tip{position:absolute;right:64px;background:var(--ink2);color:#fff;font-size:0.72rem;padding:0.38rem 0.8rem;border-radius:4px;white-space:nowrap;opacity:0;transition:opacity 0.2s;pointer-events:none}
.wa-float:hover .wa-tip{opacity:1}
@keyframes waf{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}
footer{background:var(--ink2);padding:2.5rem 3rem;display:flex;align-items:center;justify-content:space-between;gap:2rem;flex-wrap:wrap}
.f-logo{font-family:'Cormorant Garamond',serif;font-size:1.2rem;font-weight:600;color:var(--cream);margin-bottom:0.2rem}
.f-logo span{color:var(--gold3)}
footer p{font-size:0.75rem;color:rgba(255,255,255,0.35)}
.f-links{display:flex;gap:1.8rem;flex-wrap:wrap}
.f-links a{font-size:0.75rem;color:rgba(255,255,255,0.35);text-decoration:none;cursor:pointer;transition:color 0.2s}
.f-links a:hover{color:var(--gold3)}
.rev{opacity:0;transform:translateY(22px);transition:all 0.6s ease}
.rev.v{opacity:1;transform:translateY(0)}
@media(max-width:900px){
  nav{padding:1rem 1.5rem}.nav-ul{display:none}
  .hero{padding:5rem 1.5rem 3rem}
  .trust-sec{padding:3rem 1.5rem}.trust-grid{grid-template-columns:1fr}
  .sec{padding:4rem 1.5rem}
  .srv-grid{grid-template-columns:1fr}
  .srv:nth-child(3n){border-right:1px solid var(--cream3)}
  .chat-outer{grid-template-columns:1fr;gap:2.5rem;padding:4rem 1.5rem}
  .chat-box{position:static}
  .stats-row{grid-template-columns:1fr 1fr;padding:0 1.5rem}
  .sbox{border-bottom:1px solid rgba(255,255,255,0.07)}
  .about-inner,.contact-inner{grid-template-columns:1fr;gap:2.5rem;padding:4rem 1.5rem}
  .frow{grid-template-columns:1fr}
  footer{flex-direction:column;text-align:center;padding:2rem 1.5rem}
}
</style>
</head>
<body>

<div class="wa-float" onclick="openWA()">
  <span class="wa-tip">مفت مشورہ — WhatsApp کریں</span>
  <svg width="25" height="25" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
</div>

<nav>
  <a href="#" class="logo">Law<span>Agenta</span></a>
  <ul class="nav-ul">
    <li><a href="#services">Services</a></li>
    <li><a href="#chat">AI Chat</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <button class="nav-free" onclick="g('contact')">مفت شروع کریں ✦</button>
</nav>

<section class="hero">
  <div class="hero-dots"></div><div class="hero-glow"></div>
  <div class="free-badge"><div class="free-dot"></div><span class="free-txt">100% Free — No Hidden Charges</span></div>
  <h1>Pakistan کا پہلا<br><em>AI قانونی مددگار</em><br><strong>— بالکل مفت</strong></h1>
  <p class="hero-sub">قانونی مشورہ، دستاویز چیک، FIR گائیڈ — سب کچھ AI سے فوری اور مفت۔ کوئی فیس نہیں، کوئی وکیل کا انتظار نہیں۔</p>
  <div class="hero-btns">
    <button class="btn-primary" onclick="g('chat')">✦ مفت AI مشورہ لیں</button>
    <button class="btn-ghost" onclick="g('services')">تمام خدمات دیکھیں</button>
  </div>
  <div class="trust-row">
    <div class="trust-badge"><span>🔒</span> 100% Private</div>
    <div class="trust-badge"><span>🤖</span> AI Powered</div>
    <div class="trust-badge"><span>🇵🇰</span> Pakistan Law</div>
    <div class="trust-badge"><span>⚡</span> Instant Answers</div>
    <div class="trust-badge"><span>🆓</span> Always Free</div>
    <div class="trust-badge"><span>🗣️</span> Urdu + English</div>
  </div>
</section>

<div class="mq"><div class="mq-track">
  <span class="mq-i">مفت قانونی مشورہ <span class="mq-d">◆</span></span><span class="mq-i">Free Legal Advice <span class="mq-d">◆</span></span><span class="mq-i">Contract Review <span class="mq-d">◆</span></span><span class="mq-i">FIR Guidance <span class="mq-d">◆</span></span><span class="mq-i">Property Law <span class="mq-d">◆</span></span><span class="mq-i">Document Analysis <span class="mq-d">◆</span></span><span class="mq-i">Family Law <span class="mq-d">◆</span></span><span class="mq-i">مفت قانونی مشورہ <span class="mq-d">◆</span></span><span class="mq-i">Free Legal Advice <span class="mq-d">◆</span></span><span class="mq-i">Contract Review <span class="mq-d">◆</span></span><span class="mq-i">FIR Guidance <span class="mq-d">◆</span></span><span class="mq-i">Property Law <span class="mq-d">◆</span></span><span class="mq-i">Document Analysis <span class="mq-d">◆</span></span><span class="mq-i">Family Law <span class="mq-d">◆</span></span>
</div></div>

<div class="trust-sec"><div class="trust-inner rev">
  <div class="tag"><div class="tl"></div><span class="tt">ہم پر اعتماد کیوں؟</span></div>
  <h2>آپ کا مسئلہ،<br><em>ہماری ذمہ داری</em></h2>
  <div class="trust-grid">
    <div class="trust-card"><span class="tc-icon">🔒</span><h3>مکمل رازداری</h3><p>آپ کی بات چیت مکمل طور پر private ہے۔ نہ نام، نہ مسئلہ — کہیں شیئر نہیں ہوتا۔</p></div>
    <div class="trust-card"><span class="tc-icon">🤖</span><h3>Advanced AI</h3><p>دنیا کا سب سے ذہین AI — Claude by Anthropic — پاکستانی قانون کا مکمل علم رکھتا ہے۔</p></div>
    <div class="trust-card"><span class="tc-icon">🆓</span><h3>ہمیشہ مفت</h3><p>ہم ایک startup ہیں — ہمارا مقصد قانون ہر پاکستانی کی پہنچ میں لانا ہے۔ کوئی فیس نہیں۔</p></div>
    <div class="trust-card"><span class="tc-icon">⚖️</span><h3>پاکستانی قانون</h3><p>Pakistan Penal Code, Family Laws, Property Laws — تمام اہم قوانین پر مکمل رہنمائی۔</p></div>
    <div class="trust-card"><span class="tc-icon">📱</span><h3>24/7 دستیاب</h3><p>رات 2 بجے بھی مسئلہ آئے — ہمارا AI ہر وقت آپ کی خدمت میں حاضر ہے۔</p></div>
    <div class="trust-card"><span class="tc-icon">📸</span><h3>Document تجزیہ</h3><p>کنٹریکٹ یا نوٹس کی تصویر بھیجیں — AI فوری تجزیہ کر کے بتائے گا۔</p></div>
  </div>
</div></div>

<div class="srv-bg" id="services"><div class="sec">
  <div class="tag"><div class="tl"></div><span class="tt">مفت خدمات</span></div>
  <h2>ہر قانونی مسئلے کا<br><em>مفت حل</em></h2>
  <div class="srv-grid rev">
    <div class="srv"><span class="srv-ic">🤖</span><h3>AI قانونی مشورہ</h3><p>اردو یا انگریزی میں کوئی بھی سوال پوچھیں — فوری جواب پائیں۔</p><span class="srv-free">مفت</span></div>
    <div class="srv"><span class="srv-ic">📄</span><h3>Contract Review</h3><p>کنٹریکٹ upload کریں — AI خطرناک clauses نکالے گا۔</p><span class="srv-free">مفت</span></div>
    <div class="srv"><span class="srv-ic">🚔</span><h3>FIR گائیڈ</h3><p>FIR کیسے کروائیں، کیا حقوق ہیں — مکمل رہنمائی۔</p><span class="srv-free">مفت</span></div>
    <div class="srv"><span class="srv-ic">🏠</span><h3>جائیداد قانون</h3><p>زمین، مکان، کرایہ — تمام property معاملات میں مدد۔</p><span class="srv-free">مفت</span></div>
    <div class="srv"><span class="srv-ic">👨‍👩‍👧</span><h3>فیملی لا</h3><p>طلاق، خلع، حضانت، وراثت — خاندانی قانونی رہنمائی۔</p><span class="srv-free">مفت</span></div>
    <div class="srv"><span class="srv-ic">🏢</span><h3>Business Law</h3><p>کمپنی رجسٹریشن، partnership، employment law۔</p><span class="srv-free">مفت</span></div>
  </div>
</div></div>

<div class="stats-band"><div class="stats-row rev">
  <div class="sbox"><span class="sn">100%</span><span class="sl">Completely Free</span></div>
  <div class="sbox"><span class="sn">24/7</span><span class="sl">Always Available</span></div>
  <div class="sbox"><span class="sn">🔒</span><span class="sl">Fully Private</span></div>
  <div class="sbox"><span class="sn">🤖</span><span class="sl">Claude AI Powered</span></div>
</div></div>

<!-- CHATBOT -->
<div class="chat-section" id="chat"><div class="chat-outer">
  <div class="chat-info rev">
    <div class="tag"><div class="tl"></div><span class="tt">AI Chat — مفت</span></div>
    <h3>اپنا <em style="color:var(--gold)">قانونی مسئلہ</em><br>ابھی پوچھیں</h3>
    <p>ہمارا AI آپ کے سوال کا جواب دیتا ہے، دستاویز analyse کرتا ہے — سب مفت۔</p>
    <div class="cap-list">
      <div class="cap"><span class="cap-ic">💬</span><div><h4>اردو اور انگریزی دونوں</h4><p>جس زبان میں آسان ہو — AI سمجھے گا اور اسی زبان میں جواب دے گا</p></div></div>
      <div class="cap"><span class="cap-ic">📸</span><div><h4>دستاویز یا تصویر upload کریں</h4><p>کنٹریکٹ، نوٹس کی تصویر بھیجیں — AI تجزیہ کرے گا</p></div></div>
      <div class="cap"><span class="cap-ic">⚖️</span><div><h4>پاکستانی قانون کے مطابق</h4><p>Pakistan Penal Code اور local laws کی بنیاد پر guidance</p></div></div>
      <div class="cap"><span class="cap-ic">🆓</span><div><h4>بالکل مفت — ہمیشہ</h4><p>کوئی account نہیں، کوئی payment نہیں</p></div></div>
    </div>
  </div>

  <div class="chat-box rev" style="transition-delay:0.2s">
    <div class="chat-head">
      <div class="chat-av">LA</div>
      <div class="chat-meta"><h5>LawAgenta AI</h5><p>Advanced Legal Intelligence</p></div>
      <div style="margin-left:auto;display:flex;flex-direction:column;align-items:flex-end;gap:0.3rem">
        <div class="online-pill"><div class="on-dot"></div>Online</div>
        <div class="free-tag-chat">FREE</div>
      </div>
    </div>
    <div class="chat-msgs" id="chatMsgs">
      <div class="msg-a"><div class="mlb">LawAgenta AI</div><div class="bubble">السلام علیکم! 👋 میں LawAgenta AI ہوں — آپ کا مفت قانونی مددگار۔<br><br>اردو یا انگریزی میں سوال پوچھیں، یا 📎 سے دستاویز کی تصویر بھیجیں۔<br><br><span class="hl">بتائیں — کیا مسئلہ ہے؟</span></div></div>
    </div>
    <div class="upload-preview" id="uploadPreview">
      <span>📎</span><span class="up-name" id="uploadName"></span>
      <button class="up-remove" onclick="removeUpload()">✕</button>
    </div>
    <input type="file" id="fileInput" accept="image/*,.pdf" onchange="handleFile(this)" style="display:none">
    <div class="chat-footer">
      <div class="chat-input-row">
        <button class="btn-attach" onclick="document.getElementById('fileInput').click()" title="دستاویز">📎</button>
        <textarea class="chat-input" id="chatInput" placeholder="اپنا قانونی سوال یہاں لکھیں..." rows="1" onkeydown="if(event.key==='Enter'&&!event.shiftKey){event.preventDefault();sendMsg()}" oninput="this.style.height='auto';this.style.height=Math.min(this.scrollHeight,110)+'px'"></textarea>
        <button class="btn-send" onclick="sendMsg()">➤</button>
      </div>
      <div class="chat-hint">Enter بھیجیں • Shift+Enter نئی لائن • 📎 دستاویز</div>
    </div>
  </div>
</div></div>

<div class="about-sec" id="about"><div class="about-inner">
  <div class="rev">
    <div class="tag"><div class="tl"></div><span class="tt">ہمارے بارے میں</span></div>
    <h2>ہم کیوں<br><em>مختلف ہیں؟</em></h2>
    <p style="font-size:0.88rem;color:var(--muted);line-height:1.8;font-weight:300">LawAgenta ایک Pakistani startup ہے۔ ہم ابھی شروع ہو رہے ہیں — آپ کا اعتماد ہماری سب سے بڑی طاقت ہے۔</p>
    <div class="ap-list">
      <div class="ap"><div class="ap-ic">🎯</div><div><h4>ہمارا مقصد</h4><p>پاکستان میں قانونی مدد کو عام آدمی تک پہنچانا — مفت اور آسان</p></div></div>
      <div class="ap"><div class="ap-ic">🤝</div><div><h4>آپ کا اعتماد</h4><p>ہم نئے ہیں — آپ کا ہر feedback ہمارے لیے قیمتی ہے</p></div></div>
      <div class="ap"><div class="ap-ic">🚀</div><div><h4>ہمارا سفر</h4><p>ابھی شروع ہوا — آپ کے ساتھ مل کر بہتر بنتے جائیں گے</p></div></div>
      <div class="ap"><div class="ap-ic">📞</div><div><h4>براہ راست رابطہ</h4><p>کوئی بھی سوال ہو — WhatsApp یا form سے بات کریں</p></div></div>
    </div>
  </div>
  <div class="rev" style="transition-delay:0.15s">
    <div style="background:linear-gradient(145deg,var(--gold-light),var(--cream));border:1px solid var(--border);border-radius:10px;padding:3rem;text-align:center">
      <div style="font-size:4rem;margin-bottom:1rem">⚖️</div>
      <p style="font-family:'Cormorant Garamond',serif;font-size:1.7rem;font-weight:300;color:var(--ink);line-height:1.3;margin-bottom:1rem">"قانون سب کے لیے ہے — صرف امیروں کے لیے نہیں"</p>
      <p style="font-size:0.8rem;color:var(--muted)">— LawAgenta Mission</p>
      <div style="margin-top:2rem;padding-top:2rem;border-top:1px solid var(--cream3)">
        <p style="font-size:1.8rem">🇵🇰</p>
        <p style="font-size:0.76rem;color:var(--muted);margin-top:0.4rem">Made in Pakistan — For Pakistan</p>
      </div>
    </div>
  </div>
</div></div>

<div class="contact-bg" id="contact"><div class="contact-inner">
  <div class="rev">
    <div class="tag"><div class="tl"></div><span class="tt">رابطہ کریں</span></div>
    <h2>ہم سے<br><em>بات کریں</em></h2>
    <p style="font-size:0.88rem;color:var(--muted);line-height:1.8;font-weight:300">سوال ہو، مسئلہ ہو، یا feedback — ہم ہر وقت سننے کے لیے تیار ہیں۔</p>
    <div class="privacy-box">
      <div class="priv-title">🔒 آپ کی Privacy ہماری ذمہ داری</div>
      <div class="priv-item">✅ آپ کا نمبر یا email کہیں display نہیں ہوتا</div>
      <div class="priv-item">✅ صرف secure Google Sheet میں محفوظ</div>
      <div class="priv-item">✅ کوئی bot آپ کی info نہیں چرا سکتا</div>
      <div class="priv-item">✅ صرف ہم رابطہ کریں گے — کوئی spam نہیں</div>
    </div>
  </div>
  <div class="rev" style="transition-delay:0.15s">
    <div class="tag"><div class="tl"></div><span class="tt">مفت Early Access</span></div>
    <p style="font-size:0.8rem;color:var(--muted);margin-bottom:1.3rem;font-weight:300;line-height:1.7">Form بھریں — 24 گھنٹے میں رابطہ کریں گے۔</p>
    <div id="suc" class="suc"><p>✦ شکریہ! 24 گھنٹوں میں رابطہ کریں گے۔ 🎉</p></div>
    <form class="form-wrap" id="mainForm" onsubmit="handleSubmit(event)">
      <div class="frow">
        <div class="fg"><label>نام *</label><input type="text" name="name" placeholder="آپ کا نام" required></div>
        <div class="fg"><label>WhatsApp *</label><input type="tel" name="phone" placeholder="03XX-XXXXXXX" required></div>
      </div>
      <div class="fg"><label>Email *</label><input type="email" name="email" placeholder="your@email.com" required></div>
      <div class="fg"><label>مسئلہ کی نوعیت</label>
        <select name="service">
          <option value="property">جائیداد / Property</option>
          <option value="family">فیملی لا / Family Law</option>
          <option value="contract">کنٹریکٹ / Contract</option>
          <option value="fir">FIR / Police Matter</option>
          <option value="business">بزنس / Business Law</option>
          <option value="other">دیگر / Other</option>
        </select>
      </div>
      <div class="fg"><label>مسئلہ (اختیاری)</label><textarea name="message" placeholder="مختصراً بتائیں..."></textarea></div>
      <button type="submit" class="btn-sub" id="subBtn">مفت رابطہ کریں ✦</button>
      <p class="fn-note">🔒 آپ کی معلومات محفوظ — کبھی شیئر نہیں ہوں گی</p>
    </form>
  </div>
</div></div>

<footer>
  <div><div class="f-logo">Law<span>Agenta</span></div><p>© 2025 LawAgenta. Pakistan's Free AI Legal Platform.</p></div>
  <p style="text-align:center;max-width:240px;line-height:1.7">قانون سب کے لیے — مفت، آسان، قابل اعتماد</p>
  <div class="f-links">
    <a onclick="g('services')">Services</a>
    <a onclick="g('chat')">AI Chat</a>
    <a onclick="g('about')">About</a>
    <a onclick="g('contact')">Contact</a>
    <a onclick="openWA()">WhatsApp</a>
  </div>
</footer>

<script>
const _p=['92','30','20','78','64','76'].join('');
function openWA(){window.open('https://wa.me/'+_p+'?text=السلام علیکم! LawAgenta سے قانونی مشورہ چاہیے۔','_blank')}
function g(id){const el=document.getElementById(id);if(el)el.scrollIntoView({behavior:'smooth'})}
const obs=new IntersectionObserver(e=>e.forEach(x=>{if(x.isIntersecting)x.target.classList.add('v')}),{threshold:0.07});
document.querySelectorAll('.rev').forEach(el=>obs.observe(el));

let uploadedFile=null,uploadedBase64=null;
function handleFile(input){
  const f=input.files[0];if(!f)return;
  uploadedFile=f;
  document.getElementById('uploadName').textContent=f.name;
  document.getElementById('uploadPreview').style.display='flex';
  const r=new FileReader();
  r.onload=e=>{uploadedBase64=e.target.result.split(',')[1]};
  r.readAsDataURL(f);
}
function removeUpload(){
  uploadedFile=null;uploadedBase64=null;
  document.getElementById('fileInput').value='';
  document.getElementById('uploadPreview').style.display='none';
}

const msgs=document.getElementById('chatMsgs');
let chatHistory=[];

function addMsg(text,isUser){
  const d=document.createElement('div');
  d.className=isUser?'msg-u':'msg-a';
  d.innerHTML=`<div class="mlb">${isUser?'آپ':'LawAgenta AI'}</div><div class="bubble">${text}</div>`;
  msgs.appendChild(d);msgs.scrollTop=msgs.scrollHeight;
}
function showTyping(){
  const d=document.createElement('div');d.className='msg-a';d.id='typDiv';
  d.innerHTML='<div class="mlb">LawAgenta AI</div><div class="typing-bubble"><div class="td"></div><div class="td"></div><div class="td"></div></div>';
  msgs.appendChild(d);msgs.scrollTop=msgs.scrollHeight;
}
function rmTyping(){const t=document.getElementById('typDiv');if(t)t.remove()}

async function sendMsg(){
  const inp=document.getElementById('chatInput');
  const txt=inp.value.trim();
  if(!txt&&!uploadedFile)return;
  const display=uploadedFile?(txt||'📎 '+uploadedFile.name):txt;
  addMsg(display,true);inp.value='';inp.style.height='auto';
  let content=[];
  if(uploadedBase64&&uploadedFile&&uploadedFile.type.startsWith('image/')){
    content.push({type:'image',source:{type:'base64',media_type:uploadedFile.type,data:uploadedBase64}});
    removeUpload();
  } else if(uploadedFile){removeUpload();}
  content.push({type:'text',text:txt||'براہ کرم اس دستاویز کا تجزیہ کریں۔'});
  chatHistory.push({role:'user',content:content});
  showTyping();
  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body:JSON.stringify({
        model:'claude-sonnet-4-20250514',
        max_tokens:1000,
        system:`آپ LawAgenta AI ہیں — Pakistan کا مفت AI قانونی مددگار۔ آپ Pakistan کے قوانین (PPC, Family Laws, Property Laws, Contract Act) کی بنیاد پر جواب دیں۔ اردو اور انگریزی دونوں میں جواب دیں۔ جواب واضح، عملی اور آسان زبان میں ہو۔ اگر تصویر یا دستاویز ہو تو اس کا تجزیہ کریں۔ سنگین معاملات میں وکیل سے ملنے کی تجویز دیں۔ **bold** اور bullet points استعمال کریں۔`,
        messages:chatHistory
      })
    });
    const data=await res.json();
    rmTyping();
    if(data.content&&data.content[0]){
      const reply=data.content[0].text;
      chatHistory.push({role:'assistant',content:reply});
      const fmt=reply.replace(/\*\*(.*?)\*\*/g,'<b>$1</b>').replace(/\n/g,'<br>');
      addMsg(fmt,false);
    } else {fallback();}
  }catch{rmTyping();fallback();}
}
function fallback(){addMsg('معذرت — connection مسئلہ ہے۔ براہ کرم <b>WhatsApp</b> پر رابطہ کریں یا دوبارہ کوشش کریں۔',false);}

// ═══════════════════════════════════════
// GOOGLE SHEETS — اپنا URL یہاں ڈالیں:
const SHEET_URL='(https://script.google.com/macros/s/AKfycbzhc_V0hxSUQMj-4-kCDlmDIWYnI4iLG73VXA5NdcEvijIT8gXB4CbRp8al-8Gmn66dLA/exec)';
// ═══════════════════════════════════════

async function handleSubmit(e){
  e.preventDefault();
  const btn=document.getElementById('subBtn');
  const fd=new FormData(e.target);
  const data={name:fd.get('name'),phone:fd.get('phone'),email:fd.get('email'),service:fd.get('service'),message:fd.get('message')||''};
  btn.textContent='بھیجا جا رہا ہے...';btn.disabled=true;
  try{
    if(SHEET_URL==='(https://script.google.com/macros/s/AKfycbzhc_V0hxSUQMj-4-kCDlmDIWYnI4iLG73VXA5NdcEvijIT8gXB4CbRp8al-8Gmn66dLA/exec)'){await new Promise(r=>setTimeout(r,900));}
    else{await fetch(SHEET_URL,{method:'POST',mode:'no-cors',body:JSON.stringify(data)});}
    document.getElementById('mainForm').style.display='none';
    document.getElementById('suc').style.display='block';
  }catch{
    alert('مسئلہ آیا — WhatsApp پر رابطہ کریں');
    openWA();btn.textContent='مفت رابطہ کریں ✦';btn.disabled=false;
  }
}
</script>
</body>
</html>
HTMLEOF
echo "done"
