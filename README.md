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

/* TOP BANNER */

.top-banner{
  margin-top:70px;
  text-align:center;
  font-size:32px;
  color:#ff2d55;
  padding:18px 10px;
  letter-spacing:2px;
  animation:floatText 2s infinite ease-in-out;
}

@keyframes floatText{

  0%,100%{
    transform:translateY(0);
  }

  50%{
    transform:translateY(-4px);
  }

}

/* HERO */

.hero{
  padding-top:40px;
  text-align:center;
}

.main-img{
  width:280px;
  border-radius:16px;
  box-shadow:0 10px 25px rgba(0,0,0,0.2);
}

/* SIZE + COLOR */

.controls{
  margin-top:20px;
}

.btn-row{
  display:flex;
  justify-content:center;
  gap:10px;
  margin-top:10px;
  flex-wrap:wrap;
}

.size-btn,
.color-btn{
  padding:10px 14px;
  border:2px solid #111;
  background:white;
  cursor:pointer;
  border-radius:10px;
  font-size:16px;
}

.active{
  background:#111;
  color:white;
}

/* BUTTONS */

.actions{
  margin-top:15px;
}

.actions button{
  padding:12px 16px;
  margin:5px;
  border:none;
  border-radius:10px;
  cursor:pointer;
  font-size:16px;
}

.buy{
  background:#ff2d55;
  color:white;
}

.add{
  background:#19c37d;
  color:white;
}

/* START SCREEN */

.start-screen{
  position:fixed;
  inset:0;
  background:white;
  display:flex;
  justify-content:center;
  align-items:center;
  flex-direction:column;
  z-index:2000;
}

.start-screen img{
  width:260px;
  border-radius:16px;
  cursor:pointer;
  box-shadow:0 10px 25px rgba(0,0,0,.2);
}

.start-text{
  margin-top:15px;
  font-size:24px;
  color:#ff2d55;
}

/* CART */

.cart-panel{
  position:fixed;
  right:-350px;
  top:0;
  width:300px;
  height:100%;
  background:white;
  transition:.3s;
  box-shadow:-10px 0 30px rgba(0,0,0,0.2);
  padding:20px;
  z-index:3000;
}

.cart-panel.active{
  right:0;
}

.cart-panel h2{
  margin-bottom:20px;
}

.cart-item{
  margin-bottom:12px;
  padding-bottom:10px;
  border-bottom:1px solid #ddd;
}

/* MOBILE */

@media(max-width:768px){

  .top-banner{
    font-size:22px;
  }

  .main-img{
    width:85%;
  }

}

</style>
</head>

<body>

<!-- START SCREEN -->

<div class="start-screen" id="start">

  <img 
  src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
  onclick="enterSite()"
  >

  <div class="start-text">
    TAP TO ENTER
  </div>

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

  <img 
  id="mainImage"
  class="main-img"
  src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png"
  >

  <!-- SIZE -->

  <div class="controls">

    <div class="btn-row">

      <button class="size-btn active" onclick="setSize(this,'S')">
        S
      </button>

      <button class="size-btn" onclick="setSize(this,'M')">
        M
      </button>

      <button class="size-btn" onclick="setSize(this,'L')">
        L
      </button>

    </div>

    <!-- COLORS -->

    <div class="btn-row">

      <button class="color-btn active" onclick="changeColor(0,this)">
        BLACK
      </button>

      <button class="color-btn" onclick="changeColor(1,this)">
        WHITE
      </button>

      <button class="color-btn" onclick="changeColor(2,this)">
        RED
      </button>

    </div>

  </div>

  <!-- ACTION BUTTONS -->

  <div class="actions">

    <button class="buy" onclick="addToCart()">
      BUY NOW
    </button>

    <button class="add" onclick="addToCart()">
      ADD TO CART
    </button>

  </div>

</section>

<!-- CART -->

<div class="cart-panel" id="cart">

  <h2>YOUR CART</h2>

  <div id="cartItems"></div>

</div>

<script>

let cart = [];
let selectedSize = "S";

/* PRODUCT IMAGES */

const images = [

"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png",

"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png",

"https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png"

];

/* ENTER SITE */

function enterSite(){

  document.getElementById("start").style.display = "none";

}

/* SIZE */

function setSize(btn,size){

  selectedSize = size;

  document
  .querySelectorAll(".size-btn")
  .forEach(b => b.classList.remove("active"));

  btn.classList.add("active");

}

/* COLOR SWITCH */

function changeColor(index,btn){

  document.getElementById("mainImage").src = images[index];

  document
  .querySelectorAll(".color-btn")
  .forEach(b => b.classList.remove("active"));

  btn.classList.add("active");

}

/* ADD TO CART */

function addToCart(){

  cart.push({
    name:"DWOCK SHIRT",
    size:selectedSize
  });

  updateCart();

}

/* UPDATE CART */

function updateCart(){

  const cartItems = document.getElementById("cartItems");

  cartItems.innerHTML = "";

  cart.forEach(item => {

    cartItems.innerHTML += `

      <div class="cart-item">
        ${item.name} - ${item.size}
      </div>

    `;

  });

  document.getElementById("count").innerText = cart.length;

}

/* OPEN CART */

function toggleCart(){

  document
  .getElementById("cart")
  .classList.toggle("active");

}

</script>

</body>
</html>
