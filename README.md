# classic-bulbs-
Incandescent light bulbs 60 and 75 watt different brands  
classicbulbs/
  index.html
  assets/
    gv-75.jpg
    ge-reveal-75.jpg
    ge-75-6pack.jpg
    gv-60.jpg
    sylvania-60.jpg
    sylvania-75.jpg
    ge-90.jpg
    philips-60.jpg
    ge-softwhite-60.jpg
Rename/copy your images like this (matching what you provided):

/mnt/data/IMG_0910.JPG → assets/gv-75.jpg

/mnt/data/IMG_0962.JPG → assets/ge-reveal-75.jpg

/mnt/data/IMG_0919.JPG → assets/ge-75-6pack.jpg

/mnt/data/IMG_0922.JPG → assets/gv-60.jpg

/mnt/data/IMG_0960.JPG → assets/sylvania-60.jpg

/mnt/data/IMG_0950.JPG → assets/sylvania-75.jpg

/mnt/data/IMG_0945.JPG → assets/ge-90.jpg

/mnt/data/IMG_0925.JPG → assets/philips-60.jpg

/mnt/data/IMG_0929.JPG → assets/ge-softwhite-60.jpg

(If you keep them as .JPG, just update the filenames in the code.)

2) index.html (copy/paste)
After you paste this, scroll to PAYPAL_CLIENT_ID_HERE and replace it with your PayPal client id.

