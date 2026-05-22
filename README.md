<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
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
  background:#fff;
  overflow-x:hidden;
}

/* NAV */
nav{
  position:fixed;
  top:0;
  width:100%;
  height:70px;
  background:white;
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:0 6%;
  border-bottom:1px solid #eee;
  z-index:1000;
}

.logo{
  font-size:40px;
  color:#ff2d55;
}

/* CART ICON */
.cart-icon{
  position:relative;
  cursor:pointer;
  font-size:24px;
}

.cart-count{
  position:absolute;
  top:-8px;
  right:-10px;
  background:red;
  color:white;
  width:18px;
  height:18px;
  font-size:12px;
  border-radius:50%;
  display:flex;
  justify-content:center;
  align-items:center;
}

/* TOP TEXT */
.top-banner{
  margin-top:70px;
  text-align:center;
  font-size:32px;
  color:#ff2d55;
  padding:18px 10px;
}

/* HERO */
.hero{
  text-align:center;
  padding-top:30px;
}

.main-img{
  width:280px;
  border-radius:16px;
  box-shadow:0 10px 25px rgba(0,0,0,0.2);
}

/* BUTTONS */
.btn-row{
  display:flex;
  justify-content:center;
  gap:10px;
  flex-wrap:wrap;
  margin-top:10px;
}

.size-btn,.color-btn{
  padding:10px 14px;
  border:2px solid #111;
  background:white;
  border-radius:10px;
  cursor:pointer;
}

.active{
  background:#111;
  color:white;
}

/* ACTION BUTTONS */
.actions{
  margin-top:15px;
}

.actions button{
  padding:12px 16px;
  margin:5px;
  border:none;
  border-radius:10px;
  cursor:pointer;
}

.buy{ background:#ff2d55; color:white; }
.add{ background:#19c37d; color:white; }

/* START SCREEN */
.start-screen{
  position:fixed;
  inset:0;
  background:white;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  z-index:4000;
}

.start-screen img{
  width:260px;
  border-radius:16px;
  cursor:pointer;
}

.start-text{
  margin-top:10px;
  font-size:22px;
  color:#ff2d55;
}

/* CART */
.cart-panel{
  position:fixed;
  top:0;
  right:-350px;
  width:300px;
  height:100%;
  background:white;
  transition:0.3s;
  box-shadow:-10px 0 30px rgba(0,0,0,0.2);
  padding:20px;
  z-index:3000;
}

.cart-panel.active{
  right:0;
}

.cart-item{
  margin-top:10px;
  padding-bottom:10px;
  border-bottom:1px solid #ddd;
}

.total{
  margin-top:20px;
  font-size:20px;
}

.close-btn{
  position:absolute;
  top:10px;
  right:10px;
  border:none;
  background:#ff2d55;
  color:white;
  width:30px;
  height:30px;
  border-radius:50%;
  cursor:pointer;
}

</style>
</head>

<body>

<!-- START SCREEN -->
<div class="start-screen" id="start">
  <img onclick="enterSite()"
  src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png">
  <div class="start-text">TAP TO ENTER</div>
</div>

<!-- NAV -->
<nav>
  <div class="logo">DWOCK</div>

  <div class="cart-icon" onclick="toggleCart()">
    🛒
    <div class="cart-count" id="count">0</div>
  </div>
</nav>

<!-- TOP TEXT -->
<div class="top-banner">
  YOUR STYLE STARTS NOW
</div>

<!-- HERO -->
<section class="hero">

  <img id="mainImage" class="main-img"
  src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png">

  <!-- SIZE -->
  <div class="btn-row">
    <button class="size-btn active" onclick="setSize(this,'S')">S</button>
    <button class="size-btn" onclick="setSize(this,'M')">M</button>
    <button class="size-btn" onclick="setSize(this,'L')">L</button>
  </div>

  <!-- COLOR IMAGES (ALL YOUR IMAGES) -->
  <div class="btn-row">

    <button class="color-btn active" onclick="changeImage(0,this)">DROP 1</button>
    <button class="color-btn" onclick="changeImage(1,this)">DROP 2</button>
    <button class="color-btn" onclick="changeImage(2,this)">DROP 3</button>
    <button class="color-btn" onclick="changeImage(3,this)">DROP 4</button>
    <button class="color-btn" onclick="changeImage(4,this)">DROP 5</button>
    <button class="color-btn" onclick="changeImage(5,this)">DROP 6</button>
    <button class="color-btn" onclick="changeImage(6,this)">DROP 7</button>
    <button class="color-btn" onclick="changeImage(7,this)">DROP 8</button>

  </div>

  <!-- ACTIONS -->
  <div class="actions">
    <button class="buy" onclick="addToCart()">BUY NOW</button>
    <button class="add" onclick="addToCart()">ADD TO CART</button>
  </div>

</section>

<!-- CART -->
<div class="cart-panel" id="cart">

  <button class="close-btn" onclick="toggleCart()">✖</button>

  <h2>YOUR CART</h2>

  <div id="cartItems"></div>

  <div class="total" id="total">Total: $0</div>

</div>

<script>

let cart = [];
let selectedSize = "S";

/* ALL YOUR IMAGES */
const images = [
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png",
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png",
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png",
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png",
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png",
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2449.png",
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png",
"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png"
];

/* START */
function enterSite(){
  document.getElementById("start").style.display="none";
}

/* SIZE */
function setSize(btn,size){
  selectedSize=size;
  document.querySelectorAll(".size-btn").forEach(b=>b.classList.remove("active"));
  btn.classList.add("active");
}

/* CHANGE IMAGE */
function changeImage(index,btn){
  document.getElementById("mainImage").src = images[index];
  document.querySelectorAll(".color-btn").forEach(b=>b.classList.remove("active"));
  btn.classList.add("active");
}

/* CART */
function addToCart(){
  cart.push({ name:"DWOCK ITEM", size:selectedSize });
  updateCart();
}

function updateCart(){
  let box=document.getElementById("cartItems");
  let total=document.getElementById("total");
  let count=document.getElementById("count");

  box.innerHTML="";
  let sum=0;

  cart.forEach(item=>{
    sum+=30;
    box.innerHTML+=`<div class="cart-item">${item.name} (${item.size}) - $30</div>`;
  });

  total.innerText="Total: $"+sum;
  count.innerText=cart.length;
}

/* CART TOGGLE */
function toggleCart(){
  document.getElementById("cart").classList.toggle("active");
}

</script>

</body>
</html>
