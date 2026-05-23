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

/* HEADER */
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
h1{font-size:32px;}
p{font-size:20px;}

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

/* BUTTONS */
.btn{
  padding:12px 18px;
  border:none;
  border-radius:12px;
  cursor:pointer;
  font-size:16px;
  margin-top:10px;
}

.buy{background:#ff2d55;color:white;}
.cartBtn{background:#19c37d;color:white;}

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
  border-radius:12px;
}

/* CART */
.cartIcon{
  position:relative;
  cursor:pointer;
  font-size:22px;
}

.cartCount{
  position:absolute;
  top:-8px;
  right:-10px;
  background:red;
  color:white;
  width:18px;
  height:18px;
  border-radius:50%;
  font-size:12px;
  display:flex;
  align-items:center;
  justify-content:center;
}

.cartPanel{
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

.cartPanel.active{
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

.closeBtn{
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

<header>
<nav>
<div class="logo">DWOCK</div>

<div class="cartIcon" onclick="toggleCart()">
🛒
<span class="cartCount" id="count">0</span>
</div>

</nav>
<div class="banner">YOUR STYLE STARTS NOW!!!</div>
</header>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox" onclick="closeImg()">
<img id="bigImg">
</div>

<!-- CART -->
<div class="cartPanel" id="cartPanel">

<button class="closeBtn" onclick="toggleCart()">Close</button>

<h2>Your Cart</h2>
<div id="cartItems"></div>

<div class="total" id="total">Total: $0</div>

<button class="checkout" onclick="checkout()">Checkout</button>

</div>

<section class="hero">
<div class="container">

<img id="mainImage"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
onclick="openImg(this.src)">

<div>

<h1>DWOCK STREETWEAR</h1>
<p>$30</p>

<div class="img-buttons">

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png')">1</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png')">2</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png')">3</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png')">4</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png')">6</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png')">8</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png')">9</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png')">10</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/9353299672d1759321ae4322918b01472604d428/IMG_0591%20(1).jpeg')">11</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/fc86785c18195f59c1d7d29ceb4ae2c9e74d062e/22c3e4d4-1a52-479a-9fcb-2de86f1bf029.png')">12</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/main/9353299672d1759321ae4322918b01472604d428/IMG_0594.png')">13</button>

</div>

<button class="btn buy" onclick="addToCart('DWOCK Shirt',30)">BUY NOW</button>
<button class="btn cartBtn" onclick="addToCart('DWOCK Shirt',30)">ADD TO CART</button>

</div>
</div>
</section>

<script>

let cart = [];

function addToCart(name,price){
cart.push({name,price});
updateCart();
}

function updateCart(){

let box = document.getElementById("cartItems");
let count = document.getElementById("count");
let total = document.getElementById("total");

box.innerHTML = "";
let sum = 0;

cart.forEach(item=>{
sum += item.price;
box.innerHTML += `<div class="item"><span>${item.name}</span><span>$${item.price}</span></div>`;
});

count.innerText = cart.length;
total.innerText = "Total: $" + sum;
}

function toggleCart(){
document.getElementById("cartPanel").classList.toggle("active");
}

function openImg(src){
document.getElementById("bigImg").src = src;
document.getElementById("lightbox").style.display = "flex";
}

function closeImg(){
document.getElementById("lightbox").style.display = "none";
}

</script>

</body>
</html>