html
Copy code
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>ClassicBulbs.com — Vintage Incandescent Bulbs (2009–2011)</title>
  <meta name="description" content="ClassicBulbs.com sells genuine old-school incandescent light bulbs purchased 2009–2011. Limited supply, next-day shipping." />

  <!-- Basic SEO / sharing -->
  <meta property="og:title" content="ClassicBulbs.com — Vintage Incandescent Bulbs (2009–2011)" />
  <meta property="og:description" content="Real incandescent bulbs you can’t easily find anymore. Limited supply, stored indoors ~15 years." />
  <meta property="og:type" content="website" />

  <style>
    :root{
      --bg1:#0f172a;
      --bg2:#0b1224;
      --card:#0b1220cc;
      --stroke:#ffffff1a;
      --stroke2:#ffffff2a;
      --text:#e6edf6;
      --muted:#a6b3c3;
      --accent:#ffd166;
      --accent2:#ffb703;
      --good:#7ee081;
      --bad:#ff6b6b;
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius: 18px;
      --radius2: 28px;
      --max: 1180px;
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      color:var(--text);
      font-family:var(--sans);
      background:
        radial-gradient(1200px 800px at 15% 10%, rgba(255,209,102,.20), transparent 55%),
        radial-gradient(900px 700px at 85% 15%, rgba(255,183,3,.12), transparent 60%),
        radial-gradient(900px 700px at 30% 85%, rgba(126,224,129,.10), transparent 55%),
        linear-gradient(160deg, var(--bg1), var(--bg2));
      overflow-x:hidden;
    }

    /* Subtle "store lighting" pattern */
    body:before{
      content:"";
      position:fixed;
      inset:0;
      pointer-events:none;
      opacity:.16;
      background-image:
        radial-gradient(circle at 20% 25%, rgba(255,255,255,.18) 0 2px, transparent 3px),
        radial-gradient(circle at 70% 45%, rgba(255,255,255,.12) 0 2px, transparent 3px),
        radial-gradient(circle at 35% 70%, rgba(255,255,255,.10) 0 2px, transparent 3px);
      filter: blur(0.2px);
      mix-blend-mode: screen;
    }

    .frame{
      max-width:var(--max);
      margin:24px auto 60px;
      padding:18px;
    }

    .border-wrap{
      border-radius: var(--radius2);
      padding: 18px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.10), rgba(255,255,255,.03));
      box-shadow: var(--shadow);
      border: 1px solid rgba(255,255,255,.10);
      position:relative;
    }
    .border-wrap:before{
      content:"";
      position:absolute;
      inset:10px;
      border-radius: calc(var(--radius2) - 8px);
      border: 1px dashed rgba(255,255,255,.16);
      pointer-events:none;
    }

    header{
      padding: 18px 18px 0;
      display:flex;
      gap:18px;
      align-items:flex-start;
      justify-content:space-between;
      flex-wrap:wrap;
    }

    .brand{
      display:flex;
      flex-direction:column;
      gap:6px;
      min-width: 280px;
    }

    .logo{
      display:flex;
      align-items:center;
      gap:12px;
      font-weight:800;
      letter-spacing:.2px;
      font-size: 28px;
      line-height:1.1;
    }

    .bulb-icon{
      width:42px;height:42px;border-radius:14px;
      background: radial-gradient(circle at 35% 30%, #fff8dc, rgba(255,209,102,.85) 35%, rgba(255,183,3,.25) 70%, rgba(0,0,0,.15) 100%);
      border:1px solid rgba(255,255,255,.15);
      box-shadow: 0 10px 20px rgba(255,183,3,.10);
      position:relative;
      flex:0 0 auto;
    }
    .bulb-icon:after{
      content:"";
      position:absolute;
      width:16px;height:14px;
      left:50%;top:60%;
      transform:translate(-50%,-50%);
      border-radius: 0 0 10px 10px;
      background: rgba(0,0,0,.30);
      filter: blur(.2px);
      opacity:.55;
    }

    .tagline{
      color:var(--muted);
      max-width: 640px;
      font-size: 14px;
    }

    .pillbar{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      align-items:center;
    }

    .pill{
      display:inline-flex;
      gap:8px;
      align-items:center;
      padding:10px 12px;
      border-radius: 999px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.18);
      color: var(--text);
      font-size:13px;
    }
    .pill b{color: var(--accent)}
    .pill .dot{
      width:8px;height:8px;border-radius:99px;background: var(--good);
      box-shadow:0 0 0 4px rgba(126,224,129,.12);
    }

    nav{
      margin: 18px 18px 0;
      padding: 14px;
      border-radius: var(--radius);
      border:1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.18);
      display:flex;
      flex-wrap:wrap;
      gap:12px;
      align-items:center;
      justify-content:space-between;
    }

    .toc{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      align-items:center;
    }
    .toc a{
      text-decoration:none;
      color: var(--text);
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.06);
      padding:10px 12px;
      border-radius: 999px;
      font-size:13px;
      transition: transform .08s ease, background .12s ease;
    }
    .toc a:hover{ transform: translateY(-1px); background: rgba(255,255,255,.10); }

    .actions{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      align-items:center;
    }

    .btn{
      border:1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.06);
      color: var(--text);
      padding:10px 12px;
      border-radius: 12px;
      cursor:pointer;
      font-weight:600;
      font-size:13px;
      transition: transform .08s ease, background .12s ease, border-color .12s ease;
    }
    .btn:hover{ transform: translateY(-1px); background: rgba(255,255,255,.10); border-color: rgba(255,255,255,.22); }
    .btn.primary{
      background: linear-gradient(180deg, rgba(255,209,102,.95), rgba(255,183,3,.90));
      color:#1b1b1b;
      border-color: rgba(255,255,255,.12);
    }
    .btn.primary:hover{ background: linear-gradient(180deg, rgba(255,209,102,1), rgba(255,183,3,1)); }
    .btn.danger{ background: rgba(255,107,107,.14); border-color: rgba(255,107,107,.25); }

    main{
      padding: 18px;
      display:grid;
      grid-template-columns: 1.65fr .95fr;
      gap:16px;
      align-items:start;
    }

    @media (max-width: 980px){
      main{ grid-template-columns: 1fr; }
    }

    .card{
      border-radius: var(--radius);
      border:1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.18);
      box-shadow: 0 10px 22px rgba(0,0,0,.18);
      overflow:hidden;
    }
    .card .hd{
      padding:14px 14px 10px;
      border-bottom:1px solid rgba(255,255,255,.08);
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
      flex-wrap:wrap;
    }
    .card .hd h2, .card .hd h3{
      margin:0;
      font-size: 15px;
      letter-spacing:.2px;
    }
    .card .bd{ padding: 14px; }

    .notice{
      display:grid;
      gap:10px;
      color: var(--muted);
      font-size: 13px;
      line-height:1.45;
    }
    .notice b{ color: var(--text); }
    .notice .hi{ color: var(--accent); font-weight:700; }
    .notice ul{ margin:8px 0 0 18px; padding:0; }
    .notice li{ margin:4px 0; }

    .grid{
      display:grid;
      grid-template-columns: repeat(2, minmax(0,1fr));
      gap:12px;
    }
    @media (max-width: 720px){
      .grid{ grid-template-columns: 1fr; }
    }

    .product{
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.04);
      border-radius: 16px;
      overflow:hidden;
      display:flex;
      flex-direction:column;
      min-height: 100%;
    }
    .product .img{
      background: linear-gradient(180deg, rgba(255,255,255,.08), rgba(0,0,0,.10));
      border-bottom:1px solid rgba(255,255,255,.08);
      aspect-ratio: 16/10;
      display:flex;
      align-items:center;
      justify-content:center;
      overflow:hidden;
    }
    .product img{
      width:100%;
      height:100%;
      object-fit: cover;
      display:block;
    }
    .product .meta{
      padding:12px;
      display:grid;
      gap:8px;
    }
    .title{
      display:flex;
      align-items:flex-start;
      justify-content:space-between;
      gap:10px;
    }
    .title h4{
      margin:0;
      font-size:14px;
      line-height:1.2;
    }
    .sku{
      font-family:var(--mono);
      font-size:12px;
      color: var(--muted);
    }
    .specs{
      display:flex;
      flex-wrap:wrap;
      gap:8px;
      color: var(--muted);
      font-size:12px;
    }
    .chip{
      border:1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.16);
      padding:6px 8px;
      border-radius: 999px;
    }
    .row{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
      flex-wrap:wrap;
    }
    .price{
      font-weight:800;
      font-size:16px;
      color: var(--accent);
    }
    .stock{
      font-size:12px;
      color: var(--muted);
    }
    .qty{
      display:flex;
      align-items:center;
      gap:8px;
    }
    input[type="number"]{
      width:74px;
      padding:10px 10px;
      border-radius: 12px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.22);
      color: var(--text);
      outline:none;
    }
    input[type="number"]:focus{
      border-color: rgba(255,209,102,.45);
      box-shadow: 0 0 0 4px rgba(255,209,102,.10);
    }

    .section-anchor{
      scroll-margin-top: 90px;
    }

    /* Cart */
    .cart-list{
      display:grid;
      gap:10px;
    }
    .cart-item{
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.04);
      border-radius: 14px;
      padding:10px;
      display:grid;
      gap:8px;
    }
    .cart-top{
      display:flex;
      gap:10px;
      align-items:flex-start;
      justify-content:space-between;
    }
    .cart-top b{ font-size:13px; }
    .cart-top .mini{
      font-family:var(--mono);
      font-size:11px;
      color: var(--muted);
    }
    .totals{
      display:grid;
      gap:6px;
      font-size:13px;
      color: var(--muted);
      border-top:1px solid rgba(255,255,255,.08);
      padding-top:10px;
      margin-top:6px;
    }
    .totals .line{
      display:flex; align-items:center; justify-content:space-between; gap:8px;
    }
    .totals .grand{
      color: var(--text);
      font-weight:900;
      font-size: 15px;
    }
    .small{
      font-size:12px;
      color: var(--muted);
      line-height:1.45;
    }
    .divider{
      height:1px;
      background: rgba(255,255,255,.08);
      margin: 10px 0;
    }

    /* Message center */
    form{
      display:grid;
      gap:10px;
    }
    label{ font-size:12px; color: var(--muted); }
    input[type="text"], input[type="email"], textarea{
      width:100%;
      padding:10px 12px;
      border-radius: 12px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.22);
      color: var(--text);
      outline:none;
      font: inherit;
    }
    textarea{ min-height: 110px; resize: vertical; }
    input:focus, textarea:focus{
      border-color: rgba(255,209,102,.45);
      box-shadow: 0 0 0 4px rgba(255,209,102,.10);
    }
    .hp{
      position:absolute; left:-9999px; width:1px; height:1px; overflow:hidden;
    }

    footer{
      padding: 0 18px 18px;
      color: var(--muted);
      font-size:12px;
      line-height:1.55;
    }
    footer a{ color: var(--accent); text-decoration:none; }
  </style>

  <!-- PayPal SDK (replace PAYPAL_CLIENT_ID_HERE) -->
  <script src="https://www.paypal.com/sdk/js?client-id=PAYPAL_CLIENT_ID_HERE&currency=USD&intent=capture"></script>
