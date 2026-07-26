<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bavarian Motorworks — Authorized BMW Showroom</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;500;600;700&family=Inter:wght@400;500;600&family=Inter+Tight:wght@500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0b0d10;
    --panel:#14171b;
    --panel-2:#1b1f24;
    --line:#2a2f36;
    --ink:#f4f5f6;
    --ink-dim:#a8adb5;
    --blue:#1c69d4;
    --blue-bright:#4f9fff;
    --silver:#c9ccd1;
    --radius:2px;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--bg);
    color:var(--ink);
    font-family:'Inter',sans-serif;
    overflow-x:hidden;
  }
  h1,h2,h3,.display{
    font-family:'Oswald',sans-serif;
    text-transform:uppercase;
    letter-spacing:0.02em;
  }
  a{color:inherit;text-decoration:none;}
  img{max-width:100%;display:block;}
  .wrap{max-width:1240px;margin:0 auto;padding:0 32px;}
  @media(max-width:640px){.wrap{padding:0 20px;}}

  /* ---------- NAV ---------- */
  header{
    position:fixed;top:0;left:0;right:0;z-index:100;
    background:rgba(11,13,16,0.85);
    backdrop-filter:blur(10px);
    border-bottom:1px solid var(--line);
  }
  nav{display:flex;align-items:center;justify-content:space-between;height:76px;}
  .logo{font-family:'Oswald';font-weight:700;font-size:20px;letter-spacing:0.08em;}
  .logo span{color:var(--blue-bright);}
  .navlinks{display:flex;gap:36px;font-size:13px;letter-spacing:0.06em;text-transform:uppercase;color:var(--ink-dim);}
  .navlinks a:hover{color:var(--ink);}
  .nav-cta{
    border:1px solid var(--blue);
    color:var(--blue-bright);
    padding:10px 22px;
    font-size:12px;letter-spacing:0.08em;text-transform:uppercase;
    transition:all .25s;
  }
  .nav-cta:hover{background:var(--blue);color:#fff;}
  @media(max-width:900px){.navlinks{display:none;}}

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    min-height:100vh;
    display:flex;align-items:center;
    padding-top:76px;
    background:
      radial-gradient(ellipse 900px 500px at 80% 20%, rgba(28,105,212,0.18), transparent 60%),
      linear-gradient(180deg,#0b0d10 0%, #0e1114 100%);
    overflow:hidden;
  }
  .hero-grid{display:grid;grid-template-columns:1.1fr 0.9fr;gap:40px;align-items:center;width:100%;}
  @media(max-width:900px){.hero-grid{grid-template-columns:1fr;}}
  .eyebrow{
    color:var(--blue-bright);
    font-size:13px;letter-spacing:0.18em;text-transform:uppercase;
    display:flex;align-items:center;gap:12px;margin-bottom:22px;
  }
  .eyebrow::before{content:"";width:32px;height:1px;background:var(--blue-bright);}
  .hero h1{
    font-size:clamp(42px,6vw,74px);
    line-height:0.98;
    font-weight:700;
    margin-bottom:26px;
  }
  .hero h1 em{font-style:normal;color:var(--blue-bright);}
  .hero p.lede{
    font-size:17px;color:var(--ink-dim);max-width:460px;line-height:1.6;margin-bottom:36px;
  }
  .cta-row{display:flex;gap:16px;flex-wrap:wrap;}
  .btn-primary{
    background:var(--blue);color:#fff;padding:16px 32px;font-size:13px;
    letter-spacing:0.08em;text-transform:uppercase;font-weight:600;
    border:1px solid var(--blue);transition:all .25s;
  }
  .btn-primary:hover{background:#1558b0;}
  .btn-ghost{
    padding:16px 32px;font-size:13px;letter-spacing:0.08em;text-transform:uppercase;
    border:1px solid var(--line);color:var(--ink);transition:all .25s;
  }
  .btn-ghost:hover{border-color:var(--ink-dim);}

  /* Hero visual: SVG silhouette + speed lines (signature element) */
  .hero-art{position:relative;height:420px;}
  .speed-lines{position:absolute;inset:0;overflow:hidden;}
  .speed-lines .line{
    position:absolute;height:1px;right:0;
    background:linear-gradient(90deg, transparent, var(--blue-bright));
    animation:dash 3.2s linear infinite;
    opacity:0.5;
  }
  @keyframes dash{
    0%{transform:translateX(120%);opacity:0;}
    10%{opacity:0.6;}
    100%{transform:translateX(-30%);opacity:0;}
  }
  .car-silhouette{position:absolute;bottom:30px;left:0;right:0;}
  .stat-row{display:flex;gap:36px;margin-top:34px;padding-top:28px;border-top:1px solid var(--line);}
  .stat b{display:block;font-family:'Oswald';font-size:26px;color:var(--ink);}
  .stat span{font-size:11px;color:var(--ink-dim);letter-spacing:0.08em;text-transform:uppercase;}

  /* ---------- SECTION LABEL ---------- */
  .section{padding:110px 0;}
  .section-tight{padding:80px 0;}
  .sec-head{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:56px;gap:24px;flex-wrap:wrap;}
  .sec-head h2{font-size:clamp(28px,3.4vw,42px);}
  .sec-head p{color:var(--ink-dim);max-width:380px;font-size:15px;line-height:1.6;}
  .kicker{color:var(--blue-bright);font-size:12px;letter-spacing:0.18em;text-transform:uppercase;margin-bottom:14px;display:block;}

  /* ---------- MODEL LINEUP ---------- */
  .models{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--line);border:1px solid var(--line);}
  @media(max-width:900px){.models{grid-template-columns:1fr;}}
  .model-card{background:var(--panel);padding:36px 32px 32px;position:relative;transition:background .3s;}
  .model-card:hover{background:var(--panel-2);}
  .model-visual{
    height:150px;display:flex;align-items:center;justify-content:center;margin-bottom:24px;
    background:radial-gradient(ellipse at center, rgba(28,105,212,0.12), transparent 70%);
  }
  .model-visual svg{width:100%;height:100px;}
  .model-tag{font-size:11px;letter-spacing:0.1em;color:var(--ink-dim);text-transform:uppercase;margin-bottom:6px;}
  .model-card h3{font-size:24px;margin-bottom:10px;}
  .model-specs{display:flex;gap:18px;margin:18px 0 22px;font-size:12px;color:var(--ink-dim);}
  .model-specs b{color:var(--ink);font-family:'Oswald';font-size:15px;display:block;}
  .model-price{font-family:'Oswald';font-size:20px;color:var(--blue-bright);margin-bottom:18px;}
  .model-link{font-size:12px;letter-spacing:0.08em;text-transform:uppercase;border-bottom:1px solid var(--blue);padding-bottom:3px;}

  /* image placeholder slots — swap background-image with your own 4K photography */
  .photo-slot{
    aspect-ratio:16/10;
    background:
      linear-gradient(135deg, #1b1f24 0%, #23272d 100%);
    border:1px dashed var(--line);
    display:flex;flex-direction:column;align-items:center;justify-content:center;
    gap:8px;color:var(--ink-dim);font-size:11px;letter-spacing:0.06em;text-transform:uppercase;
    text-align:center;padding:20px;
  }
  .photo-slot svg{opacity:0.35;width:40px;height:40px;}

  /* ---------- EXPERIENCE / GALLERY ---------- */
  .gallery-grid{display:grid;grid-template-columns:1.3fr 1fr 1fr;grid-template-rows:auto auto;gap:14px;}
  @media(max-width:900px){.gallery-grid{grid-template-columns:1fr 1fr;}}
  .gallery-grid .g1{grid-row:span 2;}
  @media(max-width:640px){.gallery-grid{grid-template-columns:1fr;}.gallery-grid .g1{grid-row:auto;}}

  /* ---------- WHY US ---------- */
  .features{display:grid;grid-template-columns:repeat(4,1fr);gap:28px;}
  @media(max-width:900px){.features{grid-template-columns:repeat(2,1fr);}}
  @media(max-width:560px){.features{grid-template-columns:1fr;}}
  .feature{border-top:2px solid var(--blue);padding-top:20px;}
  .feature .num{font-family:'Oswald';font-size:13px;color:var(--ink-dim);margin-bottom:14px;}
  .feature h3{font-size:18px;margin-bottom:10px;font-weight:600;text-transform:none;font-family:'Inter';}
  .feature p{font-size:14px;color:var(--ink-dim);line-height:1.6;}

  /* ---------- TESTIMONIAL ---------- */
  .testimonial{
    background:var(--panel);border:1px solid var(--line);
    padding:60px;position:relative;
  }
  @media(max-width:640px){.testimonial{padding:36px 28px;}}
  .testimonial q{
    font-family:'Oswald';font-size:clamp(20px,2.6vw,30px);
    font-style:normal;text-transform:none;line-height:1.4;display:block;margin-bottom:28px;
  }
  .testi-author{display:flex;align-items:center;gap:14px;}
  .avatar-ring{width:44px;height:44px;border-radius:50%;border:1px solid var(--blue);display:flex;align-items:center;justify-content:center;font-family:'Oswald';color:var(--blue-bright);}
  .testi-author span{display:block;font-size:12px;color:var(--ink-dim);}
  .testi-author b{font-size:14px;font-weight:600;}

  /* ---------- CONTACT / FORM ---------- */
  .contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:60px;}
  @media(max-width:900px){.contact-grid{grid-template-columns:1fr;gap:40px;}}
  .form-row{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px;}
  @media(max-width:520px){.form-row{grid-template-columns:1fr;}}
  input,select,textarea{
    width:100%;background:var(--panel);border:1px solid var(--line);color:var(--ink);
    padding:14px 16px;font-family:'Inter';font-size:14px;
  }
  input:focus,select:focus,textarea:focus{outline:2px solid var(--blue-bright);outline-offset:1px;border-color:var(--blue);}
  label{font-size:11px;letter-spacing:0.08em;text-transform:uppercase;color:var(--ink-dim);display:block;margin-bottom:8px;}
  textarea{resize:vertical;min-height:100px;}
  .full-btn{width:100%;padding:16px;background:var(--blue);color:#fff;border:none;font-size:13px;letter-spacing:0.08em;text-transform:uppercase;font-weight:600;cursor:pointer;transition:background .25s;}
  .full-btn:hover{background:#1558b0;}
  .info-block{margin-bottom:28px;}
  .info-block h3{font-size:12px;letter-spacing:0.1em;color:var(--ink-dim);margin-bottom:8px;text-transform:uppercase;font-family:'Inter';font-weight:600;}
  .info-block p{font-size:16px;}
  .map-strip{height:1px;background:var(--line);margin:28px 0;}

  /* ---------- FOOTER ---------- */
  footer{border-top:1px solid var(--line);padding:48px 0;}
  .foot-grid{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:20px;}
  .foot-links{display:flex;gap:28px;font-size:13px;color:var(--ink-dim);}
  .fine-print{font-size:12px;color:#5a5f66;margin-top:24px;line-height:1.6;}

  ::selection{background:var(--blue);color:#fff;}

  @media(prefers-reduced-motion:reduce){
    .speed-lines .line{animation:none;display:none;}
    html{scroll-behavior:auto;}
  }
</style>
</head>
<body>

<header>
  <div class="wrap">
    <nav>
      <div class="logo">BAVARIAN<span>.</span>MOTORWORKS</div>
      <div class="navlinks">
        <a href="#lineup">Lineup</a>
        <a href="#experience">Showroom</a>
        <a href="#why">Why Us</a>
        <a href="#contact">Visit</a>
      </div>
      <a href="#contact" class="nav-cta">Book Test Drive</a>
    </nav>
  </div>
</header>

<!-- HERO -->
<section class="hero">
  <div class="wrap hero-grid">
    <div>
      <div class="eyebrow">Authorized BMW Showroom · Est. 2010</div>
      <h1>The Ultimate<br><em>Driving Machine</em>,<br>Delivered Today.</h1>
      <p class="lede">From the M-Series track weapons to the effortless calm of the 7 Series — explore the full BMW lineup, drive one home this week, and get factory-backed service for the life of the car.</p>
      <div class="cta-row">
        <a href="#contact" class="btn-primary">Schedule a Test Drive</a>
        <a href="#lineup" class="btn-ghost">View Full Lineup</a>
      </div>
      <div class="stat-row">
        <div class="stat"><b>140+</b><span>Cars In Stock</span></div>
        <div class="stat"><b>4.9/5</b><span>Buyer Rating</span></div>
        <div class="stat"><b>24 Mo</b><span>0% APR Available</span></div>
      </div>
    </div>
    <div class="hero-art">
      <div class="speed-lines">
        <div class="line" style="top:20%; width:60%; animation-delay:0s;"></div>
        <div class="line" style="top:38%; width:80%; animation-delay:0.6s;"></div>
        <div class="line" style="top:56%; width:45%; animation-delay:1.2s;"></div>
        <div class="line" style="top:74%; width:70%; animation-delay:1.8s;"></div>
      </div>
      <svg class="car-silhouette" viewBox="0 0 600 200" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M40 150 C 60 100, 130 80, 190 78 L 260 40 C 300 25, 380 25, 420 45 L 470 78 C 520 80, 555 105, 565 140 L 565 155 L 40 155 Z"
          fill="none" stroke="#4f9fff" stroke-width="2" opacity="0.55"/>
        <circle cx="150" cy="158" r="26" fill="none" stroke="#c9ccd1" stroke-width="2" opacity="0.6"/>
        <circle cx="150" cy="158" r="10" fill="#1c69d4" opacity="0.6"/>
        <circle cx="460" cy="158" r="26" fill="none" stroke="#c9ccd1" stroke-width="2" opacity="0.6"/>
        <circle cx="460" cy="158" r="10" fill="#1c69d4" opacity="0.6"/>
        <line x1="40" y1="158" x2="565" y2="158" stroke="#2a2f36" stroke-width="2"/>
      </svg>
    </div>
  </div>
</section>

<!-- LINEUP -->
<section class="section" id="lineup">
  <div class="wrap">
    <div class="sec-head">
      <div>
        <span class="kicker">Current Lineup</span>
        <h2>Three Ways to<br>Drive Bavarian.</h2>
      </div>
      <p>Every model below is available for immediate test drive at our showroom floor, with full factory warranty and certified BMW technicians on site.</p>
    </div>

    <div class="models">
      <div class="model-card">
        <div class="model-visual">
          <svg viewBox="0 0 300 100"><path d="M20 75 C 35 45,70 35,100 34 L140 15 C165 8,200 8,220 18 L255 34 C275 35,292 50,296 70" fill="none" stroke="#4f9fff" stroke-width="2" opacity="0.7"/><circle cx="85" cy="78" r="13" fill="none" stroke="#c9ccd1" stroke-width="2"/><circle cx="240" cy="78" r="13" fill="none" stroke="#c9ccd1" stroke-width="2"/></svg>
        </div>
        <div class="model-tag">Sports Sedan</div>
        <h3>3 Series</h3>
        <div class="model-specs">
          <div><b>255 hp</b>Power</div>
          <div><b>4.4s</b>0–60 mph</div>
          <div><b>36 mpg</b>Highway</div>
        </div>
        <div class="model-price">Starting at $43,800</div>
        <a href="#contact" class="model-link">Reserve This Model →</a>
      </div>

      <div class="model-card">
        <div class="model-visual">
          <svg viewBox="0 0 300 100"><path d="M15 78 C 25 40,60 28,110 27 L150 10 C178 3,210 5,232 16 L268 30 C282 34,292 50,295 72" fill="none" stroke="#4f9fff" stroke-width="2" opacity="0.7"/><circle cx="90" cy="80" r="14" fill="none" stroke="#c9ccd1" stroke-width="2"/><circle cx="235" cy="80" r="14" fill="none" stroke="#c9ccd1" stroke-width="2"/></svg>
        </div>
        <div class="model-tag">Performance SAV</div>
        <h3>X5 M</h3>
        <div class="model-specs">
          <div><b>600 hp</b>Power</div>
          <div><b>3.8s</b>0–60 mph</div>
          <div><b>AWD</b>Drivetrain</div>
        </div>
        <div class="model-price">Starting at $112,500</div>
        <a href="#contact" class="model-link">Reserve This Model →</a>
      </div>

      <div class="model-card">
        <div class="model-visual">
          <svg viewBox="0 0 300 100"><path d="M18 76 C 30 42,65 30,105 28 L145 12 C170 5,205 5,228 16 L262 30 C280 33,290 48,294 70" fill="none" stroke="#4f9fff" stroke-width="2" opacity="0.7"/><circle cx="88" cy="79" r="14" fill="none" stroke="#c9ccd1" stroke-width="2"/><circle cx="232" cy="79" r="14" fill="none" stroke="#c9ccd1" stroke-width="2"/></svg>
        </div>
        <div class="model-tag">Executive Flagship</div>
        <h3>7 Series</h3>
        <div class="model-specs">
          <div><b>536 hp</b>Power</div>
          <div><b>4.1s</b>0–60 mph</div>
          <div><b>Elec.</b>Available</div>
        </div>
        <div class="model-price">Starting at $95,200</div>
        <a href="#contact" class="model-link">Reserve This Model →</a>
      </div>
    </div>
  </div>
</section>

<!-- SHOWROOM / GALLERY -->
<section class="section-tight" id="experience" style="background:var(--panel);border-top:1px solid var(--line);border-bottom:1px solid var(--line);">
  <div class="wrap">
    <div class="sec-head">
      <div>
        <span class="kicker">The Showroom Floor</span>
        <h2>Walk It Before<br>You Buy It.</h2>
      </div>
      <p>These slots are sized and cropped for full 4K dealership photography — drop your own showroom, delivery-bay, and vehicle shots straight in.</p>
    </div>
    <div class="gallery-grid">
      <div class="photo-slot g1">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="1"/><circle cx="8.5" cy="9.5" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        Showroom Floor — 3840×2400
      </div>
      <div class="photo-slot">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="1"/><circle cx="8.5" cy="9.5" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        Delivery Bay — 3840×2160
      </div>
      <div class="photo-slot">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="1"/><circle cx="8.5" cy="9.5" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        Service Center — 3840×2160
      </div>
      <div class="photo-slot">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="5" width="18" height="14" rx="1"/><circle cx="8.5" cy="9.5" r="1.5"/><path d="M21 15l-5-5-4 4-3-3-6 6"/></svg>
        Detail Bay — 3840×2160
      </div>
    </div>
  </div>
</section>

<!-- WHY US -->
<section class="section" id="why">
  <div class="wrap">
    <div class="sec-head">
      <div>
        <span class="kicker">Why Buy Here</span>
        <h2>Built On Trust,<br>Not Just Torque.</h2>
      </div>
    </div>
    <div class="features">
      <div class="feature">
        <div class="num">01</div>
        <h3>Factory-Certified Techs</h3>
        <p>Every service bay is staffed by BMW-trained technicians using OEM parts exclusively.</p>
      </div>
      <div class="feature">
        <div class="num">02</div>
        <h3>Transparent Pricing</h3>
        <p>No hidden dealer fees. The price on the sticker is the price you sign for.</p>
      </div>
      <div class="feature">
        <div class="num">03</div>
        <h3>Flexible Financing</h3>
        <p>In-house financing with rates as low as 0% APR for qualified buyers.</p>
      </div>
      <div class="feature">
        <div class="num">04</div>
        <h3>7-Day Return Window</h3>
        <p>Not in love with the drive? Bring it back within a week, no questions asked.</p>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONIAL -->
<section class="section-tight">
  <div class="wrap">
    <div class="testimonial">
      <q>"I walked in for an X5 and walked out with a delivery date, a fair trade-in number, and zero pressure. This is what buying a car should feel like."</q>
      <div class="testi-author">
        <div class="avatar-ring">JR</div>
        <div>
          <b>James R.</b>
          <span>X5 M Owner, Purchased 2025</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="section" id="contact" style="background:var(--panel);border-top:1px solid var(--line);">
  <div class="wrap contact-grid">
    <div>
      <span class="kicker">Get In Touch</span>
      <h2 style="font-size:clamp(26px,3vw,38px);margin-bottom:24px;">Book Your Test Drive.</h2>
      <div class="info-block">
        <h3>Showroom Address</h3>
        <p>1400 Autobahn Way, Metro Business District</p>
      </div>
      <div class="info-block">
        <h3>Sales Line</h3>
        <p>(555) 019-2847</p>
      </div>
      <div class="info-block">
        <h3>Hours</h3>
        <p>Mon–Sat: 9:00 AM – 8:00 PM · Sun: 11:00 AM – 5:00 PM</p>
      </div>
    </div>
    <form onsubmit="event.preventDefault(); document.getElementById('form-success').style.display='block'; this.reset();">
      <div class="form-row">
        <div>
          <label>Full Name</label>
          <input type="text" required placeholder="Your name">
        </div>
        <div>
          <label>Phone Number</label>
          <input type="tel" required placeholder="(555) 000-0000">
        </div>
      </div>
      <div class="form-row">
        <div>
          <label>Model Interested In</label>
          <select>
            <option>3 Series</option>
            <option>X5 M</option>
            <option>7 Series</option>
            <option>Other / Not Sure</option>
          </select>
        </div>
        <div>
          <label>Preferred Visit Day</label>
          <input type="date">
        </div>
      </div>
      <label style="margin-top:4px;">Message</label>
      <textarea placeholder="Tell us what you're looking for..." style="margin-bottom:20px;"></textarea>
      <button type="submit" class="full-btn">Request Test Drive</button>
      <p id="form-success" style="display:none;color:var(--blue-bright);font-size:13px;margin-top:14px;">Thanks — our sales team will call within 1 business hour.</p>
    </form>
  </div>
</section>

<footer>
  <div class="wrap">
    <div class="foot-grid">
      <div class="logo" style="font-size:16px;">BAVARIAN<span>.</span>MOTORWORKS</div>
      <div class="foot-links">
        <a href="#lineup">Lineup</a>
        <a href="#experience">Showroom</a>
        <a href="#contact">Visit</a>
        <a href="#">Financing</a>
      </div>
    </div>
    <p class="fine-print">Bavarian Motorworks is an independently owned, authorized BMW dealership. BMW and related model names are trademarks of BMW AG and are used here for identification purposes only. This demo template ships with placeholder imagery — replace with your own licensed dealership and vehicle photography before publishing.</p>
  </div>
</footer>

</body>
</html>
