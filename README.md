<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>DWOCK STORE</title>

<link href="https://fonts.googleapis.com/css2?family=Modak&display=swap" rel="stylesheet">

<style>

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Modak',cursive;
}

body{
  background:white;
  overflow-x:hidden;
}

/* NAV */
nav{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  padding:15px 6%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:rgba(255,255,255,.9);
  border-bottom:1px solid #eee;
  z-index:1000;
}

.logo{
  font-size:38px;
  color:#ff2d55;
}

nav a{
  margin-left:15px;
  font-size:16px;
  text-decoration:none;
  color:#111;
}

/* CART ICON */
.cart-icon{
  position:relative;
  cursor:pointer;
  font-size:20px;
}

.cart-count{
  position:absolute;
  top:-8px;
  right:-10px;
  background:red;
  color:white;
  font-size:12px;
  width:18px;
  height:18px;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
}

/* TOP BANNER */
.top-banner{
  position:fixed;
  top:70px;
  left:50%;
  transform:translateX(-50%);
  font-size:38px;
  color:#ff2d55;
  letter-spacing:3px;
  z-index:999;
  text-align:center;
  pointer-events:none;
  animation:bounceGlow 2.5s infinite;
}

.top-banner.small{
  font-size:20px;
  top:55px;
  opacity:.9;
}

@keyframes bounceGlow{
  0%,100%{transform:translateX(-50%) translateY(0);}
  50%{transform:translateX(-50%) translateY(-6px);}
}

/* HERO */
.hero{
  padding:140px 6% 40px;
  display:flex;
  justify-content:center;
}

.container{
  display:flex;
  flex-wrap:wrap;
  gap:40px;
  max-width:1100px;
  align-items:center;
}

.hero img{
  width:350px;
  border-radius:18px;
  cursor:pointer;
}

/* BUTTONS */
.btn{
  padding:12px 18px;
  border:none;
  border-radius:12px;
  cursor:pointer;
  font-size:18px;
}

.buy{background:#ff2d55;color:white;}
.cart{background:#19c37d;color:white;}

/* SIZE BUTTONS */
.sizes{
  display:flex;
  gap:10px;
  margin:10px 0;
}

.size-btn{
  padding:8px 14px;
  border:2px solid #111;
  border-radius:8px;
  cursor:pointer;
  background:white;
}

/* GALLERY */
.gallery{
  padding:60px 6%;
}

.gallery-title{
  text-align:center;
  font-size:42px;
  margin-bottom:30px;
}

.gallery-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
  gap:18px;
}

.card{
  background:white;
  padding:6px;
  border-radius:14px;
  box-shadow:0 10px 20px rgba(0,0,0,.1);
}

.card img{
  width:100%;
  border-radius:12px;
  cursor:pointer;
}

.card button{
  width:100%;
  margin-top:8px;
  padding:10px;
  border:none;
  border-radius:10px;
  background:#0BA3FF;
  color:white;
  cursor:pointer;
}

/* LIGHTBOX */
.lightbox{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.9);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:2000;
}

.lightbox img{
  max-width:90%;
  max-height:90%;
}

/* CART */
.cart-panel{
  position:fixed;
  top:0;
  right:-380px;
  width:320px;
  height:100%;
  background:white;
  box-shadow:-10px 0 30px rgba(0,0,0,.2);
  padding:20px;
  transition:.3s;
  z-index:3000;
}

.cart-panel.active{right:0;}

.item{
  display:flex;
  justify-content:space-between;
  margin:10px 0;
  border-bottom:1px solid #eee;
  padding-bottom:8px;
}

.total{
  margin-top:20px;
  font-size:22px;
}

.checkout{
  margin-top:15px;
  width:100%;
  padding:12px;
  background:#ff2d55;
  color:white;
  border:none;
  border-radius:10px;
}

</style>
</head>

<body>

<nav>
<div class="logo">DWOCK</div>

<div>
<a href="#">Home</a>
<a href="#">Shop</a>

<span class="cart-icon" onclick="toggleCart()">🛒
<span class="cart-count" id="count">0</span>
</span>

</div>
</nav>

<div class="top-banner" id="banner">
YOUR STYLE STARTS NOW!!!
</div>

<section class="hero">
<div class="container">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
onclick="openImg(this.src)">

<div>
<h1>DWOCK STREETWEAR</h1>
<p>$30</p>

<!-- SIZE BUTTONS ADDED -->
<div class="sizes">
<button class="size-btn">S</button>
<button class="size-btn">M</button>
<button class="size-btn">L</button>
</div>

<button class="btn buy" onclick="addToCart('Main Shirt',30)">BUY NOW</button>
<button class="btn cart" onclick="addToCart('Main Shirt',30)">ADD TO CART</button>
</div>

</div>
</section>

<section class="gallery">
<h2 class="gallery-title">LATEST DROPS</h2>

<div class="gallery-grid">

<div class="card"><img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png"><button onclick="addToCart('Drop 1',25)">Add</button></div>

<div class="card"><img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png"><button onclick="addToCart('Drop 2',25)">Add</button></div>

</div>
</section>

<div class="lightbox" id="lightbox" onclick="this.style.display='none'">
<img id="bigImg">
</div>

<div class="cart-panel" id="cartPanel">
<h2>Your Cart</h2>
<div id="cartItems"></div>
<div class="total" id="total">Total: $0</div>
<button class="checkout" onclick="checkout()">Checkout</button>
</div>

<script>

let cart=[];

function addToCart(name,price){
cart.push({name,price});
updateCart();
}

function updateCart(){
let box=document.getElementById("cartItems");
let count=document.getElementById("count");
let total=document.getElementById("total");

box.innerHTML="";
let sum=0;

cart.forEach(item=>{
sum+=item.price;
box.innerHTML+=`
<div class="item">
<span>${item.name}</span>
<span>$${item.price}</span>
</div>`;
});

count.innerText=cart.length;
total.innerText="Total: $"+sum;
}

function toggleCart(){
document.getElementById("cartPanel").classList.toggle("active");
}

function openImg(src){
document.getElementById("bigImg").src=src;
document.getElementById("lightbox").style.display="flex";
}

window.addEventListener("scroll",()=>{
const b=document.getElementById("banner");
if(window.scrollY>80){
b.classList.add("small");
}
});

function checkout(){
alert("Checkout coming soon 🔥");
}

</script>

</body>
</html>
