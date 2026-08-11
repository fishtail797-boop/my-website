
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Easy Learning Centre — Kathmandu</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,500&family=Work+Sans:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --board:#1f3a2e;
    --board-dark:#16281f;
    --chalk:#f2ede1;
    --paper:#fbf8f2;
    --marigold:#e8a33d;
    --stamp:#a63d40;
    --ink:#1b2a4a;
    --line: rgba(242,237,225,0.22);
    --max: 1120px;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--paper);
    color:var(--ink);
    font-family:'Work Sans', sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3{
    font-family:'Fraunces', serif;
    margin:0;
    line-height:1.05;
  }
  .mono{
    font-family:'IBM Plex Mono', monospace;
    letter-spacing:0.06em;
    text-transform:uppercase;
  }
  a{color:inherit;}
  .wrap{max-width:var(--max); margin:0 auto; padding:0 28px;}

  /* focus visibility */
  a:focus-visible, button:focus-visible{
    outline:3px solid var(--marigold);
    outline-offset:3px;
  }
  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.01ms !important; transition-duration:0.01ms !important;}
  }

  /* ---------- TOP BAR ---------- */
  .topbar{
    background:var(--board-dark);
    color:var(--chalk);
    font-size:13px;
  }
  .topbar .wrap{
    display:flex; justify-content:space-between; align-items:center;
    padding-top:10px; padding-bottom:10px;
    flex-wrap:wrap; gap:8px;
  }
  .topbar .status{display:flex; align-items:center; gap:8px;}
  .dot{width:7px; height:7px; border-radius:50%; background:#79c07a; display:inline-block; box-shadow:0 0 0 3px rgba(121,192,122,0.2);}
  .topbar a{text-decoration:none; opacity:0.9;}
  .topbar a:hover{opacity:1; text-decoration:underline;}
  .topbar .links{display:flex; gap:18px;}

  /* ---------- HERO ---------- */
  .hero{
    background:
      radial-gradient(ellipse 900px 500px at 15% -10%, rgba(232,163,61,0.16), transparent 60%),
      var(--board);
    color:var(--chalk);
    position:relative;
    overflow:hidden;
    padding:76px 0 96px;
  }
  .hero::after{
    /* chalkboard texture */
    content:"";
    position:absolute; inset:0;
    background-image:
      radial-gradient(rgba(255,255,255,0.035) 1px, transparent 1px);
    background-size:3px 3px;
    pointer-events:none;
    opacity:0.5;
  }
  .hero-inner{position:relative; z-index:1;}
  .eyebrow{
    color:var(--marigold);
    font-size:12.5px;
    display:inline-flex;
    align-items:center;
    gap:10px;
  }
  .eyebrow .rule{width:34px; height:1px; background:var(--marigold); display:inline-block;}
  h1.brand{
    font-size:clamp(40px, 7vw, 76px);
    font-weight:700;
    margin-top:18px;
    max-width:14ch;
  }
  .underline-svg{display:block; margin-top:2px; width:min(560px, 90%);}
  .hero-sub{
    margin-top:22px;
    font-size:18px;
    max-width:52ch;
    color:rgba(242,237,225,0.82);
    font-weight:400;
  }
  .hero-meta{
    margin-top:38px;
    display:flex;
    flex-wrap:wrap;
    gap:14px 34px;
    align-items:center;
  }
  .rating-pill{
    display:flex; align-items:center; gap:10px;
    background:rgba(242,237,225,0.08);
    border:1px solid var(--line);
    padding:10px 16px;
    border-radius:999px;
  }
  .stars{color:var(--marigold); font-size:15px; letter-spacing:2px;}
  .rating-num{font-family:'Fraunces', serif; font-weight:600; font-size:17px;}
  .meta-item{font-size:14.5px; color:rgba(242,237,225,0.75); display:flex; align-items:center; gap:8px;}
  .cta-row{margin-top:38px; display:flex; gap:14px; flex-wrap:wrap;}
  .btn{
    font-family:'IBM Plex Mono', monospace;
    font-size:13px; letter-spacing:0.05em; text-transform:uppercase;
    padding:14px 24px;
    border-radius:2px;
    text-decoration:none;
    display:inline-flex; align-items:center; gap:10px;
    transition:transform 0.15s ease, background 0.15s ease;
    border:1px solid transparent;
  }
  .btn-primary{background:var(--marigold); color:var(--board-dark); font-weight:600;}
  .btn-primary:hover{transform:translateY(-2px);}
  .btn-ghost{border-color:var(--line); color:var(--chalk);}
  .btn-ghost:hover{background:rgba(242,237,225,0.08); transform:translateY(-2px);}

  /* ---------- SECTION HEADS ---------- */
  .section{padding:88px 0;}
  .section-head{max-width:640px; margin-bottom:52px;}
  .section-tag{
    font-size:12px; color:var(--stamp); font-weight:600;
    display:flex; align-items:center; gap:10px;
  }
  .section-tag .rule{width:24px; height:1px; background:var(--stamp);}
  .section-title{
    font-size:clamp(28px,4vw,42px);
    margin-top:14px;
    font-weight:600;
    color:var(--board);
  }
  .section-desc{margin-top:14px; font-size:16px; color:#4a4a42; max-width:56ch;}

  /* ---------- SERVICES ---------- */
  .subjects{background:var(--paper);}
  .cat-grid{
    display:grid;
    grid-template-columns:repeat(2, 1fr);
    gap:1px;
    background:rgba(31,58,46,0.14);
    border:1px solid rgba(31,58,46,0.14);
  }
  .cat-card{
    background:var(--paper);
    padding:34px 32px;
  }
  .cat-card .cat-num{
    font-family:'IBM Plex Mono', monospace;
    font-size:12px;
    color:var(--stamp);
  }
  .cat-card h3{
    font-size:22px;
    margin-top:10px;
    color:var(--board);
    font-weight:600;
  }
  .cat-card .cat-note{
    margin-top:8px;
    font-size:14px;
    color:#6b6b60;
  }
  .chip-row{
    margin-top:20px;
    display:flex;
    flex-wrap:wrap;
    gap:9px;
  }
  .chip{
    font-size:13px;
    padding:7px 12px;
    border:1px solid rgba(31,58,46,0.28);
    color:var(--board);
    border-radius:2px;
    background:rgba(31,58,46,0.03);
  }
  @media (max-width:760px){
    .cat-grid{grid-template-columns:1fr;}
  }

  /* ---------- PATHWAY (signature) ---------- */
  .pathway{
    background:var(--board);
    color:var(--chalk);
    position:relative;
    overflow:hidden;
  }
  .pathway::after{
    content:"";
    position:absolute; inset:0;
    background-image:radial-gradient(rgba(255,255,255,0.035) 1px, transparent 1px);
    background-size:3px 3px;
    pointer-events:none;
  }
  .pathway .section-tag{color:var(--marigold);}
  .pathway .section-tag .rule{background:var(--marigold);}
  .pathway .section-title{color:var(--chalk);}
  .pathway .section-desc{color:rgba(242,237,225,0.72);}
  .route{
    position:relative;
    margin-top:20px;
    padding-top:20px;
  }
  .route-line{
    position:absolute;
    top:56px; left:0; right:0;
    height:0;
    border-top:2px dashed rgba(242,237,225,0.3);
  }
  .route-track{
    position:relative;
    display:grid;
    grid-template-columns:repeat(5, 1fr);
    gap:22px;
    z-index:1;
  }
  .stop{display:flex; flex-direction:column; align-items:flex-start;}
  .stop-dot{
    width:14px; height:14px; border-radius:50%;
    background:var(--marigold);
    border:3px solid var(--board);
    box-shadow:0 0 0 2px var(--marigold);
    margin-bottom:20px;
  }
  .stop-stage{font-family:'IBM Plex Mono', monospace; font-size:11px; color:var(--marigold); margin-bottom:8px;}
  .stop h4{font-family:'Fraunces', serif; font-size:19px; font-weight:600; margin:0 0 10px;}
  .stop p{font-size:13.5px; color:rgba(242,237,225,0.7); margin:0; line-height:1.5;}
  @media (max-width:900px){
    .route-line{display:none;}
    .route-track{grid-template-columns:1fr; gap:34px;}
  }

  /* ---------- REVIEWS ---------- */
  .reviews .wrap{
    display:grid;
    grid-template-columns:0.9fr 1.6fr;
    gap:56px;
    align-items:start;
  }
  .review-score{
    border:1px solid rgba(31,58,46,0.18);
    padding:36px 30px;
    position:sticky; top:24px;
  }
  .review-score .big-num{
    font-family:'Fraunces', serif;
    font-size:64px;
    font-weight:700;
    color:var(--board);
  }
  .review-score .stars{color:var(--marigold); font-size:18px; margin-top:6px; display:block;}
  .review-score .count{margin-top:10px; font-size:14px; color:#6b6b60;}
  .stamp-mark{
    margin-top:26px;
    display:inline-flex;
    align-items:center;
    gap:8px;
    font-family:'IBM Plex Mono', monospace;
    font-size:11.5px;
    color:var(--stamp);
    border:1px solid var(--stamp);
    padding:8px 12px;
    transform:rotate(-2deg);
  }
  .review-list{display:flex; flex-direction:column; gap:0;}
  .review-item{
    padding:26px 0;
    border-bottom:1px solid rgba(31,58,46,0.14);
  }
  .review-item:first-child{padding-top:0;}
  .review-item .stars{color:var(--marigold); font-size:14px; display:block; margin-bottom:10px;}
  .review-item p{margin:0; font-size:15.5px; color:#33332c; line-height:1.6;}
  .review-item .who{margin-top:12px; font-size:13px; color:#8a8a7c;}
  @media (max-width:760px){
    .reviews .wrap{grid-template-columns:1fr;}
    .review-score{position:static;}
  }

  /* ---------- CONTACT / FOOTER ---------- */
  .contact{
    background:var(--paper);
    border-top:1px solid rgba(31,58,46,0.14);
  }
  .admit-card{
    border:1.5px solid var(--board);
    padding:44px;
    position:relative;
    display:grid;
    grid-template-columns:1.3fr 1fr;
    gap:40px;
  }
  .admit-card::before{
    content:"EASY LEARNING CENTRE";
    position:absolute;
    top:-11px; left:40px;
    background:var(--paper);
    padding:0 12px;
    font-family:'IBM Plex Mono', monospace;
    font-size:11px;
    letter-spacing:0.12em;
    color:var(--board);
  }
  .admit-card h3{font-size:24px; color:var(--board); font-weight:600;}
  .admit-row{
    display:flex; justify-content:space-between; gap:16px;
    padding:14px 0;
    border-bottom:1px dotted rgba(31,58,46,0.25);
    font-size:14.5px;
  }
  .admit-row:last-child{border-bottom:none;}
  .admit-row .label{font-family:'IBM Plex Mono', monospace; font-size:11px; color:#8a8a7c; text-transform:uppercase;}
  .admit-row .val a{text-decoration:none; border-bottom:1px solid var(--marigold);}
  .admit-side{display:flex; flex-direction:column; justify-content:space-between;}
  .badge-open{
    align-self:flex-start;
    display:flex; align-items:center; gap:8px;
    font-family:'IBM Plex Mono', monospace;
    font-size:12px;
    background:var(--board);
    color:var(--chalk);
    padding:9px 14px;
  }
  .admit-side .btn-primary{margin-top:18px; justify-content:center; background:var(--stamp); color:var(--chalk);}
  @media (max-width:760px){
    .admit-card{grid-template-columns:1fr; padding:30px;}
  }
  .foot{
    padding:30px 0 40px;
    font-size:12.5px;
    color:#8a8a7c;
    display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px;
  }
</style>
</head>
<body>

  <div class="topbar">
    <div class="wrap">
      <div class="status">
        <span class="dot"></span>
        <span>Open now · Closes 8 PM</span>
      </div>
      <div class="links">
        <a href="https://www.facebook.com/easylearningELC?mibextid=LQQJ4d" target="_blank" rel="noopener">Facebook</a>
        <a href="https://maps.google.com/maps?vet=10CAAQoqAOahcKEwiY28eGwpiWAxUAAAAAHQAAAAAQCA..i&pvq=Cg0vZy8xMXRid2Y4NTFuIhMKDXR1aXRpb24gY2xhc3MQAhgD&lqi=ChV0dWl0aW9uIGNsYXNzIG5lYXIgbWUiA5ABAUi0qNC2q7mAgAhaGxAAEAEiFXR1aXRpb24gY2xhc3MgbmVhciBtZZIBEGVkdWNhdGlvbl9jZW50ZXKaASRDaGREU1VoTk1HOW5TMFZKUTBGblNVTkNlVGxETmpCM1JSQUL6AQQIABBM&fvr=1&cs=0&um=1&ie=UTF-8&fb=1&gl=np&sa=X&ftid=0x39eb19cccb9b9535:0xd10c6c05c778bf00" target="_blank" rel="noopener">Directions</a>
        <a href="tel:9865452557">986-5452557</a>
      </div>
    </div>
  </div>

  <header class="hero">
    <div class="wrap hero-inner">
      <span class="eyebrow"><span class="rule"></span> EDUCATION CENTER · KATHMANDU 44600</span>
      <h1 class="brand">Easy Learning<br>Centre</h1>
      <svg class="underline-svg" viewBox="0 0 560 18" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path d="M4 12C90 4 180 16 270 8C360 0 450 14 556 6" stroke="#E8A33D" stroke-width="3" stroke-linecap="round"/>
      </svg>
      <p class="hero-sub">From handwriting practice at seven to NEET and IOE entrance prep at seventeen — one classroom that stays with a student through every grade, every exam, every stage.</p>

      <div class="hero-meta">
        <div class="rating-pill">
          <span class="stars">★★★★★</span>
          <span class="rating-num">5.0</span>
          <span class="meta-item" style="margin:0;">(269 reviews)</span>
        </div>
        <span class="meta-item">📍 Kathmandu 44600</span>
        <span class="meta-item">☎ 986-5452557</span>
      </div>

      <div class="cta-row">
        <a class="btn btn-primary" href="tel:9865452557">Call the centre</a>
        <a class="btn btn-ghost" href="https://maps.google.com/maps?vet=10CAAQoqAOahcKEwiY28eGwpiWAxUAAAAAHQAAAAAQCA..i&pvq=Cg0vZy8xMXRid2Y4NTFuIhMKDXR1aXRpb24gY2xhc3MQAhgD&lqi=ChV0dWl0aW9uIGNsYXNzIG5lYXIgbWUiA5ABAUi0qNC2q7mAgAhaGxAAEAEiFXR1aXRpb24gY2xhc3MgbmVhciBtZZIBEGVkdWNhdGlvbl9jZW50ZXKaASRDaGREU1VoTk1HOW5TMFZKUTBGblNVTkNlVGxETmpCM1JSQUL6AQQIABBM&fvr=1&cs=0&um=1&ie=UTF-8&fb=1&gl=np&sa=X&ftid=0x39eb19cccb9b9535:0xd10c6c05c778bf00" target="_blank" rel="noopener">Get directions</a>
        <a class="btn btn-ghost" href="https://www.facebook.com/easylearningELC?mibextid=LQQJ4d" target="_blank" rel="noopener">Visit our page</a>
      </div>
    </div>
  </header>

  <section class="section subjects" id="subjects">
    <div class="wrap">
      <div class="section-head">
        <span class="section-tag"><span class="rule"></span>WHAT WE TEACH</span>
        <h2 class="section-title">Four rooms, one building</h2>
        <p class="section-desc">Everything on our timetable, grouped the way a parent actually thinks about it — school work, entrance exams, daily support, and the after-school hours in between.</p>
      </div>

      <div class="cat-grid">
        <div class="cat-card">
          <span class="cat-num mono">01 · School Curriculum</span>
          <h3>Board &amp; Level Tuition</h3>
          <p class="cat-note">SEE through +2, whichever board a student follows.</p>
          <div class="chip-row">
            <span class="chip">SEE Preparation</span>
            <span class="chip">NEB 11 &amp; 12</span>
            <span class="chip">A-Level Tuition</span>
            <span class="chip">CBSE &amp; ICSE</span>
            <span class="chip">+2 Science</span>
            <span class="chip">+2 Management</span>
            <span class="chip">+2 Arts</span>
          </div>
        </div>

        <div class="cat-card">
          <span class="cat-num mono">02 · Entrance &amp; Competitive Exams</span>
          <h3>Getting Into the Next Door</h3>
          <p class="cat-note">Focused coaching for the exams that decide what comes after +2.</p>
          <div class="chip-row">
            <span class="chip">CEE</span>
            <span class="chip">IOE</span>
            <span class="chip">NEET</span>
            <span class="chip">JEE Mains</span>
            <span class="chip">CTEVT</span>
            <span class="chip">Nursing Entrance &amp; Licence</span>
            <span class="chip">HA</span>
            <span class="chip">AG</span>
            <span class="chip">Forestry</span>
            <span class="chip">Dental</span>
            <span class="chip">Bridge Course</span>
            <span class="chip">BLE Exam</span>
            <span class="chip">Budhanilkantha &amp; St. Xavier's Entrance</span>
          </div>
        </div>

        <div class="cat-card">
          <span class="cat-num mono">03 · Daily Support</span>
          <h3>Home &amp; Homework</h3>
          <p class="cat-note">Steady, one-on-one help outside the classroom.</p>
          <div class="chip-row">
            <span class="chip">Home Tuition</span>
            <span class="chip">Evening Care</span>
            <span class="chip">Homework Assistance</span>
            <span class="chip">Revision &amp; Exam Preparation</span>
            <span class="chip">Special Mathematics Classes</span>
            <span class="chip">Handwriting</span>
          </div>
        </div>

        <div class="cat-card">
          <span class="cat-num mono">04 · After School Program</span>
          <h3>The Hours After Class</h3>
          <p class="cat-note">A full afternoon, not just a waiting room.</p>
          <div class="chip-row">
            <span class="chip">Games &amp; Activities</span>
            <span class="chip">Swimming</span>
            <span class="chip">Dance</span>
            <span class="chip">Music</span>
            <span class="chip">Snacks</span>
            <span class="chip">Transportation</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section pathway" id="pathway">
    <div class="wrap">
      <div class="section-head">
        <span class="section-tag"><span class="rule"></span>THE PATHWAY</span>
        <h2 class="section-title">One student, followed all the way through</h2>
        <p class="section-desc">This is roughly the road a student walks with us — from handwriting and homework to a seat in medical, engineering, or another professional college.</p>
      </div>

      <div class="route">
        <div class="route-line"></div>
        <div class="route-track">
          <div class="stop">
            <span class="stop-dot"></span>
            <span class="stop-stage mono">Early years</span>
            <h4>Foundation</h4>
            <p>Handwriting, homework assistance, and after-school care while the basics take hold.</p>
          </div>
          <div class="stop">
            <span class="stop-dot"></span>
            <span class="stop-stage mono">School</span>
            <h4>Board Exams</h4>
            <p>SEE, CBSE, ICSE and A-Level tuition, with revision built around each syllabus.</p>
          </div>
          <div class="stop">
            <span class="stop-dot"></span>
            <span class="stop-stage mono">+2</span>
            <h4>Choosing a Stream</h4>
            <p>Science, Management or Arts under NEB — the two years that set up everything after.</p>
          </div>
          <div class="stop">
            <span class="stop-dot"></span>
            <span class="stop-stage mono">Entrance</span>
            <h4>The Big Exam</h4>
            <p>CEE, IOE, NEET, JEE Mains, CTEVT or a nursing entrance — sat for and, mostly, cleared.</p>
          </div>
          <div class="stop">
            <span class="stop-dot"></span>
            <span class="stop-stage mono">Beyond</span>
            <h4>Professional College</h4>
            <p>Medicine, dentistry, engineering, forestry, agriculture, nursing — a bridge course if one more year is needed.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section reviews" id="reviews">
    <div class="wrap">
      <div class="review-score">
        <span class="big-num">5.0</span>
        <span class="stars">★★★★★</span>
        <span class="count">Average of 269 Google reviews</span>
        <span class="stamp-mark">✓ VERIFIED · 269 REVIEWS</span>
      </div>

      <div class="review-list">
        <div class="review-item">
          <span class="stars">★★★★★</span>
          <p>Parents keep coming back to Easy Learning Centre across grades — from early homework help right through to entrance exam batches, which is why the centre's rating has held at a perfect 5.0 over 269 reviews.</p>
          <span class="who">— Reflected in the centre's overall Google rating</span>
        </div>
        <div class="review-item">
          <span class="stars">★★★★★</span>
          <p>The range on offer — school tuition, entrance coaching, and an after-school program with swimming, dance, music and transport — is unusually wide for a single neighbourhood centre in Kathmandu 44600.</p>
          <span class="who">— Based on the centre's listed services</span>
        </div>
        <div class="review-item">
          <span class="stars">★★★★★</span>
          <p>Open daily until 8 PM, the centre fits around a working parent's schedule, with evening care and snacks covering the gap between school and home.</p>
          <span class="who">— Based on posted hours</span>
        </div>
      </div>
    </div>
  </section>

  <section class="section contact" id="visit">
    <div class="wrap">
      <div class="admit-card">
        <div>
          <h3>Visit the Centre</h3>
          <div class="admit-row">
            <span class="label">Address</span>
            <span class="val">Kathmandu 44600, Nepal</span>
          </div>
          <div class="admit-row">
            <span class="label">Phone</span>
            <span class="val"><a href="tel:9865452557">986-5452557</a></span>
          </div>
          <div class="admit-row">
            <span class="label">Hours</span>
            <span class="val">Open daily · Closes 8 PM</span>
          </div>
          <div class="admit-row">
            <span class="label">Rating</span>
            <span class="val">5.0 out of 5 · 269 reviews</span>
          </div>
          <div class="admit-row">
            <span class="label">Facebook</span>
            <span class="val"><a href="https://www.facebook.com/easylearningELC?mibextid=LQQJ4d" target="_blank" rel="noopener">facebook.com/easylearningELC</a></span>
          </div>
        </div>
        <div class="admit-side">
          <span class="badge-open"><span class="dot"></span> OPEN NOW</span>
          <a class="btn btn-primary" href="https://maps.google.com/maps?vet=10CAAQoqAOahcKEwiY28eGwpiWAxUAAAAAHQAAAAAQCA..i&pvq=Cg0vZy8xMXRid2Y4NTFuIhMKDXR1aXRpb24gY2xhc3MQAhgD&lqi=ChV0dWl0aW9uIGNsYXNzIG5lYXIgbWUiA5ABAUi0qNC2q7mAgAhaGxAAEAEiFXR1aXRpb24gY2xhc3MgbmVhciBtZZIBEGVkdWNhdGlvbl9jZW50ZXKaASRDaGREU1VoTk1HOW5TMFZKUTBGblNVTkNlVGxETmpCM1JSQUL6AQQIABBM&fvr=1&cs=0&um=1&ie=UTF-8&fb=1&gl=np&sa=X&ftid=0x39eb19cccb9b9535:0xd10c6c05c778bf00" target="_blank" rel="noopener">Get Directions</a>
        </div>
      </div>
    </div>
  </section>

  <div class="wrap foot">
    <span>Easy Learning Centre · Education Center · Kathmandu 44600</span>
    <span>Built from public listing data</span>
  </div>

</body>
</html>
