# -zn-das-ofertas
🛍️ Bem-vindo à **ZN das Ofertas**! Aqui você encontra produtos de qualidade, preços baixos e promoções imperdíveis. Trabalhamos com variedade, atendimento de confiança e envio rápido para todo o Brasil. Aproveite nossas ofertas e economize em cada compra!
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ZN das Ofertas — garimpo diário de promoções</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Inter:wght@400;500;600;700;800&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#12131a;
    --card:#1b1d29;
    --card-hi:#232637;
    --line: rgba(242,240,235,0.09);
    --text:#f2f0eb;
    --muted:#9498a8;
    --gold:#ffc145;
    --magenta:#ff4d6d;
    --teal:#3fd6c4;
    --radius: 14px;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:
      radial-gradient(1100px 600px at 85% -10%, rgba(255,193,69,0.10), transparent 60%),
      radial-gradient(900px 500px at -10% 20%, rgba(255,77,109,0.08), transparent 55%),
      var(--ink);
    color:var(--text);
    font-family:'Inter', sans-serif;
    line-height:1.5;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit; text-decoration:none;}
  .display{font-family:'Archivo Black', sans-serif;}
  .mono{font-family:'Space Mono', monospace;}
  .wrap{max-width:1180px; margin:0 auto; padding:0 24px;}

  /* focus visibility */
  a:focus-visible, button:focus-visible, input:focus-visible{
    outline:2px solid var(--gold); outline-offset:3px;
  }
  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important;}
  }

  /* ---------- HEADER ---------- */
  header{
    position:sticky; top:0; z-index:50;
    background:rgba(18,19,26,0.85);
    backdrop-filter: blur(10px);
    border-bottom:1px solid var(--line);
  }
  .header-inner{display:flex; align-items:center; justify-content:space-between; padding:16px 24px; gap:20px;}
  .logo{display:flex; align-items:baseline; gap:2px; font-size:1.5rem; letter-spacing:-0.5px;}
  .logo .zn{color:var(--gold);}
  .logo .rest{font-size:0.95rem; font-weight:600; color:var(--muted); font-family:'Inter'; letter-spacing:0.5px; text-transform:uppercase; margin-left:8px;}
  nav{display:flex; gap:28px;}
  nav a{font-size:0.92rem; font-weight:600; color:var(--muted); transition:color .15s;}
  nav a:hover{color:var(--text);}
  .btn-anunciar{
    background:var(--gold); color:#1a1305; font-weight:800; font-size:0.85rem;
    padding:10px 18px; border-radius:100px; border:none; cursor:pointer;
    transition:transform .15s ease, box-shadow .15s ease;
  }
  .btn-anunciar:hover{transform:translateY(-1px); box-shadow:0 8px 20px rgba(255,193,69,0.25);}
  .nav-toggle{display:none;}

  /* ---------- TICKER ---------- */
  .ticker-bar{
    background:var(--magenta); overflow:hidden; white-space:nowrap;
    border-bottom:1px solid rgba(0,0,0,0.15);
  }
  .ticker-track{
    display:inline-flex; gap:48px; padding:9px 0;
    animation: scroll-left 32s linear infinite;
  }
  .ticker-bar:hover .ticker-track{ animation-play-state: paused; }
  .ticker-track span{font-family:'Space Mono', monospace; font-size:0.82rem; font-weight:700; color:#fff0f2;}
  @keyframes scroll-left{
    from{transform:translateX(0);}
    to{transform:translateX(-50%);}
  }

  /* ---------- HERO ---------- */
  .hero{padding:64px 0 48px;}
  .hero-grid{display:grid; grid-template-columns:1.1fr 0.9fr; gap:48px; align-items:center;}
  .eyebrow{
    display:inline-flex; align-items:center; gap:8px;
    font-family:'Space Mono'; font-size:0.75rem; color:var(--teal);
    background:rgba(63,214,196,0.1); border:1px solid rgba(63,214,196,0.3);
    padding:6px 12px; border-radius:100px; margin-bottom:20px;
  }
  .eyebrow .dot{width:6px; height:6px; border-radius:50%; background:var(--teal); animation:pulse 1.6s ease-in-out infinite;}
  @keyframes pulse{0%,100%{opacity:1;} 50%{opacity:0.3;}}
  h1{
    font-size:clamp(2.4rem, 5vw, 3.6rem); line-height:1.02; letter-spacing:-1px;
    margin-bottom:20px;
  }
  h1 .accent{color:var(--gold);}
  .hero p.lede{color:var(--muted); font-size:1.08rem; max-width:480px; margin-bottom:32px;}
  .search-box{
    display:flex; gap:8px; background:var(--card); border:1px solid var(--line);
    border-radius:100px; padding:6px 6px 6px 20px; max-width:480px;
  }
  .search-box input{
    flex:1; background:transparent; border:none; color:var(--text); font-size:0.95rem;
  }
  .search-box input::placeholder{color:var(--muted);}
  .search-box button{
    background:var(--text); color:var(--ink); border:none; font-weight:700;
    padding:11px 22px; border-radius:100px; cursor:pointer; font-size:0.88rem;
  }
  .hero-stats{display:flex; gap:28px; margin-top:28px;}
  .stat b{display:block; font-family:'Space Mono'; font-size:1.4rem; color:var(--gold);}
  .stat span{font-size:0.78rem; color:var(--muted);}

  /* Featured deal card in hero */
  .feature-card{
    background:linear-gradient(160deg, var(--card-hi), var(--card));
    border:1px solid var(--line); border-radius:20px; padding:26px;
    position:relative; overflow:hidden;
  }
  .feature-card::before{
    content:"MAIS QUENTE AGORA"; position:absolute; top:18px; right:-38px;
    background:var(--magenta); color:#fff; font-family:'Space Mono'; font-size:0.65rem;
    font-weight:700; padding:5px 44px; transform:rotate(35deg); letter-spacing:1px;
  }
  .feature-thumb{
    height:150px; border-radius:12px; margin-bottom:18px;
    background:
      repeating-linear-gradient(135deg, rgba(255,193,69,0.14) 0 12px, rgba(255,193,69,0.05) 12px 24px),
      linear-gradient(135deg, #2a2d40, #1b1d29);
    display:flex; align-items:center; justify-content:center; font-size:2.6rem;
  }
  .feature-store{font-size:0.75rem; color:var(--muted); font-weight:600; text-transform:uppercase; letter-spacing:0.5px;}
  .feature-title{font-size:1.15rem; font-weight:700; margin:6px 0 14px;}
  .price-row{display:flex; align-items:baseline; gap:10px; margin-bottom:16px;}
  .price-old{font-family:'Space Mono'; color:var(--muted); text-decoration:line-through; font-size:0.9rem;}
  .price-new{font-family:'Space Mono'; color:var(--gold); font-size:1.7rem; font-weight:700;}
  .badge-off{
    font-family:'Space Mono'; font-size:0.78rem; font-weight:700; color:#1a1305;
    background:var(--gold); padding:4px 10px; border-radius:6px;
  }
  .feature-cta{
    display:block; text-align:center; background:var(--gold); color:#1a1305;
    font-weight:800; padding:13px; border-radius:10px; font-size:0.9rem;
  }

  /* ---------- CATEGORIES ---------- */
  .categories{padding:8px 0 44px;}
  .cat-row{display:flex; gap:10px; flex-wrap:wrap;}
  .cat-chip{
    background:var(--card); border:1px solid var(--line); color:var(--muted);
    padding:10px 18px; border-radius:100px; font-size:0.85rem; font-weight:600;
    cursor:pointer; transition:all .15s; display:flex; align-items:center; gap:8px;
  }
  .cat-chip:hover{border-color:var(--gold); color:var(--text);}
  .cat-chip.active{background:var(--gold); color:#1a1305; border-color:var(--gold);}

  /* ---------- DEALS GRID ---------- */
  .section-head{display:flex; align-items:baseline; justify-content:space-between; margin-bottom:24px;}
  .section-head h2{font-size:1.6rem; letter-spacing:-0.5px;}
  .section-head p{color:var(--muted); font-size:0.88rem;}
  .deals-grid{
    display:grid; grid-template-columns:repeat(3, 1fr); gap:20px; padding-bottom:70px;
  }
  .deal-card{
    background:var(--card); border:1px solid var(--line); border-radius:var(--radius);
    padding:18px; display:flex; flex-direction:column; transition:transform .18s, border-color .18s;
  }
  .deal-card:hover{transform:translateY(-4px); border-color:rgba(255,193,69,0.35);}
  .deal-thumb{
    height:120px; border-radius:10px; margin-bottom:14px; position:relative;
    background:linear-gradient(150deg, #262a3c, #1b1d29);
    display:flex; align-items:center; justify-content:center; font-size:2.3rem;
  }
  /* signature: ticket-stub discount badge with torn/perforated edge */
  .ticket{
    position:absolute; top:8px; left:8px; display:flex; align-items:stretch;
    filter:drop-shadow(0 3px 6px rgba(0,0,0,0.35));
  }
  .ticket-body{
    background:var(--magenta); color:#fff; font-family:'Space Mono'; font-weight:700;
    font-size:0.78rem; padding:5px 10px 5px 8px; border-radius:6px 0 0 6px;
    display:flex; align-items:center;
  }
  .ticket-notch{
    width:10px; background:
      radial-gradient(circle 4px at 0 0, transparent 4px, var(--magenta) 4.5px) top left,
      radial-gradient(circle 4px at 0 100%, transparent 4px, var(--magenta) 4.5px) bottom left;
    background-repeat:no-repeat;
  }
  .deal-store{font-size:0.72rem; color:var(--muted); font-weight:600; text-transform:uppercase; letter-spacing:0.4px;}
  .deal-title{font-size:0.95rem; font-weight:700; margin:5px 0 12px; min-height:2.6em;}
  .deal-price-row{display:flex; align-items:baseline; gap:8px; margin-bottom:10px;}
  .deal-old{font-family:'Space Mono'; font-size:0.78rem; color:var(--muted); text-decoration:line-through;}
  .deal-new{font-family:'Space Mono'; font-size:1.25rem; font-weight:700; color:var(--gold);}
  .deal-meta{display:flex; align-items:center; justify-content:space-between; margin-top:auto; padding-top:10px; border-top:1px dashed var(--line);}
  .deal-quente{display:flex; align-items:center; gap:5px; font-size:0.78rem; color:var(--teal); font-weight:600;}
  .deal-timer{font-family:'Space Mono'; font-size:0.72rem; color:var(--muted);}
  .deal-card.hidden{display:none;}

  /* ---------- NEWSLETTER ---------- */
  .cta-band{
    background:var(--card-hi); border-top:1px solid var(--line); border-bottom:1px solid var(--line);
    padding:56px 0;
  }
  .cta-inner{display:flex; align-items:center; justify-content:space-between; gap:32px; flex-wrap:wrap;}
  .cta-inner h3{font-size:1.7rem; max-width:420px; letter-spacing:-0.5px;}
  .cta-inner p{color:var(--muted); margin-top:8px; max-width:420px; font-size:0.92rem;}
  .cta-form{display:flex; gap:10px;}
  .cta-form input{
    background:var(--ink); border:1px solid var(--line); border-radius:10px; padding:13px 16px;
    color:var(--text); font-size:0.9rem; width:230px;
  }
  .cta-form button{
    background:var(--teal); border:none; color:#062a25; font-weight:800; padding:13px 20px;
    border-radius:10px; cursor:pointer; font-size:0.88rem; white-space:nowrap;
  }

  /* ---------- FOOTER ---------- */
  footer{padding:40px 0 30px;}
  .footer-inner{display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:16px;}
  footer .logo{font-size:1.1rem;}
  .footer-links{display:flex; gap:22px;}
  .footer-links a{color:var(--muted); font-size:0.82rem;}
  .footer-links a:hover{color:var(--text);}
  .footer-fine{color:var(--muted); font-size:0.75rem; margin-top:18px; opacity:0.7;}

  @media (max-width: 860px){
    .header-inner nav{display:none;}
    .hero-grid{grid-template-columns:1fr;}
    .deals-grid{grid-template-columns:repeat(2, 1fr);}
    .cta-inner{flex-direction:column; align-items:flex-start;}
  }
  @media (max-width: 540px){
    .deals-grid{grid-template-columns:1fr;}
    .hero-stats{flex-wrap:wrap;}
    .cta-form{flex-direction:column; width:100%;}
    .cta-form input{width:100%;}
  }
</style>
</head>
<body>

<header>
  <div class="header-inner">
    <div class="logo display"><span class="zn">ZN</span> das Ofertas<span class="rest">garimpo diário</span></div>
    <nav>
      <a href="#ofertas">Ofertas</a>
      <a href="#categorias">Categorias</a>
      <a href="#cupons">Cupons</a>
      <a href="#alertas">Alertas</a>
    </nav>
    <button class="btn-anunciar">Postar oferta</button>
  </div>
  <div class="ticker-bar">
    <div class="ticker-track" id="tickerTrack"></div>
  </div>
</header>

<section class="hero">
  <div class="wrap hero-grid">
    <div>
      <div class="eyebrow"><span class="dot"></span> 1.284 ofertas ativas agora</div>
      <h1 class="display">Achamos o<br>preço <span class="accent">baixo</span>.<br>Você garante.</h1>
      <p class="lede">A comunidade garimpa, confere e avisa. Preço bom não dura — entre antes que esgote.</p>
      <div class="search-box">
        <input type="text" id="searchInput" placeholder="Buscar produto, loja ou categoria…">
        <button id="searchBtn">Garimpar</button>
      </div>
      <div class="hero-stats">
        <div class="stat"><b>247</b><span>ofertas hoje</span></div>
        <div class="stat"><b>R$ 38k</b><span>economizados essa semana</span></div>
        <div class="stat"><b>32k</b><span>garimpeiros ativos</span></div>
      </div>
    </div>

    <div class="feature-card">
      <div class="feature-thumb">🎧</div>
      <div class="feature-store">Kabum · há 12 min</div>
      <div class="feature-title">Fone Bluetooth JBL Tune 510BT</div>
      <div class="price-row">
        <span class="price-old mono">R$ 249,90</span>
        <span class="price-new mono">R$ 129,90</span>
        <span class="badge-off">-48%</span>
      </div>
      <a href="#" class="feature-cta">Ver oferta →</a>
    </div>
  </div>
</section>

<section class="categories wrap" id="categorias">
  <div class="cat-row" id="catRow">
    <button class="cat-chip active" data-cat="todas">🔥 Todas</button>
    <button class="cat-chip" data-cat="eletronicos">📱 Eletrônicos</button>
    <button class="cat-chip" data-cat="casa">🏠 Casa</button>
    <button class="cat-chip" data-cat="moda">👕 Moda</button>
    <button class="cat-chip" data-cat="games">🎮 Games</button>
    <button class="cat-chip" data-cat="beleza">💄 Beleza</button>
    <button class="cat-chip" data-cat="mercado">🛒 Mercado</button>
  </div>
</section>

<section class="wrap" id="ofertas">
  <div class="section-head">
    <h2 class="display">Quentes agora</h2>
    <p>Atualizado a cada poucos minutos pela comunidade</p>
  </div>
  <div class="deals-grid" id="dealsGrid"></div>
</section>

<section class="cta-band" id="alertas">
  <div class="wrap cta-inner">
    <div>
      <h3 class="display">Receba ofertas no WhatsApp</h3>
      <p>Escolha suas categorias favoritas e a gente te avisa assim que o preço despencar.</p>
    </div>
    <form class="cta-form" onsubmit="event.preventDefault(); this.querySelector('button').textContent='Inscrito ✓';">
      <input type="tel" placeholder="(85) 99999-0000" required>
      <button type="submit">Quero receber</button>
    </form>
  </div>
</section>

<footer class="wrap">
  <div class="footer-inner">
    <div class="logo display"><span class="zn">ZN</span> das Ofertas</div>
    <div class="footer-links">
      <a href="#cupons" id="cupons">Cupons</a>
      <a href="#">Sobre</a>
      <a href="#">Anuncie</a>
      <a href="#">Contato</a>
    </div>
  </div>
  <p class="footer-fine">ZN das Ofertas reúne promoções enviadas pela comunidade. Preços e disponibilidade podem mudar sem aviso — confira sempre na loja antes de comprar.</p>
</footer>

<script>
  // ---- Ticker content ----
  const tickerItems = [
    "🔥 Air Fryer Mondial 4L — R$ 189,90 (-45%)",
    "⚡ SSD Kingston 480GB — R$ 139,90 (-38%)",
    "🎮 Controle Xbox Series — R$ 279,00 (-30%)",
    "👟 Tênis Olympikus — R$ 119,90 (-50%)",
    "📺 Smart TV 50\" 4K — R$ 1.899,00 (-27%)",
    "☕ Cafeteira Elétrica — R$ 89,90 (-40%)"
  ];
  const track = document.getElementById('tickerTrack');
  const doubled = [...tickerItems, ...tickerItems];
  track.innerHTML = doubled.map(t => `<span>${t}</span>`).join('<span style="opacity:.4">&nbsp;&nbsp;•&nbsp;&nbsp;</span>');

  // ---- Deals data ----
  const deals = [
    {cat:'eletronicos', emoji:'💻', store:'Amazon', title:'Notebook Lenovo Ideapad 8GB/256GB SSD', old:2799.00, price:1899.00, off:32, time:'8 min', quente:98},
    {cat:'casa', emoji:'🍳', store:'Magazine Luiza', title:'Air Fryer Mondial 4L Digital', old:349.90, price:189.90, off:46, time:'22 min', quente:87},
    {cat:'moda', emoji:'👟', store:'Netshoes', title:'Tênis Olympikus Corre 3 Unissex', old:239.90, price:119.90, off:50, time:'5 min', quente:76},
    {cat:'games', emoji:'🎮', store:'Kabum', title:'Controle Xbox Series Wireless', old:399.00, price:279.00, off:30, time:'41 min', quente:64},
    {cat:'beleza', emoji:'💧', store:'Sephora', title:'Kit Skincare Vitamina C 3 itens', old:189.90, price:99.90, off:47, time:'1 h', quente:52},
    {cat:'eletronicos', emoji:'🎧', store:'Kabum', title:'Fone Bluetooth JBL Tune 510BT', old:249.90, price:129.90, off:48, time:'12 min', quente:99},
    {cat:'mercado', emoji:'☕', store:'Amazon', title:'Cafeteira Elétrica Mondial 30 Xícaras', old:149.90, price:89.90, off:40, time:'33 min', quente:45},
    {cat:'casa', emoji:'🛋️', store:'Mobly', title:'Sofá Retrátil 3 Lugares Suede', old:1899.00, price:1299.00, off:32, time:'2 h', quente:38},
    {cat:'eletronicos', emoji:'📺', store:'Fast Shop', title:'Smart TV 50" 4K UHD LED', old:2599.00, price:1899.00, off:27, time:'19 min', quente:71},
  ];

  const grid = document.getElementById('dealsGrid');
  const brl = n => n.toLocaleString('pt-BR', {minimumFractionDigits:2, maximumFractionDigits:2});

  function render(list){
    grid.innerHTML = list.map(d => `
      <div class="deal-card" data-cat="${d.cat}">
        <div class="deal-thumb">
          <div class="ticket">
            <div class="ticket-body">-${d.off}%</div>
            <div class="ticket-notch"></div>
          </div>
          <span>${d.emoji}</span>
        </div>
        <div class="deal-store">${d.store} · há ${d.time}</div>
        <div class="deal-title">${d.title}</div>
        <div class="deal-price-row">
          <span class="deal-old mono">R$ ${brl(d.old)}</span>
          <span class="deal-new mono">R$ ${brl(d.price)}</span>
        </div>
        <div class="deal-meta">
          <span class="deal-quente">🔥 ${d.quente}° quente</span>
          <span class="deal-timer mono">expira em breve</span>
        </div>
      </div>
    `).join('');
  }
  render(deals);

  // ---- Category filter ----
  document.getElementById('catRow').addEventListener('click', (e) => {
    const chip = e.target.closest('.cat-chip');
    if(!chip) return;
    document.querySelectorAll('.cat-chip').forEach(c => c.classList.remove('active'));
    chip.classList.add('active');
    const cat = chip.dataset.cat;
    const filtered = cat === 'todas' ? deals : deals.filter(d => d.cat === cat);
    render(filtered);
  });

  // ---- Search ----
  function doSearch(){
    const q = document.getElementById('searchInput').value.trim().toLowerCase();
    if(!q){ render(deals); return; }
    const filtered = deals.filter(d =>
      d.title.toLowerCase().includes(q) || d.store.toLowerCase().includes(q) || d.cat.includes(q)
    );
    render(filtered);
    document.querySelectorAll('.cat-chip').forEach(c => c.classList.remove('active'));
    document.querySelector('.cat-chip[data-cat="todas"]').classList.add('active');
    document.getElementById('ofertas').scrollIntoView({behavior:'smooth'});
  }
  document.getElementById('searchBtn').addEventListener('click', doSearch);
  document.getElementById('searchInput').addEventListener('keydown', e => { if(e.key === 'Enter') doSearch(); });
</script>

</body>
</html>
