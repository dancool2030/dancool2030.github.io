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
  color:#111;
}

/* NAVBAR */

nav{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  padding:16px 6%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:rgba(255,255,255,.95);
  border-bottom:1px solid #eee;
  z-index:1000;
  backdrop-filter:blur(10px);
}

.logo{
  font-size:42px;
  color:#ff2d55;
  letter-spacing:2px;
}

.nav-right{
  display:flex;
  align-items:center;
  gap:18px;
}

nav a{
  text-decoration:none;
  color:#111;
  font-size:16px;
}

/* CART */

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

/* TOP BANNER */

.top-banner{
  position:fixed;
  top:92px; /* LOWERED */
  left:50%;
  transform:translateX(-50%);
  z-index:999;
  font-size:30px;
  color:#ff2d55;
  letter-spacing:2px;
  text-align:center;
  animation:bounce 2.5s infinite;
  transition:.3s;
  pointer-events:none;
}

.top-banner.small{
  top:82px;
  font-size:20px;
}

@keyframes bounce{
  0%,100%{
    transform:translateX(-50%) translateY(0);
  }
  50%{
    transform:translateX(-50%) translateY(-5px);
  }
}

/* HERO */

.hero{
  padding:180px 6% 70px;
}

.container{
  max-width:1200px;
  margin:auto;
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
  align-items:center;
  gap:50px;
}

.hero-image{
  width:420px;
}

.hero-image img{
  width:100%;
  border-radius:22px;
  box-shadow:0 15px 35px rgba(0,0,0,.15);
  cursor:pointer;
}

/* IMAGE BUTTONS */

.image-buttons{
  display:flex;
  flex-wrap:wrap;
  gap:10px;
  margin-top:18px;
  justify-content:center;
}

.image-btn{
  width:42px;
  height:42px;
  border:none;
  border-radius:12px;
  background:#111;
  color:white;
  cursor:pointer;
  font-size:14px;
  transition:.3s;
}

.image-btn:hover{
  background:#ff2d55;
  transform:scale(1.08);
}

/* HERO TEXT */

.hero-text{
  max-width:480px;
}

.hero-text h1{
  font-size:58px;
  line-height:1;
  margin-bottom:15px;
}

.hero-text p{
  font-size:24px;
  margin-bottom:18px;
}

.price{
  font-size:42px;
  color:#ff2d55;
  margin-bottom:25px;
}

/* BUTTONS */

.buttons{
  display:flex;
  gap:15px;
  flex-wrap:wrap;
}

.btn{
  padding:14px 22px;
  border:none;
  border-radius:14px;
  cursor:pointer;
  font-size:18px;
  transition:.3s;
}

.btn:hover{
  transform:translateY(-3px);
}

.buy{
  background:#ff2d55;
  color:white;
}

.cart{
  background:#19c37d;
  color:white;
}

/* LIGHTBOX */

.lightbox{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.92);
  display:none;
  align-items:center;
  justify-content:center;
  z-index:5000;
}

.lightbox img{
  max-width:90%;
  max-height:90%;
  border-radius:20px;
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

/* MOBILE */

@media(max-width:768px){

  .top-banner{
    font-size:20px;
    top:88px;
  }

  .hero{
    padding-top:170px;
  }

  .hero-image{
    width:100%;
  }

  .hero-text h1{
    font-size:40px;
  }

}

</style>
</head>

<body>

<!-- NAV -->

<nav>

<div class="logo">DWOCK</div>

<div class="nav-right">

<a href="#">Home</a>
<a href="#">Shop</a>

<div class="cart-icon" onclick="toggleCart()">
🛒
<div class="cart-count" id="count">0</div>
</div>

</div>

</nav>

<!-- TOP BANNER -->

<div class="top-banner" id="banner">
YOUR STYLE STARTS NOW!!!
</div>

<!-- HERO -->

<section class="hero">

<div class="container">

<div class="hero-image">

<img id="mainImage"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
onclick="openImg(this.src)">

<!-- IMAGE SWITCH BUTTONS -->

<div class="image-buttons">

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png')">1</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png')">2</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png')">3</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png')">4</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png')">5</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png')">6</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png')">7</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png')">8</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png')">9</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0591%20(1).jpeg')">10</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0594.png')">11</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/22c3e4d4-1a52-479a-9fcb-2de86f1bf029.png')">12</button>

<button class="image-btn" onclick="changeMainImage('https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bdfbdedca938b7f7384594259496d482430debf3/Screenshot%202026-05-21%20185824.png')">13</button>

</div>

</div>

<div class="hero-text">

<h1>DWOCK STREETWEAR</h1>

<p>
Premium streetwear made for riders and everyday fits.
</p>

<div class="price">$30</div>

<div class="buttons">

<button class="btn buy"
onclick="addToCart('Main Shirt',30)">
BUY NOW
</button>

<button class="btn cart"
onclick="addToCart('Main Shirt',30)">
ADD TO CART
</button>

</div>

</div>

</div>

</section>

<!-- LIGHTBOX -->

<div class="lightbox" id="lightbox"
onclick="closeImg()">

<img id="bigImg">

</div>

<!-- CART -->

<div class="cart-panel" id="cartPanel">

<button class="close-cart"
onclick="toggleCart()">
✖
</button>

<h2>Your Cart</h2>

<div id="cartItems"></div>

<div class="total" id="total">
Total: $0
</div>

<button class="checkout"
onclick="checkout()">
Checkout
</button>

</div>

<script>

let cart = [];

/* CHANGE IMAGE */

function changeMainImage(src){

document.getElementById("mainImage").src = src;

}

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

cart.forEach(item=>{

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

/* CART */

function toggleCart(){

document.getElementById("cartPanel")
.classList.toggle("active");

}

/* LIGHTBOX */

function openImg(src){

document.getElementById("bigImg").src = src;

document.getElementById("lightbox").style.display = "flex";

}

function closeImg(){

document.getElementById("lightbox").style.display = "none";

}

/* CHECKOUT */

function checkout(){

alert("Checkout coming soon 🔥");

}

/* BANNER SCROLL */

window.addEventListener("scroll",()=>{

const banner = document.getElementById("banner");

if(window.scrollY > 80){

banner.classList.add("small");

}else{

banner.classList.remove("small");

}

});

</script>

</body>
</html>
