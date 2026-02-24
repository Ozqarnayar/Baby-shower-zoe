# Baby-shower-zoe
baby shower zoe
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Baby Shower Zoé</title>

<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Montserrat:wght@300;500&display=swap" rel="stylesheet">

<style>
body{
    margin:0;
    font-family:'Montserrat', sans-serif;
    background:linear-gradient(to bottom, #ffd6e8, #ffffff);
    text-align:center;
    color:#8b4a6b;
    overflow-x:hidden;
}

/* Animación de entrada */
.fade-in{
    opacity:0;
    transform:translateY(30px);
    animation:fadeInUp 1.5s forwards;
}

@keyframes fadeInUp{
    to{
        opacity:1;
        transform:translateY(0);
    }
}

.section{
    padding:60px 20px;
}

h1{
    font-family:'Pacifico', cursive;
    font-size:3.2em;
    animation:heartbeat 2s infinite;
}

@keyframes heartbeat{
    0%,100%{transform:scale(1);}
    50%{transform:scale(1.05);}
}

h2{
    font-size:2em;
}

.button{
    display:inline-block;
    padding:15px 30px;
    margin:15px;
    background:#ff9ecb;
    color:white;
    text-decoration:none;
    border-radius:30px;
    font-weight:bold;
    transition:0.3s;
    box-shadow:0 5px 15px rgba(0,0,0,0.1);
}

.button:hover{
    background:#ff6fb3;
    transform:scale(1.1);
}

.countdown{
    font-size:1.6em;
    margin-top:20px;
    font-weight:bold;
}

/* Globos flotando */
.balloon{
    position:fixed;
    bottom:-150px;
    width:40px;
    height:50px;
    background:#ffb6d9;
    border-radius:50%;
    animation:float 10s infinite;
}

.balloon:after{
    content:'';
    position:absolute;
    width:2px;
    height:40px;
    background:#aaa;
    left:50%;
    top:50px;
}

@keyframes float{
    0%{transform:translateY(0);}
    100%{transform:translateY(-110vh);}
}

.balloon:nth-child(1){left:10%; animation-duration:9s;}
.balloon:nth-child(2){left:30%; animation-duration:12s;}
.balloon:nth-child(3){left:50%; animation-duration:10s;}
.balloon:nth-child(4){left:70%; animation-duration:14s;}
.balloon:nth-child(5){left:90%; animation-duration:11s;}

.pooh{
    width:200px;
    margin:20px auto;
}
</style>
</head>

<body>

<!-- Globos -->
<div class="balloon"></div>
<div class="balloon"></div>
<div class="balloon"></div>
<div class="balloon"></div>
<div class="balloon"></div>

<audio autoplay loop>
  <source src="gimnasia.mp3" type="audio/mpeg">
</audio>

<div class="section fade-in">
    <h1>Baby Shower</h1>
    <h2>Zoé</h2>
    <img class="pooh" src="https://i.imgur.com/6QZ6Z9F.png" alt="Winnie Pooh">
    <p><strong>La dulce espera está por terminar</strong></p>
</div>

<div class="section fade-in">
    <h2>📅 28 de marzo 2026</h2>
    <h2>🕒 4:40 PM</h2>
    <div class="countdown" id="countdown"></div>
</div>

<div class="section fade-in">
    <h2>📍 Ubicación</h2>
    <a class="button" href="https://maps.app.goo.gl/CfFLgyTNA2M7JLFj6?g_st=ic" target="_blank">
        Ver en Google Maps
    </a>
</div>

<div class="section fade-in">
    <h2>💌 Confirmar asistencia</h2>
    <a class="button" href="https://wa.me/525543700603" target="_blank">
        Confirmar por WhatsApp
    </a>
</div>

<script>
var eventDate = new Date("March 28, 2026 16:40:00").getTime();

var x = setInterval(function() {

var now = new Date().getTime();
var distance = eventDate - now;

var days = Math.floor(distance / (1000 * 60 * 60 * 24));
var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));

document.getElementById("countdown").innerHTML =
"Faltan " + days + " días, " + hours + " horas y " + minutes + " minutos";

if (distance < 0) {
    clearInterval(x);
    document.getElementById("countdown").innerHTML = "¡Hoy es el gran día!";
}

}, 1000);
</script>

</body>
</html>
