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

/* BANNER */
.top-banner{
  position:fixed;
  top:110px;
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
  font-size:22px;
  top:85px;
}

@keyframes bounceGlow{
  0%,100%{transform:translateX(-50%) translateY(0);}
  50%{transform:translateX(-50%) translateY(-6px);}
}

/* HERO */
.hero{
  padding:180px 6% 40px;
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
  margin-top:10px;
}

.buy{background:#ff2d55;color:white;}
.cart{background:#19c37d;color:white;}

/* SIZE */
.sizes{
  display:flex;
  gap:10px;
  margin:10px 0;
}

.size-btn{
  padding:8px 14px;
  border-radius:10px;
  border:2px solid #111;
  cursor:pointer;
  background:white;
}

.size-btn.active{
  background:#111;
  color:white;
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
.cart-backdrop{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.5);
  opacity:0;
  pointer-events:none;
  transition:.3s;
  z-index:2500;
}

.cart-backdrop.active{
  opacity:1;
  pointer-events:auto;
}

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

.close-cart{
  position:absolute;
  top:10px;
  right:10px;
  width:35px;
  height:35px;
  border:none;
  border-radius:50%;
  background:#ff2d55;
  color:white;
  cursor:pointer;
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
</style>
</head>

<body>

<nav>
<div class="logo">DWOCK</div>
<div>
<a href="#">Home</a>
<a href="#">Shop</a>
<span class="cart-icon" onclick="toggleCart()">🛒 <span class="cart-count" id="count">0</span></span>
</div>
</nav>

<div class="top-banner" id="banner">YOUR STYLE STARTS NOW!!!</div>

<section class="hero">
<div class="container">

<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png" onclick="openImg(this.src)">

<div>
<h1>DWOCK STREETWEAR</h1>
<p>$30</p>

<div class="sizes">
<button class="size-btn" onclick="setSize(this,'S')">S</button>
<button class="size-btn" onclick="setSize(this,'M')">M</button>
<button class="size-btn" onclick="setSize(this,'L')">L</button>
</div>

<button class="btn buy" onclick="addToCart('Main Shirt',30)">BUY NOW</button>
<button class="btn cart" onclick="addToCart('Main Shirt',30)">ADD TO CART</button>
</div>

</div>
</section>

<section class="gallery">
<h2 class="gallery-title">LATEST DROPS</h2>

<div class="gallery-grid">

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 1',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 2',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 3',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 4',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 5',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2449.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 6',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 7',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 8',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 9',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0591%20(1).jpeg" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 10',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0594.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 11',25)">Add</button>
</div>

<div class="card">
<img src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/22c3e4d4-1a52-479a-9fcb-2de86f1bf029.png" onclick="openImg(this.src)">
<button onclick="addToCart('Drop 12',25)">Add</button>
</div>

</div>
</section>

<div class="lightbox" id="lightbox" onclick="this.style.display='none'">
<img id="bigImg">
</div>

<div class="cart-backdrop" id="cartBackdrop" onclick="toggleCart()"></div>

<div class="cart-panel" id="cartPanel">
<button class="close-cart" onclick="toggleCart()">✖</button>
<h2>Your Cart</h2>
<div id="cartItems"></div>
<div class="total" id="total">Total: $0</div>
<button class="checkout" onclick="checkout()">Checkout</button>
</div>

<script>
let cart=[];
let selectedSize="M";

function setSize(btn,size){
selectedSize=size;
document.querySelectorAll(".size-btn").forEach(b=>b.classList.remove("active"));
btn.classList.add("active");
}

function addToCart(name,price){
cart.push({name,price,size:selectedSize});
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
<span>${item.name} (${item.size})</span>
<span>$${item.price}</span>
</div>`;
});

count.innerText=cart.length;
total.innerText="Total: $"+sum;
}

function toggleCart(){
document.getElementById("cartPanel").classList.toggle("active");
document.getElementById("cartBackdrop").classList.toggle("active");
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
