<!DOCTYPE html>
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
  top:78px;
  left:50%;
  transform:translateX(-50%);
  font-size:28px;
  color:#ff2d55;
  z-index:999;
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
  align-items:center;
  justify-content:center;
  max-width:1100px;
}

/* MAIN IMAGE */
.hero img{
  width:340px;
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
  margin-top:10px;
}

.buy{background:#ff2d55;color:white;}
.cart{background:#19c37d;color:white;}

/* IMAGE BUTTONS */
.img-buttons{
  display:flex;
  flex-wrap:wrap;
  gap:8px;
  margin-top:15px;
}

.img-btn{
  padding:8px 12px;
  border:none;
  border-radius:8px;
  background:#0BA3FF;
  color:white;
  cursor:pointer;
  font-size:13px;
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

.cart-panel.active{
  right:0;
}

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
  cursor:pointer;
}

.close-cart{
  background:#111;
  color:white;
  border:none;
  padding:8px;
  border-radius:8px;
  cursor:pointer;
  margin-bottom:10px;
}

</style>
</head>

<body>

<!-- NAV -->
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

<!-- BANNER -->
<div class="top-banner">YOUR STYLE STARTS NOW!!!</div>

<!-- HERO -->
<section class="hero">
<div class="container">

<img id="mainImage"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
onclick="openImg(this.src)">

<div>
<h1>DWOCK STREETWEAR</h1>
<p>$30</p>

<div class="img-buttons">

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png')">IMG 1</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png')">IMG 2</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png')">IMG 3</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png')">IMG 4</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png')">IMG 6</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2449.png')">IMG 7</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png')">IMG 8</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png')">IMG 9</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png')">IMG 10</button>

<!-- NEW IMAGE (replaces removed one) -->
<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/fc86785c18195f59c1d7d29ceb4ae2c9e74d062e/22c3e4d4-1a52-479a-9fcb-2de86f1bf029.png')">IMG 11</button>

</div>

<button class="btn buy" onclick="addToCart('Main Shirt',30)">BUY NOW</button>
<button class="btn cart" onclick="addToCart('Main Shirt',30)">ADD TO CART</button>

</div>

</div>
</section>

<!-- GALLERY -->
<section class="gallery">
<h2 class="gallery-title">LATEST DROPS</h2>

<div class="gallery-grid">

<div class="card"><img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png" onclick="openImg(this.src)"><button onclick="addToCart('Drop 1',25)">Add</button></div>

<div class="card"><img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png" onclick="openImg(this.src)"><button onclick="addToCart('Drop 2',25)">Add</button></div>

<div class="card"><img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png" onclick="openImg(this.src)"><button onclick="addToCart('Drop 3',25)">Add</button></div>

</div>
</section>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox" onclick="this.style.display='none'">
<img id="bigImg">
</div>

<!-- CART -->
<div class="cart-panel" id="cartPanel">
<button class="close-cart" onclick="toggleCart()">Close</button>

<h2>Your Cart</h2>
<div id="cartItems"></div>
<div class="total" id="total">Total: $0</div>

<button class="checkout" onclick="checkout()">Checkout</button>
</div>

<script>

let cart = [];

function changeImg(btn,src){
document.getElementById("mainImage").src = src;
document.querySelectorAll(".img-btn").forEach(b=>b.style.opacity="0.6");
btn.style.opacity="1";
}

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

cart.forEach(i=>{
sum+=i.price;
box.innerHTML+=`<div class="item"><span>${i.name}</span><span>$${i.price}</span></div>`;
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

function checkout(){
alert("Checkout coming soon 🔥");
}

</script>

</body>
</html>
