!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>The Local Shop</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{--bg:#fafaf7;--card:#fff;--ink:#1c1c1c;--muted:#6b6b6b;--accent:#e8590c;--line:#eaeaea}
@media(prefers-color-scheme:dark){:root{--bg:#121212;--card:#1d1d1d;--ink:#f2f2f2;--muted:#a0a0a0;--line:#2c2c2c}}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'Poppins',system-ui,sans-serif;background:var(--bg);color:var(--ink);line-height:1.5}
.hero{min-height:92vh;display:flex;align-items:center;justify-content:center;text-align:center;padding:24px;color:#fff;
background:linear-gradient(rgba(0,0,0,.5),rgba(0,0,0,.55)),url('https://i.ibb.co/pjSnysMw/taylor-kopel-Dk-H2-X5-Nz-Hnc-unsplash.jpg') center/cover #333}
.hero h1{font-size:clamp(2.2rem,8vw,4.5rem);line-height:1.1;font-weight:700;text-transform:capitalize}
.hero p{margin:14px 0 28px;font-size:clamp(1rem,3.5vw,1.4rem);opacity:.92}
.btn{display:inline-block;border:0;cursor:pointer;background:var(--accent);color:#fff;font:600 1rem 'Poppins',sans-serif;padding:13px 30px;border-radius:50px;text-decoration:none;transition:transform .15s}
.btn:hover{transform:translateY(-2px)}
section{padding:56px 16px;max-width:1100px;margin:auto}
h2{text-align:center;font-size:1.8rem;margin-bottom:28px}
.carousel{position:relative}
.track{display:flex;gap:18px;overflow-x:auto;scroll-snap-type:x mandatory;padding:6px 4px 16px;scrollbar-width:thin}
.card{flex:0 0 min(86%,340px);scroll-snap-align:center;background:var(--card);border:1px solid var(--line);border-radius:18px;overflow:hidden;box-shadow:0 6px 22px rgba(0,0,0,.07);margin:0 auto}
.track.single{justify-content:center}
.card img{width:100%;aspect-ratio:1;object-fit:cover;display:block;background:#eee}
.card .body{padding:16px}
.card h3{font-size:1.05rem;font-weight:600}
.price{color:var(--accent);font-weight:700;font-size:1.25rem;margin:4px 0 12px}
.card .btn{width:100%;padding:12px}
.link{background:none;border:0;color:var(--muted);font:500 .85rem 'Poppins';cursor:pointer;text-decoration:underline;margin-bottom:10px}
.nav{position:absolute;top:40%;width:40px;height:40px;border-radius:50%;border:0;background:var(--card);color:var(--ink);box-shadow:0 2px 10px rgba(0,0,0,.25);font-size:1.3rem;cursor:pointer}
.nav.l{left:-4px}.nav.r{right:-4px}
.details{max-width:700px;margin:auto;background:var(--card);border:1px solid var(--line);border-radius:18px;padding:22px}
.details h3{margin-bottom:10px}
.details ul{padding-left:18px;color:var(--muted);font-size:.92rem}
.details li{margin:5px 0}.details b{color:var(--ink)}
footer{text-align:center;padding:30px 16px 90px;color:var(--muted);font-size:.9rem;border-top:1px solid var(--line)}
.wa{position:fixed;right:18px;bottom:18px;width:58px;height:58px;border-radius:50%;background:#25d366;display:grid;place-items:center;box-shadow:0 4px 16px rgba(0,0,0,.35);z-index:50}
.wa svg{width:32px;height:32px;fill:#fff}
.modal{position:fixed;inset:0;background:rgba(0,0,0,.6);display:none;align-items:center;justify-content:center;padding:16px;z-index:100}
.modal.open{display:flex}
.box{background:var(--card);width:100%;max-width:440px;max-height:92vh;overflow:auto;border-radius:18px;padding:22px}
.box h3{margin-bottom:4px}
.sum{font-size:.9rem;color:var(--muted);margin-bottom:14px}
label{display:block;font-size:.82rem;font-weight:500;margin:10px 0 4px}
input,textarea{width:100%;padding:11px 12px;border:1px solid var(--line);border-radius:10px;background:var(--bg);color:var(--ink);font:inherit}
.phone{display:flex;align-items:center;border:1px solid var(--line);border-radius:10px;background:var(--bg)}
.phone span{padding:0 10px 0 12px;font-weight:600}
.phone input{border:0;background:none}
.qty{width:90px}
.row{display:flex;gap:10px;margin-top:18px}
.row .btn{flex:1;padding:12px}
.ghost{background:var(--line);color:var(--ink)}
#msg{margin-top:12px;font-size:.9rem;text-align:center;min-height:1.2em}
</style>
</head>
<body>

<header class="hero">
  <div>
    <h1>The Local Shop</h1>
    <p>Fresh Finds, Starting Rs 1299</p>
    <a href="#products" class="btn">Shop Now</a>
  </div>
</header>

<section id="products">
  <h2>Our Products</h2>
  <div class="carousel">
    <button class="nav l" aria-label="Previous" onclick="slide(-1)">‹</button>
    <div class="track" id="track"></div>
    <button class="nav r" aria-label="Next" onclick="slide(1)">›</button>
  </div>
</section>

<section id="details">
  <div class="details">
    <h3>M10 Wireless Earbuds With Digital Display</h3>
    <ul>
      <li><b>Material:</b> Plastic</li>
      <li><b>Connectivity:</b> Bluetooth 5.2</li>
      <li><b>Features:</b> Long-lasting battery with fast charge, super bass, clear voice, compatible with all Android devices, advanced &amp; active noise cancellation</li>
      <li><b>Color:</b> Black</li>
      <li><b>Package Includes:</b> 1 x Earbuds</li>
      <li><b>Battery:</b> 500 mAh &nbsp;|&nbsp; <b>Call Time:</b> 95 hrs &nbsp;|&nbsp; <b>Standby:</b> 48 hrs</li>
      <li><b>Voltage / Watts:</b> 2 A / 2 W</li>
      <li><b>Weight:</b> 120 g &nbsp;|&nbsp; <b>Size:</b> 4 × 4 × 2 inches</li>
      <li>Clear sound with deep bass, compact charging case, perfect for daily use, calls, music and workouts.</li>
      <li><i>Note: Follow the user manual for proper usage and safety.</i></li>
      <li><b>Product Code:</b> MZ2134200138TETDAA</li>
    </ul>
  </div>
</section>

<footer>© <span id="yr"></span> The Local Shop · mrfaizanbossuktt@gmail.com · 0333-4127070</footer>

<a class="wa" href="https://wa.me/923334127070" target="_blank" rel="noopener" aria-label="Chat on WhatsApp">
  <svg viewBox="0 0 32 32"><path d="M16 3C9 3 3.4 8.6 3.4 15.5c0 2.3.6 4.4 1.7 6.3L3 29l7.4-2c1.8 1 3.800 1.500 5.600 1.500 7 0 12.600-5.600 12.600-12.500S23 3 16 3zm0 22.800c-1.800 0-3.500-.5-5-1.400l-.4-.2-4.400 1.200 1.200-4.300-.3-.4a10.200 10.200 0 0 1-1.600-5.500C5.500 9.900 10.200 5.300 16 5.300s10.500 4.600 10.500 10.300S21.800 25.800 16 25.800zm5.800-7.600c-.3-.2-1.900-.9-2.200-1s-.5-.2-.7.200-.8 1-1 1.200-.4.200-.7.100a8.500 8.500 0 0 1-4.200-3.700c-.3-.6.300-.5.900-1.700.1-.2 0-.4 0-.5l-1-2.300c-.2-.6-.5-.5-.7-.5h-.6c-.2 0-.6.100-.9.400s-1.100 1.100-1.100 2.600 1.100 3 1.300 3.200c.2.200 2.200 3.400 5.300 4.700 2 .8 2.700.9 3.700.7.600-.1 1.900-.8 2.100-1.500.3-.7.300-1.400.2-1.500l-.5-.4z"/></svg>
</a>

<div class="modal" id="modal">
  <div class="box">
    <h3>Send Order</h3>
    <p class="sum" id="sum"></p>
    <label>Quantity</label>
    <input class="qty" id="qty" type="number" min="1" max="20" value="1">
    <label>Full Name</label>
    <input id="name" autocomplete="name" placeholder="Your name">
    <label>Phone (Pakistan)</label>
    <div class="phone"><span>+92</span><input id="phone" type="tel" inputmode="numeric" maxlength="10" placeholder="3XXXXXXXXX"></div>
    <label>Email</label>
    <input id="email" type="email" autocomplete="email" placeholder="you@example.com">
    <label>Delivery Address</label>
    <textarea id="address" rows="3" placeholder="House, street, city"></textarea>
    <div class="row">
      <button class="btn ghost" onclick="closeModal()">Cancel</button>
      <button class="btn" id="send" onclick="sendOrder()">Send Order</button>
    </div>
    <div id="msg"></div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4.4.1/dist/email.min.js"></script>
<script>
/* ===== EMAILJS SETUP (free at emailjs.com) =====
   1. Create account → add an Email Service (Gmail) → copy SERVICE_ID
   2. Create a template. Set "To Email" to {{to_email}} and use variables:
      {{customer_name}} {{phone}} {{customer_email}} {{address}} {{items}} {{total}}
   3. Copy TEMPLATE_ID and your Public Key (Account → API Keys) */
const EMAILJS = { PUBLIC_KEY:"YOUR_PUBLIC_KEY", SERVICE_ID:"YOUR_SERVICE_ID", TEMPLATE_ID:"YOUR_TEMPLATE_ID" };
const OWNER_EMAIL = "mrfaizanbossuktt@gmail.com";

/* Add more products here — they appear in the carousel automatically */
const PRODUCTS = [
  { id:1, name:"M10 Wireless Earbuds With Digital Display", price:1299,
    image:"https://i.ibb.co/1Gt0Qw8C/file-000000000cd482119a8b2888c1ea8ee5.png" }
];

const $ = id => document.getElementById(id);
const track = $("track");
let current = null;

if (!window.emailjs || EMAILJS.PUBLIC_KEY.startsWith("YOUR")) console.warn("EmailJS keys not set yet.");
else emailjs.init({ publicKey: EMAILJS.PUBLIC_KEY });

PRODUCTS.forEach(p => {
  const d = document.createElement("div");
  d.className = "card";
  d.innerHTML = `<img src="${p.image}" alt="${p.name}" loading="lazy">
    <div class="body"><h3>${p.name}</h3><div class="price">Rs ${p.price.toLocaleString()}</div>
    <button class="btn" onclick="openModal(${p.id})">Send Order</button></div>`;
  track.appendChild(d);
});
if (PRODUCTS.length < 2) { track.classList.add("single"); document.querySelectorAll(".nav").forEach(n => n.style.display="none"); }
$("yr").textContent = new Date().getFullYear();

function slide(dir){
  const w = track.querySelector(".card").offsetWidth + 18;
  if (dir > 0 && track.scrollLeft + track.clientWidth >= track.scrollWidth - 10) track.scrollTo({left:0,behavior:"smooth"});
  else track.scrollBy({left:dir*w,behavior:"smooth"});
}
let auto = PRODUCTS.length > 1 ? setInterval(() => slide(1), 3500) : null;
["touchstart","mouseenter"].forEach(e => track.addEventListener(e, () => clearInterval(auto)));

function openModal(id){
  current = PRODUCTS.find(p => p.id === id);
  $("sum").textContent = `${current.name} — Rs ${current.price.toLocaleString()}`;
  $("msg").textContent = ""; $("modal").classList.add("open");
}
function closeModal(){ $("modal").classList.remove("open"); }
$("modal").addEventListener("click", e => { if (e.target.id === "modal") closeModal(); });
$("phone").addEventListener("input", e => { e.target.value = e.target.value.replace(/\D/g,"").replace(/^0+/,""); });

function say(t, ok){ const m=$("msg"); m.textContent=t; m.style.color = ok ? "#1a9d4a" : "#d33"; }

async function sendOrder(){
  const name=$("name").value.trim(), phone=$("phone").value.trim(),
        email=$("email").value.trim(), address=$("address").value.trim(),
        qty=Math.max(1, parseInt($("qty").value)||1);
  if (!name) return say("Please enter your name.");
  if (!/^3\d{9}$/.test(phone)) return say("Enter a valid Pakistani number: +92 followed by 10 digits (3XXXXXXXXX).");
  if (!/^\S+@\S+\.\S+$/.test(email)) return say("Please enter a valid email.");
  if (address.length < 8) return say("Please enter your full address.");
  if (EMAILJS.PUBLIC_KEY.startsWith("YOUR")) return say("Shop owner: add your EmailJS keys in the code first.");

  const btn=$("send"); btn.disabled=true; btn.textContent="Sending…";
  try{
    await emailjs.send(EMAILJS.SERVICE_ID, EMAILJS.TEMPLATE_ID, {
      to_email: OWNER_EMAIL,
      customer_name: name,
      phone: "+92" + phone,
      customer_email: email,
      address: address,
      items: `${current.name} x ${qty} @ Rs ${current.price}`,
      total: "Rs " + (current.price * qty).toLocaleString()
    });
    say("✅ Order sent! We will contact you soon.", true);
    ["name","phone","email","address"].forEach(i => $(i).value="");
    setTimeout(closeModal, 2500);
  }catch(err){
    console.error(err); say("Could not send order. Please try WhatsApp instead.");
  }
  btn.disabled=false; btn.textContent="Send Order";
}
</script>
</body>
</html>
