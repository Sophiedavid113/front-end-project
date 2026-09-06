<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Coffee House</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --cream:#eee7d7;--brown:#2e2118;--dark:#211811;--gold:#caa24b;
  --white:#fff;--muted:#74685e;
}
body{font-family:Arial,Helvetica,sans-serif;background:var(--cream);color:var(--brown);line-height:1.5}
a{text-decoration:none;color:inherit}
.container{width:min(1180px,92%);margin:auto}

/* NAVBAR */
header{background:#f4eee2;position:sticky;top:0;z-index:20;box-shadow:0 2px 12px #00000012}
.nav{height:76px;display:flex;align-items:center;justify-content:space-between}
.logo{font-family:Georgia,serif;font-size:25px;font-weight:700}
.nav-links{display:flex;gap:30px;font-size:14px;font-weight:600}
.nav-links a:hover{color:#9c7130}
.nav-icons{display:flex;gap:15px;align-items:center}
.icon-btn{border:0;background:transparent;font-size:21px;cursor:pointer}
.menu-btn{display:none}

/* HERO */
.hero{min-height:470px;display:flex;align-items:center;background:
linear-gradient(90deg,#101820cc 0%,#10182088 45%,#10182022 100%),
url("https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?auto=format&fit=crop&w=1600&q=85") center/cover}
.hero-content{color:white;max-width:520px;padding:65px 0}
.eyebrow{font-size:13px;letter-spacing:3px;text-transform:uppercase;margin-bottom:12px;color:#e6d6b7}
.hero h1{font-family:Georgia,serif;font-size:56px;line-height:1.05;margin-bottom:20px}
.hero p{font-size:17px;color:#eee;max-width:440px;margin-bottom:27px}
.btn{display:inline-block;border:0;background:var(--dark);color:white;padding:13px 25px;border-radius:25px;font-weight:700;cursor:pointer;transition:.25s}
.btn:hover{transform:translateY(-2px);background:#493327}
.btn.light{background:white;color:var(--brown)}

/* FEATURES */
.features{background:#e7dfce;padding:24px 0}
.feature-row{display:grid;grid-template-columns:repeat(4,1fr);gap:15px;text-align:center}
.feature{padding:10px}
.feature .ficon{font-size:28px;margin-bottom:4px}
.feature strong{display:block;font-size:14px}
.feature span{font-size:12px;color:var(--muted)}

/* PRODUCTS */
.section{padding:62px 0}
.section-title{text-align:center;margin-bottom:32px}
.section-title h2{font-family:Georgia,serif;font-size:30px}
.section-title p{font-size:13px;color:var(--muted);margin-top:5px}
.products{display:grid;grid-template-columns:repeat(4,1fr);gap:22px}
.card{background:#fff;padding:11px;border-radius:5px;box-shadow:0 5px 18px #0000000b;position:relative}
.card img{width:100%;height:190px;object-fit:cover;border-radius:3px;display:block}
.card-body{padding:13px 5px 6px}
.card h3{font-family:Georgia,serif;font-size:16px;margin-bottom:4px}
.card p{font-size:12px;color:var(--muted);height:37px;overflow:hidden}
.price-row{display:flex;justify-content:space-between;align-items:center;margin-top:11px}
.price{font-weight:700}
.buy{border:0;background:#2d2119;color:white;padding:7px 13px;border-radius:4px;font-size:11px;cursor:pointer}
.buy:hover{background:#8b612d}
.badge{position:absolute;top:18px;left:18px;background:white;padding:4px 8px;font-size:10px;border-radius:15px}

/* PROMO */
.promo{background:#e8decb;overflow:hidden}
.promo-inner{min-height:170px;display:flex;align-items:center;justify-content:center;text-align:center;position:relative}
.promo-copy{z-index:2}
.promo h2{font-family:Georgia,serif;font-size:31px}
.promo p{font-size:14px;color:#6d5f52;margin:5px 0 15px}
.beans{position:absolute;font-size:80px;opacity:.15}
.beans.left{left:0}.beans.right{right:0}

/* TESTIMONIALS */
.testimonials{background:#fff}
.reviews{display:grid;grid-template-columns:repeat(3,1fr);gap:25px}
.review{padding:25px;border:1px solid #eee;text-align:left;border-radius:5px}
.stars{color:#d59d2c;letter-spacing:2px;margin-bottom:10px}
.review-top{display:flex;gap:12px;align-items:center;margin-bottom:10px}
.avatar{width:42px;height:42px;border-radius:50%;object-fit:cover}
.review h4{font-size:14px}.review small{color:#888}
.review p{font-size:13px;color:#6c625b}
.dots{text-align:center;margin-top:25px;letter-spacing:5px}

/* NEWSLETTER */
.newsletter{padding:65px 0;background:#e9dfcd;text-align:center;position:relative;overflow:hidden}
.newsletter h2{font-family:Georgia,serif;font-size:29px}
.newsletter p{color:#716458;margin:5px 0 18px}
.form{display:flex;justify-content:center;max-width:530px;margin:auto}
.form input{flex:1;border:1px solid #d1c5b1;padding:13px 17px;border-radius:24px 0 0 24px;outline:none}
.form button{border-radius:0 24px 24px 0}

/* FOOTER */
footer{background:#291e17;color:#ddd;padding:45px 0 20px}
.footer-grid{display:grid;grid-template-columns:1.5fr repeat(4,1fr);gap:35px}
.footer-brand h2{font-family:Georgia,serif;color:#fff;margin-bottom:8px}
.footer-brand p{font-size:12px;color:#aaa;max-width:220px}
footer h4{color:#fff;margin-bottom:13px;font-size:13px}
footer ul{list-style:none}
footer li{font-size:12px;color:#aaa;margin:7px 0}
.social{display:flex;gap:9px;margin-top:14px}
.social a{width:30px;height:30px;border:1px solid #66574d;border-radius:50%;display:grid;place-items:center;font-size:12px}
.copyright{border-top:1px solid #473a32;margin-top:30px;padding-top:15px;text-align:center;color:#888;font-size:11px}

/* CART */
.cart{position:fixed;right:20px;bottom:20px;background:#2e2118;color:#fff;border:0;border-radius:50%;width:58px;height:58px;font-size:22px;cursor:pointer;box-shadow:0 5px 20px #0004;z-index:30}
.cart span{position:absolute;right:-2px;top:-2px;background:#c68d30;border-radius:50%;font-size:10px;width:19px;height:19px;display:grid;place-items:center}
.toast{position:fixed;left:50%;bottom:28px;transform:translate(-50%,100px);background:#2e2118;color:#fff;padding:12px 20px;border-radius:25px;font-size:13px;transition:.3s;z-index:40}
.toast.show{transform:translate(-50%,0)}

/* RESPONSIVE */
@media(max-width:850px){
 .nav-links{display:none}.menu-btn{display:block}
 .hero h1{font-size:43px}.hero{min-height:430px}
 .products{grid-template-columns:repeat(2,1fr)}
 .reviews{grid-template-columns:1fr}
 .footer-grid{grid-template-columns:repeat(2,1fr)}
}
@media(max-width:520px){
 .nav{height:65px}.logo{font-size:21px}
 .feature-row{grid-template-columns:repeat(2,1fr)}
 .hero h1{font-size:37px}.hero p{font-size:14px}
 .products{grid-template-columns:1fr}
 .card img{height:230px}
 .footer-grid{grid-template-columns:1fr 1fr}
 .promo h2,.newsletter h2{font-size:25px}
 .form{padding:0 15px}
}
</style>
</head>
<body>

<header>
  <div class="container nav">
    <a class="logo" href="#">COFFEE</a>
    <nav class="nav-links">
      <a href="#home">Home</a><a href="#shop">Shop</a><a href="#about">About</a>
      <a href="#reviews">Reviews</a><a href="#contact">Contact</a>
    </nav>
    <div class="nav-icons">
      <button class="icon-btn" aria-label="Search" onclick="searchProducts()">⌕</button>
      <button class="icon-btn menu-btn" onclick="toggleMenu()">☰</button>
      <button class="icon-btn" aria-label="Cart" onclick="showCart()">🛒</button>
    </div>
  </div>
</header>

<main>
<section class="hero" id="home">
 <div class="container">
  <div class="hero-content">
   <div class="eyebrow">Freshly roasted coffee</div>
   <h1>We serve the richest coffee in town!</h1>
   <p>Discover carefully selected beans, delicious drinks and the perfect coffee experience made for every coffee lover.</p>
   <a href="#shop" class="btn light">Shop Now</a>
  </div>
 </div>
</section>

<section class="features">
 <div class="container feature-row">
  <div class="feature"><div class="ficon">☕</div><strong>Fresh Coffee</strong><span>Roasted with care</span></div>
  <div class="feature"><div class="ficon">♨</div><strong>Premium Quality</strong><span>Best ingredients</span></div>
  <div class="feature"><div class="ficon">🥤</div><strong>Perfect Taste</strong><span>Made fresh daily</span></div>
  <div class="feature"><div class="ficon">♛</div><strong>Best Service</strong><span>For every customer</span></div>
 </div>
</section>

<section class="section" id="shop">
 <div class="container">
  <div class="section-title"><h2>Our Special Coffee</h2><p>Choose your favorite coffee from our special collection</p></div>
  <div class="products" id="coffeeProducts"></div>
  <div class="section-title" style="margin-top:60px"><h2>Our Special Dessert</h2><p>Sweet treats that go perfectly with coffee</p></div>
  <div class="products" id="dessertProducts"></div>
 </div>
</section>

<section class="promo">
 <div class="container promo-inner">
  <div class="beans left">☕ ☕</div>
  <div class="promo-copy"><h2>Check out our best coffee beans</h2><p>Rich aroma, smooth flavor and freshly roasted beans.</p><a href="#shop" class="btn">Explore Now</a></div>
  <div class="beans right">☕ ☕</div>
 </div>
</section>

<section class="section testimonials" id="reviews">
 <div class="container">
  <div class="section-title"><h2>What People Say</h2><p>Real words from our happy customers</p></div>
  <div class="reviews">
   <article class="review"><div class="review-top"><img class="avatar" src="https://i.pravatar.cc/100?img=47"><div><h4>Sarah Williams</h4><small>Verified customer</small></div></div><div class="stars">★★★★★</div><p>“Amazing coffee and a beautiful atmosphere. The taste is rich and fresh. I will definitely order again.”</p></article>
   <article class="review"><div class="review-top"><img class="avatar" src="https://i.pravatar.cc/100?img=12"><div><h4>John Smith</h4><small>Verified customer</small></div></div><div class="stars">★★★★★</div><p>“The cappuccino was perfect and the delivery was quick. One of my favorite coffee shops.”</p></article>
   <article class="review"><div class="review-top"><img class="avatar" src="https://i.pravatar.cc/100?img=32"><div><h4>Emma Brown</h4><small>Verified customer</small></div></div><div class="stars">★★★★★</div><p>“Great quality beans and excellent service. The desserts are also delicious!”</p></article>
  </div>
  <div class="dots">• • •</div>
 </div>
</section>

<section class="newsletter" id="contact">
 <div class="container">
  <h2>Join our coffee club</h2>
  <p>Get new offers, coffee tips and special discounts in your inbox.</p>
  <form class="form" onsubmit="subscribe(event)">
   <input id="email" type="email" placeholder="Enter your email address" required>
   <button class="btn" type="submit">Subscribe</button>
  </form>
 </div>
</section>
</main>

<footer id="about">
 <div class="container">
  <div class="footer-grid">
   <div class="footer-brand"><h2>COFFEE</h2><p>Fresh coffee, delicious desserts and a warm place for every coffee lover.</p><div class="social"><a href="#">f</a><a href="#">◎</a><a href="#">𝕏</a><a href="#">▶</a></div></div>
   <div><h4>Company</h4><ul><li><a href="#about">About us</a></li><li>Our story</li><li>Careers</li><li>Blog</li></ul></div>
   <div><h4>Shop</h4><ul><li><a href="#shop">Coffee</a></li><li><a href="#shop">Desserts</a></li><li>Gift cards</li><li>Special offers</li></ul></div>
   <div><h4>Support</h4><ul><li>Contact us</li><li>Shipping</li><li>Returns</li><li>FAQ</li></ul></div>
   <div><h4>Contact</h4><ul><li>hello@coffee.com</li><li>+92 300 1234567</li><li>Mon - Sat</li><li>9:00 AM - 8:00 PM</li></ul></div>
  </div>
  <div class="copyright">© 2026 Coffee House. All rights reserved.</div>
 </div>
</footer>

<button class="cart" onclick="showCart()" aria-label="Shopping cart">🛒<span id="cartCount">0</span></button>
<div class="toast" id="toast"></div>

<script>
const coffee = [
 {name:"Cappuccino",price:"Rs. 450",img:"https://images.unsplash.com/photo-1572442388796-11668a67e53d?auto=format&fit=crop&w=700&q=80"},
 {name:"Caffe Latte",price:"Rs. 480",img:"https://images.unsplash.com/photo-1541167760496-1628856ab772?auto=format&fit=crop&w=700&q=80"},
 {name:"Iced Coffee",price:"Rs. 520",img:"https://images.unsplash.com/photo-1517701604599-bb29b565090c?auto=format&fit=crop&w=700&q=80"},
 {name:"Caramel Macchiato",price:"Rs. 550",img:"https://images.unsplash.com/photo-1485808191679-5f86510681a2?auto=format&fit=crop&w=700&q=80"}
];
const desserts = [
 {name:"Chocolate Cake",price:"Rs. 650",img:"https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&w=700&q=80"},
 {name:"Cream Dessert",price:"Rs. 590",img:"https://images.unsplash.com/photo-1551024506-0bccd828d307?auto=format&fit=crop&w=700&q=80"},
 {name:"Croissant",price:"Rs. 380",img:"https://images.unsplash.com/photo-1555507036-ab1f4038808a?auto=format&fit=crop&w=700&q=80"},
 {name:"Cookies",price:"Rs. 420",img:"https://images.unsplash.com/photo-1499636136210-6f4ee915583e?auto=format&fit=crop&w=700&q=80"}
];
let cartCount=0;

function renderProducts(items,id){
 const el=document.getElementById(id);
 el.innerHTML=items.map((p,i)=>`
  <article class="card">
   ${i===0?'<span class="badge">POPULAR</span>':''}
   <img src="${p.img}" alt="${p.name}" loading="lazy">
   <div class="card-body">
    <h3>${p.name}</h3><p>Freshly prepared with premium ingredients for a wonderful taste.</p>
    <div class="price-row"><span class="price">${p.price}</span><button class="buy" onclick="addToCart('${p.name}')">Add to cart</button></div>
   </div>
  </article>`).join("");
}
renderProducts(coffee,"coffeeProducts");
renderProducts(desserts,"dessertProducts");

function addToCart(name){
 cartCount++;
 document.getElementById("cartCount").textContent=cartCount;
 showToast(name+" added to cart ✓");
}
function showToast(msg){
 const t=document.getElementById("toast");t.textContent=msg;t.classList.add("show");
 setTimeout(()=>t.classList.remove("show"),2200);
}
function showCart(){showToast(cartCount?`You have ${cartCount} item(s) in your cart.`:"Your cart is empty.");}
function subscribe(e){
 e.preventDefault();
 const email=document.getElementById("email").value;
 showToast("Thanks! "+email+" has been subscribed.");
 e.target.reset();
}
function searchProducts(){
 const q=prompt("Search for coffee or dessert:");
 if(q){
  const all=[...coffee,...desserts].filter(x=>x.name.toLowerCase().includes(q.toLowerCase()));
  if(all.length){document.getElementById("shop").scrollIntoView({behavior:"smooth"});showToast(all.length+" item(s) found.");}
  else showToast("No matching item found.");
 }
}
function toggleMenu(){
 const nav=document.querySelector(".nav-links");
 const visible=nav.style.display==="flex";
 nav.style.display=visible?"none":"flex";
 if(!visible){nav.style.position="absolute";nav.style.top="65px";nav.style.left="0";nav.style.right="0";nav.style.background="#f4eee2";nav.style.padding="20px";nav.style.flexDirection="column";nav.style.gap="15px";}
}
</script>
</body>
</html>
