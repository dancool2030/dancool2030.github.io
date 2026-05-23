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

/* BANNER */
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
  width:350px;
  border-radius:18px;
}

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

/* CART BUTTONS */
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

</style>
</head>

<body>

<nav>
<div class="logo">DWOCK</div>
</nav>

<div class="top-banner">YOUR STYLE STARTS NOW!!!</div>

<section class="hero">

<div class="container">

<!-- MAIN IMAGE -->
<img id="mainImage"
src="https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png">

<div>

<h1>DWOCK STREETWEAR</h1>
<p>$30</p>

<!-- ALL IMAGE BUTTONS (EVERY IMAGE YOU USED) -->
<div class="img-buttons">

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/bb8fa202f78fe6d39039532d410679af1013b1d7/IMG_2449.png')">IMG 1</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2008_11_12%20AM.png')">IMG 2</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/ChatGPT%20Image%20May%2013%2C%202026%2C%2007_25_46%20PM.png')">IMG 3</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/da666a1a15eea37f1e562a0cded39443d2a29802/33d8dc77-8b36-45ab-a6cd-9124637d6da4.png')">IMG 4</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/182ea8c6-dc6e-4fb3-aeb1-209ef47e9f9a.png')">IMG 5</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2455.png')">IMG 6</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2449.png')">IMG 7</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_2447.png')">IMG 8</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0598.png')">IMG 9</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/c283e41d7265ec6b28026ef18c334227bdf8614a/IMG_0597.png')">IMG 10</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0591%20(1).jpeg')">IMG 11</button>

<button class="img-btn" onclick="changeImg(this,'https://raw.githubusercontent.com/dancool2030/dancool2030.github.io/9353299672d1759321ae4322918b01472604d428/IMG_0594.png')">IMG 12</button>

</div>

<button class="btn buy">BUY NOW</button>
<button class="btn cart">ADD TO CART</button>

</div>

</div>

</section>

<script>

function changeImg(btn,src){
document.getElementById("mainImage").src = src;

document.querySelectorAll(".img-btn").forEach(b=>{
b.style.opacity="0.6";
});

btn.style.opacity="1";
}

</script>

</body>
</html>
