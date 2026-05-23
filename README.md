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
  background:white;
  overflow-x:hidden;
  transform:scale(0.95);
  transform-origin:top;
}

/* NAV + BANNER SAME LINE */
header{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  z-index:1000;
  background:rgba(255,255,255,.95);
  border-bottom:1px solid #eee;
}

nav{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:12px 6%;
}

.logo{
  font-size:34px;
  color:#ff2d55;
}

/* banner INSIDE NAV so it stays aligned */
.banner{
  text-align:center;
  font-size:20px;
  color:#ff2d55;
  padding-bottom:8px;
}

/* HERO */
.hero{
  padding:160px 6% 40px;
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
  width:320px;
  border-radius:18px;
  cursor:pointer;
  box-shadow:0 10px 25px rgba(0,0,0,.15);
}

/* TEXT */
h1{
  font-size:32px;
}

p{
  font-size:20px;
}

/* IMAGE BUTTONS */
.img-buttons{
  display:flex;
  flex-wrap:wrap;
  gap:8px;
  margin-top:12px;
  max-width:420px;
}

.img-btn{
  padding:8px 10px;
  border:none;
  border-radius:8px;
  background:#0BA3FF;
  color:white;
  cursor:pointer;
  font-size:12px;
}

/* ALL BUTTONS */
.btn{
  padding:12px 18px;
  border:none;
  border-radius:12px;
  cursor:pointer;
  font-size:16px;
  margin-top:10px;
}

.buy{background:#ff2d55;color:white;}
.cart{background:#19c37d;color:white;}

/* CART */
.cart-panel{
  position:fixed;
  top:0;
  right:-350px;
  width:300px;
  height:100%;
  background:white;
  box-shadow:-10px 0 30px rgba(0,0,0,.2);
  padding:20px;
  transition:.3s;
  z-index:2000;
}

.cart-panel.active{
  right:0;
}

.close-cart{
  background:#ff2d55;
  color:white;
  border:none;
  padding:8px 12px;
  border-radius:10px;
  cursor:pointer;
  margin-bottom:10px;
}

.item{
  display:flex;
  justify-content:space-between;
  margin:10px 0;
  border-bottom:1px solid #eee;
  padding-bottom:6px;
}

</style>
</head>

<body>

<!-- HEADER -->
<header>
<nav>
<div class="logo">DWOCK</div>
<button class="close-cart" onclick="toggleCart()">🛒 Cart</button>
</nav>

<div class="banner">YOUR STYLE STARTS NOW!!!</div>
</header>

<!-- HERO -->
<section class="hero">
<div class="container">

<img id="mainImage"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
onclick="openImg(this.src)">

<div>

<h1>DWOCK STREETWEAR</h1>
<p>$30</p>

<!-- ALL IMAGE BUTTONS -->
<div class="img-buttons">

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png')">1</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png')">2</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png')">3</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png')">4</button>

<!-- FIXED IMAGE 5 -->
<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png')">5</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png')">6</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2449.png')">7</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png')">8</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png')">9</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png')">10</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0591%20(1).jpeg')">11</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0594.png')">12</button>

</div>

<button class="btn buy">BUY NOW</button>
<button class="btn cart" onclick="toggleCart()">ADD TO CART</button>

</div>
</div>
</section>

<!-- CART -->
<div class="cart-panel" id="cart">
<button class="close-cart" onclick="toggleCart()">Close ✖</button>
<h3>Your Cart</h3>
<div id="cartItems"></div>
</div>

<script>

let cart=[];

function changeImg(btn,src){
document.getElementById("mainImage").src=src;
document.querySelectorAll(".img-btn").forEach(b=>b.style.opacity=".6");
btn.style.opacity="1";
}

function toggleCart(){
document.getElementById("cart").classList.toggle("active");
}

function addToCart(name,price){
cart.push({name,price});
updateCart();
}

function updateCart(){
let box=document.getElementById("cartItems");
box.innerHTML="";
cart.forEach(i=>{
box.innerHTML+=`
<div class="item">
<span>${i.name}</span>
<span>$${i.price}</span>
</div>`;
});
}

function openImg(src){
window.open(src,"_blank");
}

</script>

</body>
</html>