</head>

<body>
  <div class="frame">
    <div class="border-wrap">

      <header>
        <div class="brand">
          <div class="logo">
            <span class="bulb-icon" aria-hidden="true"></span>
            <span>ClassicBulbs<span style="color:var(--accent)">.com</span></span>
          </div>
          <div class="tagline">
            Vintage, old-school <b>incandescent</b> bulbs purchased <b>2009–2011</b>. Stored indoors for ~15 years.
            Packaging may show light age — bulbs are the real deal you can’t easily find anymore.
          </div>
        </div>

        <div class="pillbar">
          <div class="pill"><span class="dot"></span> <b>Limited supply</b> • while inventory lasts</div>
          <div class="pill">🚚 <b>Next-day shipping</b> • ships next business day</div>
          <div class="pill">📦 Shipping: <b>$14.95</b> first box + <b>$7.95</b> each additional</div>
        </div>
      </header>

      <nav>
        <div class="toc">
          <span style="font-size:12px;color:var(--muted);margin-right:6px;">Browse wattage:</span>
          <a href="#w60">60W</a>
          <a href="#w75">75W</a>
          <a href="#w90">90W</a>
          <a href="#message-center">Message Center</a>
        </div>
        <div class="actions">
          <button class="btn" id="btnScrollCart" type="button">View Cart</button>
          <button class="btn danger" id="btnClearCart" type="button">Clear Cart</button>
        </div>
      </nav>

      <main>
        <!-- LEFT: Catalog -->
        <section class="card" aria-label="Catalog">
          <div class="hd">
            <h2>Catalog (Incandescent • 2009–2011)</h2>
            <div class="small">All items are sold as <b>packs</b> (pack size shown). Inventory is live-limited to quantities listed.</div>
          </div>
          <div class="bd notice">
            <div>
              <b>Important notes</b>
              <ul>
                <li><span class="hi">Limited supply:</span> once a pack is gone, it’s gone.</li>
                <li><b>Condition:</b> stored indoors ~15 years; packaging shows minor age; contents are genuine.</li>
                <li><b>Shipping:</b> next business day. Shipping charge is calculated as <b>$14.95 for the first box</b> + <b>$7.95 per additional box</b>.</li>
              </ul>
            </div>

            <!-- 60W -->
            <div class="divider"></div>
            <h3 id="w60" class="section-anchor" style="margin:0;color:var(--text);">60 Watt</h3>
            <div class="grid" id="grid60"></div>

            <!-- 75W -->
            <div class="divider"></div>
            <h3 id="w75" class="section-anchor" style="margin:0;color:var(--text);">75 Watt</h3>
            <div class="grid" id="grid75"></div>

            <!-- 90W -->
            <div class="divider"></div>
            <h3 id="w90" class="section-anchor" style="margin:0;color:var(--text);">90 Watt</h3>
            <div class="grid" id="grid90"></div>
          </div>
        </section>

        <!-- RIGHT: Cart + Checkout + Message center -->
        <aside style="display:grid;gap:16px;">
          <section class="card" id="cartCard" aria-label="Cart">
            <div class="hd">
              <h2>Cart</h2>
              <div class="small" id="cartCount">0 items</div>
            </div>
            <div class="bd">
              <div class="cart-list" id="cartList"></div>

              <div class="totals" id="totals">
                <div class="line"><span>Subtotal</span><span id="subTotal">$0.00</span></div>
                <div class="line"><span>Shipping</span><span id="shipTotal">$0.00</span></div>
                <div class="line grand"><span>Total</span><span id="grandTotal">$0.00</span></div>
                <div class="small">
                  Shipping is calculated as <b>$14.95</b> for the first box + <b>$7.95</b> each additional box.
                  <br/>For simplicity, this checkout treats <b>each pack as one shippable box</b> in combined shipping.
                </div>
              </div>

              <div class="divider"></div>

              <div class="small">
                <b>PayPal Checkout</b><br/>
                Replace <span style="font-family:var(--mono);">PAYPAL_CLIENT_ID_HERE</span> in the page source with your PayPal Client ID.
              </div>
              <div id="paypal-buttons" style="margin-top:10px;"></div>
            </div>
          </section>

          <section class="card" id="message-center" aria-label="Message Center">
            <div class="hd">
              <h2>Message Center</h2>
              <div class="small">Spam-blocked contact form</div>
            </div>
            <div class="bd">
              <!-- Netlify Forms enabled -->
              <form name="message-center" method="POST" data-netlify="true" netlify-honeypot="bot-field" id="contactForm">
                <input type="hidden" name="form-name" value="message-center" />
                <p class="hp">
                  <label>Don’t fill this out: <input name="bot-field" /></label>
                </p>

                <div>
                  <label for="name">Name</label>
                  <input id="name" name="name" type="text" autocomplete="name" required minlength="2" />
                </div>

                <div>
                  <label for="email">Email</label>
                  <input id="email" name="email" type="email" autocomplete="email" required />
                </div>

                <div>
                  <label for="topic">Topic</label>
                  <input id="topic" name="topic" type="text" placeholder="Order question, bulk request, product question…" required />
                </div>

                <div>
                  <label for="message">Message</label>
                  <textarea id="message" name="message" required minlength="10"></textarea>
                </div>

                <button class="btn primary" type="submit" id="sendBtn">Send Message</button>
                <div class="small" id="formStatus"></div>
              </form>
            </div>
          </section>
        </aside>
      </main>

      <footer>
        <div class="divider"></div>
        <div>
          <b>ClassicBulbs.com</b> sells vintage incandescent lighting inventory (purchased 2009–2011).
          Photos show the actual packages; minor shelf-wear may be present.
          <br/>
          Need something special (bulk order, mixed wattage)? Use the <a href="#message-center">Message Center</a>.
        </div>
      </footer>
    </div>
  </div>

