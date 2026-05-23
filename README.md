<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ĐOCK STORE</title>

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
  background:linear-gradient(
    90deg,
    #00ff88,
    #00aaff,
    #ff2d55,
    #ff66cc
  );
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.title{
  background:linear-gradient(
    90deg,
    #00ff88,
    #00aaff,
    #ff2d55,
    #ff66cc
  );
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.banner{
  text-align:center;
  font-size:20px;
  color:#ff2d55;
  padding-bottom:8px;
}

/* CART ICON */

.cart-icon{
  position:relative;
  cursor:pointer;
  font-size:22px;
}

.cart-count{
  position:absolute;
  top:-8px;
  right:-10px;
  width:18px;
  height:18px;
  border-radius:50%;
  background:red;
  color:white;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:11px;
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

/* BUTTONS */
.btn{
  padding:12px 18px;
  border:none;
  border-radius:12px;
  cursor:pointer;
  font-size:16px;
  margin-top:10px;
}

.buy{
  background:#ff2d55;
  color:white;
}

.cartBtn{
  background:#19c37d;
  color:white;
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
  border-radius:12px;
}

/* CART PANEL */

.cart-panel{
  position:fixed;
  top:0;
  right:-360px;
  width:320px;
  height:100%;
  background:white;
  padding:20px;
  box-shadow:-10px 0 30px rgba(0,0,0,.2);
  transition:.3s;
  z-index:6000;
  overflow-y:auto;
}

.cart-panel.active{
  right:0;
}

.close-cart{
  position:absolute;
  top:12px;
  right:12px;
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
  margin:12px 0;
  padding-bottom:10px;
  border-bottom:1px solid #eee;
}

.total{
  margin-top:20px;
  font-size:24px;
}

.checkout{
  width:100%;
  margin-top:20px;
  padding:14px;
  border:none;
  border-radius:12px;
  background:#ff2d55;
  color:white;
  cursor:pointer;
  font-size:18px;
}

</style>
</head>

<body>

<header>

<nav>

<div class="logo">ĐOCK</div>

<!-- CART ICON -->
<div class="cart-icon" onclick="toggleCart()">
🛒
<div class="cart-count" id="count">0</div>
</div>

</nav>

<div class="banner">YOUR STYLE STARTS NOW!!!</div>

</header>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox" onclick="closeImg()">
<img id="bigImg">
</div>

<!-- CART PANEL -->

<div class="cart-panel" id="cartPanel">

<button class="close-cart" onclick="toggleCart()">
✖
</button>

<h2>Your Cart</h2>

<div id="cartItems"></div>

<div class="total" id="total">
Total: $0
</div>

<button class="checkout" onclick="checkout()">
Checkout
</button>

</div>

<section class="hero">
<div class="container">

<!-- MAIN IMAGE -->
<img id="mainImage"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
onclick="openImg(this.src)">

<div>

<h1 class="title">ĐOCK Joggers</h1>
<p>$30</p>

<div class="img-buttons">

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png')">1</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png')">2</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png')">3</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png')">4</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png')">6</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png')">8</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png')">9</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png')">10</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0591%20(1).jpeg')">11</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/fc86785c18195f59c1d7d29ceb4ae2c9e74d062e/22c3e4d4-1a52-479a-9fcb-2de86f1bf029.png')">12</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0594.png')">13</button>

</div>

<button class="btn buy" onclick="addToCart('ĐOCK Joggers',30)">
BUY NOW
</button>

<button class="btn cartBtn" onclick="addToCart('ĐOCK Joggers',30)">
ADD TO CART
</button>

</div>
</div>
</section>

<script>

/* IMAGE SWITCHER */

function changeImg(btn,src){

document.getElementById("mainImage").src=src;

document.querySelectorAll(".img-btn").forEach(b=>{
b.style.opacity=".5";
});

btn.style.opacity="1";

}

/* LIGHTBOX */

function openImg(src){

document.getElementById("bigImg").src=src;
document.getElementById("lightbox").style.display="flex";

}

function closeImg(){

document.getElementById("lightbox").style.display="none";

}

/* CART */

let cart = [];

/* ADD TO CART */

function addToCart(name,price){

cart.push({name,price});

updateCart();

}

/* UPDATE CART */

function updateCart(){

let box = document.getElementById("cartItems");
let count = document.getElementById("count");
let total = document.getElementById("total");

box.innerHTML = "";

let sum = 0;

cart.forEach((item,index)=>{

sum += item.price;

box.innerHTML += `
<div class="item">
<span>${item.name}</span>
<span>$${item.price}</span>
</div>
`;

});

count.innerText = cart.length;

total.innerText = "Total: $" + sum;

}

/* TOGGLE CART */

function toggleCart(){

document.getElementById("cartPanel")
.classList.toggle("active");

}

/* CHECKOUT */

function checkout(){

alert("Checkout coming soon 🔥");

}

</script>

</body>
</html>
