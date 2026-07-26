# Gta-mini
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>GTA Mini</title>

<style>
body{
margin:0;
overflow:hidden;
background:#6ec6ff;
font-family:Arial;
}

#map{
width:100vw;
height:100vh;
position:relative;
background:#5cb85c;
}

#road{
position:absolute;
left:45%;
width:10%;
height:100%;
background:#555;
}

#player{
position:absolute;
width:40px;
height:40px;
background:red;
border-radius:8px;
left:50%;
top:80%;
transform:translate(-50%,-50%);
}

.car{
position:absolute;
width:50px;
height:80px;
background:blue;
left:50%;
top:20%;
transform:translateX(-50%);
}

.house{
position:absolute;
width:80px;
height:80px;
background:#d19a66;
}

#house1{left:20%;top:20%;}
#house2{left:70%;top:60%;}

#ui{
position:absolute;
top:10px;
left:10px;
color:white;
font-size:22px;
font-weight:bold;
text-shadow:2px 2px black;
}
</style>
</head>

<body>

<div id="map">

<div id="road"></div>

<div id="player"></div>

<div class="car"></div>

<div class="house" id="house1"></div>
<div class="house" id="house2"></div>

<div id="ui">
HP:100<br>
Uang:$0
</div>

</div>

<script>

const player=document.getElementById("player");

let x=window.innerWidth/2;
let y=window.innerHeight*0.8;

const speed=6;

let keys={};

document.addEventListener("keydown",(e)=>{
keys[e.key.toLowerCase()]=true;
});

document.addEventListener("keyup",(e)=>{
keys[e.key.toLowerCase()]=false;
});

function update(){

if(keys["w"]) y-=speed;
if(keys["s"]) y+=speed;
if(keys["a"]) x-=speed;
if(keys["d"]) x+=speed;

player.style.left=x+"px";
player.style.top=y+"px";

requestAnimationFrame(update);

}

update();

</script>

</body>
</html>
