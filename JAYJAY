<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Custom Shoe Shop</title>

<style>

body{
font-family:Arial;
margin:0;
background:#f4f4f4;
}

header{
background:#111;
color:white;
padding:20px;
text-align:center;
}

.container{
display:flex;
flex-wrap:wrap;
padding:20px;
gap:20px;
}

.configurator, .cart{
background:white;
padding:20px;
border-radius:10px;
box-shadow:0 0 10px rgba(0,0,0,0.1);
flex:1;
min-width:300px;
}

.preview{
width:100%;
height:200px;
background:#ddd;
border-radius:10px;
display:flex;
align-items:center;
justify-content:center;
margin-bottom:20px;
position:relative;
}

.shoe{
width:200px;
height:80px;
border-radius:40px;
position:relative;
}

.sole{
position:absolute;
bottom:-10px;
height:20px;
width:100%;
border-radius:20px;
}

.laces{
position:absolute;
top:25px;
left:20px;
right:20px;
height:5px;
}

select,button,input{
width:100%;
padding:10px;
margin-top:10px;
border-radius:6px;
border:1px solid #ccc;
}

button{
background:#111;
color:white;
cursor:pointer;
}

button:hover{
background:#333;
}

.cart-item{
border-bottom:1px solid #ddd;
padding:10px 0;
}

.checkout{
margin-top:20px;
}

</style>
</head>

<body>

<header>
<h1>👟 Custom Shoe Shop</h1>
<p>Konfiguriere deinen eigenen Schuh</p>
</header>

<div class="container">

<div class="configurator">

<h2>Schuh konfigurieren</h2>

<div class="preview">

<div id="shoe" class="shoe">

<div id="sole" class="sole"></div>
<div id="laces" class="laces"></div>

</div>

</div>

<label>Schuhfarbe</label>
<select id="color">
<option value="red">Rot</option>
<option value="blue">Blau</option>
<option value="black">Schwarz</option>
<option value="white">Weiß</option>
</select>

<label>Sohlenfarbe</label>
<select id="soleColor">
<option value="white">Weiß</option>
<option value="black">Schwarz</option>
<option value="gray">Grau</option>
</select>

<label>Schnürsenkel</label>
<select id="lacesColor">
<option value="white">Weiß</option>
<option value="black">Schwarz</option>
<option value="red">Rot</option>
</select>

<label>Größe</label>
<select id="size">
<option>38</option>
<option>39</option>
<option>40</option>
<option>41</option>
<option>42</option>
<option>43</option>
<option>44</option>
</select>

<button onclick="addToCart()">Zum Warenkorb hinzufügen</button>

</div>

<div class="cart">

<h2>Warenkorb 🛒</h2>

<div id="cartItems"></div>

<h3 id="total">Gesamt: 0€</h3>

<div class="checkout">

<h3>Checkout</h3>

<input placeholder="Name" id="name">
<input placeholder="Adresse" id="address">
<input placeholder="Email" id="email">

<button onclick="checkout()">Bestellen</button>

</div>

</div>

</div>

<script>

const shoe = document.getElementById("shoe")
const sole = document.getElementById("sole")
const laces = document.getElementById("laces")

const color = document.getElementById("color")
const soleColor = document.getElementById("soleColor")
const lacesColor = document.getElementById("lacesColor")

color.onchange = updateShoe
soleColor.onchange = updateShoe
lacesColor.onchange = updateShoe

function updateShoe(){

shoe.style.background=color.value
sole.style.background=soleColor.value
laces.style.background=lacesColor.value

}

updateShoe()

let cart=[]
let total=0

function addToCart(){

const item={
color:color.value,
sole:soleColor.value,
laces:lacesColor.value,
size:document.getElementById("size").value,
price:79
}

cart.push(item)

total+=item.price

renderCart()

}

function renderCart(){

const cartDiv=document.getElementById("cartItems")
cartDiv.innerHTML=""

cart.forEach((item,index)=>{

const div=document.createElement("div")
div.className="cart-item"

div.innerHTML=`
Schuh ${index+1}<br>
Farbe: ${item.color}<br>
Sohle: ${item.sole}<br>
Schnürsenkel: ${item.laces}<br>
Größe: ${item.size}<br>
Preis: ${item.price}€
`

cartDiv.appendChild(div)

})

document.getElementById("total").innerText="Gesamt: "+total+"€"

}

function checkout(){

if(cart.length===0){

alert("Warenkorb ist leer")
return

}

const name=document.getElementById("name").value
const address=document.getElementById("address").value
const email=document.getElementById("email").value

if(!name || !address || !email){

alert("Bitte alle Felder ausfüllen")
return

}

alert("Danke für deine Bestellung "+name+"!")

cart=[]
total=0
renderCart()

}

</script>

</body>
</html>