<script>
  // ---------------------------
  // Inventory (your exact list)
  // ---------------------------
  // NOTE: If an item doesn't have a photo provided, image is set to "" (shows placeholder).
  const products = [
    // 60W
    {
      id:"SYL-60-4",
      watt:60,
      name:"Sylvania DOUBLELife Soft White 60W",
      pack:"Pack of 4 (A19)",
      lumens:"(see package)",
      notes:"DOUBLELife series • real incandescent",
      price:34.95,
      stock:18,
      image:"assets/sylvania-60.jpg",
      tags:["Incandescent","Soft White","A19","Limited"]
    },
    {
      id:"GE-SW-60-4-840",
      watt:60,
      name:"GE Soft White 60W (840 lumens, ~0.9 year life)",
      pack:"Pack of 4 (A19)",
      lumens:"840 lumens",
      notes:"Soft White",
      price:34.95,
      stock:32, // your: 32 packs of ge softwhite 8040 lumen (interpreting as 840 lumens)
      image:"assets/ge-softwhite-60.jpg",
      tags:["Incandescent","Soft White","A19"]
    },
    {
      id:"GE-DL-60-4-780",
      watt:60,
      name:"GE Double Life 60W (780 lumens, ~1.8 year life)",
      pack:"Pack of 4 (A19)",
      lumens:"780 lumens",
      notes:"Longer-life incandescent (package may vary)",
      price:34.95,
      stock:11,
      image:"", // photo not provided in your set
      tags:["Incandescent","Double Life","A19"]
    },
    {
      id:"GV-60-4-760",
      watt:60,
      name:"Great Value A19 Household 60W (760 lumens, 1000 hours)",
      pack:"Pack of 4 (A19)",
      lumens:"760 lumens",
      notes:"Soft White • indoor/outdoor",
      price:24.95,
      stock:32,
      image:"assets/gv-60.jpg",
      tags:["Incandescent","Value","A19"]
    },
    {
      id:"PH-60-4-860",
      watt:60,
      name:"Philips Soft White 60W (860 lumens)",
      pack:"Pack of 4 (A19)",
      lumens:"860 lumens",
      notes:"Classic Philips incandescent",
      price:34.95,
      stock:8,
      image:"assets/philips-60.jpg",
      tags:["Incandescent","Soft White","A19"]
    },

    // 75W
    {
      id:"SYL-75-4",
      watt:75,
      name:"Sylvania DOUBLELife Soft White 75W",
      pack:"Pack of 4 (A19)",
      lumens:"(see package)",
      notes:"DOUBLELife series • real incandescent",
      price:39.95,
      stock:19,
      image:"assets/sylvania-75.jpg",
      tags:["Incandescent","Soft White","A19","Limited"]
    },
    {
      id:"GE-REVEAL-75-4-830",
      watt:75,
      name:"GE Reveal 75W (830 lumens)",
      pack:"Pack of 4 (A19)",
      lumens:"830 lumens",
      notes:"Reveal line (clean, beautiful light)",
      price:49.95,
      stock:20,
      image:"assets/ge-reveal-75.jpg",
      tags:["Incandescent","Reveal","A19"]
    },
    {
      id:"GE-75-6-1085",
      watt:75,
      name:"GE Soft White 75W (1085 lumens, ~1.4 year life)",
      pack:"Pack of 6 (A19)",
      lumens:"1085 lumens",
      notes:"Value Pack • classic incandescent",
      price:49.95,
      stock:59,
      image:"assets/ge-75-6pack.jpg",
      tags:["Incandescent","Soft White","A19","6-Pack"]
    },
    {
      id:"GE-DL-75-4-1085",
      watt:75,
      name:"GE Double Life 75W (1085 lumens, ~1.4 year life)",
      pack:"Pack of 4 (A19)",
      lumens:"1085 lumens",
      notes:"Double Life incandescent (package may vary)",
      price:34.95,
      stock:23,
      image:"", // photo not provided in your set
      tags:["Incandescent","Double Life","A19"]
    },
    {
      id:"GV-75-4-950",
      watt:75,
      name:"Great Value A19 Household 75W (950 lumens, 1000 hours)",
      pack:"Pack of 4 (A19)",
      lumens:"950 lumens",
      notes:"Soft White • indoor/outdoor",
      price:24.95,
      stock:11,
      image:"assets/gv-75.jpg",
      tags:["Incandescent","Value","A19"]
    },

    // 90W
    {
      id:"GE-90-4-1450",
      watt:90,
      name:"GE Soft White 90W (1450 lumens, ~0.9 year life)",
      pack:"Pack of 4 (A19)",
      lumens:"1450 lumens",
      notes:"Longer Life line",
      price:29.95,
      stock:52,
      image:"assets/ge-90.jpg",
      tags:["Incandescent","Soft White","A19"]
    },
  ];

  // ---------------------------
  // Helpers
  // ---------------------------
  const money = (n) => n.toLocaleString(undefined, {style:"currency", currency:"USD"});
  const el = (q) => document.querySelector(q);
  const cart = new Map(); // id -> qty

  function shippingForBoxes(boxCount){
    // Shipping rule: $14.95 first box + $7.95 each additional
    if(boxCount <= 0) return 0;
    return 14.95 + (boxCount - 1) * 7.95;
  }

  function getCartLines(){
    const lines = [];
    for(const [id, qty] of cart.entries()){
      const p = products.find(x=>x.id===id);
      if(!p) continue;
      lines.push({product:p, qty});
    }
    return lines;
  }

  function calcTotals(){
    const lines = getCartLines();
    const subtotal = lines.reduce((s,l)=> s + l.product.price * l.qty, 0);
    const boxes = lines.reduce((s,l)=> s + l.qty, 0); // each pack = one "box" for combined shipping
    const ship = shippingForBoxes(boxes);
    return { lines, subtotal, ship, total: subtotal + ship, boxes };
  }

  // ---------------------------
  // Rendering
  // ---------------------------
  function productCard(p){
    const imgHtml = p.image
      ? `<img src="${p.image}" alt="${p.name} — ${p.pack}" loading="lazy">`
      : `<div style="padding:14px;text-align:center;color:var(--muted);font-size:12px;">
          Photo coming soon
        </div>`;

    return `
      <article class="product">
        <div class="img">${imgHtml}</div>
        <div class="meta">
          <div class="title">
            <div>
              <h4>${p.name}</h4>
              <div class="sku">${p.id}</div>
            </div>
            <div class="price">${money(p.price)}</div>
          </div>

          <div class="specs">
            <span class="chip">${p.watt}W</span>
            <span class="chip">${p.pack}</span>
            <span class="chip">${p.lumens}</span>
          </div>

          <div class="small" style="margin-top:-2px;">
            ${p.notes}
          </div>

          <div class="row">
            <div class="stock">In stock: <b>${p.stock}</b> pack(s)</div>
            <div class="qty">
              <input type="number" min="1" max="${p.stock}" value="1" id="qty_${p.id}" />
              <button class="btn primary" type="button" onclick="addToCart('${p.id}')">Add</button>
            </div>
          </div>
        </div>
      </article>
    `;
  }

  function renderCatalog(){
    const p60 = products.filter(p=>p.watt===60);
    const p75 = products.filter(p=>p.watt===75);
    const p90 = products.filter(p=>p.watt===90);

    el("#grid60").innerHTML = p60.map(productCard).join("");
    el("#grid75").innerHTML = p75.map(productCard).join("");
    el("#grid90").innerHTML = p90.map(productCard).join("");
  }

  function renderCart(){
    const { lines, subtotal, ship, total, boxes } = calcTotals();

    el("#cartCount").textContent = `${boxes} pack(s) / box(es)`;
    el("#subTotal").textContent = money(subtotal);
    el("#shipTotal").textContent = money(ship);
    el("#grandTotal").textContent = money(total);

    if(lines.length === 0){
      el("#cartList").innerHTML = `<div class="small">Your cart is empty. Add items from the catalog.</div>`;
      return;
    }

    el("#cartList").innerHTML = lines.map(({product, qty}) => `
      <div class="cart-item">
        <div class="cart-top">
          <div>
            <b>${product.name}</b>
            <div class="mini">${product.id} • ${product.pack}</div>
          </div>
          <button class="btn danger" type="button" onclick="removeFromCart('${product.id}')">Remove</button>
        </div>
        <div class="row">
          <div class="small">Price: <b>${money(product.price)}</b></div>
          <div class="qty">
            <label class="small" style="margin-right:6px;">Qty</label>
            <input type="number" min="1" max="${product.stock}" value="${qty}"
              onchange="setQty('${product.id}', this.value)" />
          </div>
        </div>
      </div>
    `).join("");
  }

  // ---------------------------
  // Cart actions (inventory-limited)
  // ---------------------------
  window.addToCart = function(id){
    const p = products.find(x=>x.id===id);
    if(!p) return;
    const qtyInput = document.getElementById(`qty_${id}`);
    let qty = parseInt(qtyInput?.value || "1", 10);
    if(Number.isNaN(qty) || qty < 1) qty = 1;

    const existing = cart.get(id) || 0;
    const desired = Math.min(p.stock, existing + qty);
    cart.set(id, desired);

    renderCart();
  }

  window.removeFromCart = function(id){
    cart.delete(id);
    renderCart();
  }

  window.setQty = function(id, qtyVal){
    const p = products.find(x=>x.id===id);
    if(!p) return;
    let qty = parseInt(qtyVal, 10);
    if(Number.isNaN(qty) || qty < 1) qty = 1;
    qty = Math.min(p.stock, qty);
    cart.set(id, qty);
    renderCart();
  }

  // ---------------------------
  // Buttons
  // ---------------------------
  document.getElementById("btnClearCart").addEventListener("click", ()=>{
    cart.clear();
    renderCart();
  });

  document.getElementById("btnScrollCart").addEventListener("click", ()=>{
    document.getElementById("cartCard").scrollIntoView({behavior:"smooth", block:"start"});
  });

  // ---------------------------
  // Message Center spam protection
  // ---------------------------
  (function(){
    const form = document.getElementById("contactForm");
    const status = document.getElementById("formStatus");
    const sendBtn = document.getElementById("sendBtn");
    const startedAt = Date.now();

    form.addEventListener("submit", (e)=>{
      // Basic bot timing: if submitted in <2.5s, likely spam
      const tooFast = (Date.now() - startedAt) < 2500;
      const hpFilled = form.querySelector('input[name="bot-field"]')?.value?.trim()?.length > 0;

      if(tooFast || hpFilled){
        e.preventDefault();
        status.textContent = "Blocked as spam. If you’re a human, please wait a moment and try again.";
        status.style.color = "var(--bad)";
        return;
      }

      // Disable button to reduce double submits
      sendBtn.disabled = true;
      sendBtn.textContent = "Sending…";
      status.textContent = "Sending your message…";
      status.style.color = "var(--muted)";
    });
  })();

  // ---------------------------
  // PayPal Buttons
  // ---------------------------
  function initPayPal(){
    if(!window.paypal){
      console.warn("PayPal SDK not loaded (check your client-id).");
      return;
    }

    paypal.Buttons({
      style: { layout: "vertical" },

      onClick: function(data, actions){
        const { lines } = calcTotals();
        if(lines.length === 0){
          alert("Your cart is empty. Add items first.");
          return actions.reject();
        }
        return actions.resolve();
      },

      createOrder: function(data, actions){
        const { lines, subtotal, ship, total } = calcTotals();

        const purchase_units = [{
          description: "ClassicBulbs.com — Incandescent Bulb Packs",
          amount: {
            currency_code: "USD",
            value: total.toFixed(2),
            breakdown: {
              item_total: { currency_code: "USD", value: subtotal.toFixed(2) },
              shipping:   { currency_code: "USD", value: ship.toFixed(2) }
            }
          },
          items: lines.map(({product, qty}) => ({
            name: product.name,
            sku: product.id,
            unit_amount: { currency_code:"USD", value: product.price.toFixed(2) },
            quantity: String(qty),
            category: "PHYSICAL_GOODS"
          }))
        }];

        return actions.order.create({ purchase_units });
      },

      onApprove: function(data, actions){
        return actions.order.capture().then(function(details){
          // After successful capture, show confirmation.
          alert("Payment captured! Thank you. Order: " + details.id);
          cart.clear();
          renderCart();
        });
      },

      onError: function(err){
        console.error(err);
        alert("PayPal checkout error. Please try again or use the Message Center.");
      }
    }).render("#paypal-buttons");
  }

  // ---------------------------
  // Boot
  // ---------------------------
  renderCatalog();
  renderCart();
  initPayPal();
</script>
</body>
</html>
