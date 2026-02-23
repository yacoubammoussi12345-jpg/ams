<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Klick Spiel</title>
</head>
<body style="text-align:center; font-family:Arial;">

<h1>Klick Spiel</h1>
<p id="zeit">Zeit: 10</p>
<p id="punkte">Punkte: 0</p>
<button onclick="klick()">KLICK!</button>

<script>
let punkte = 0;
let zeit = 10;

function klick() {
    if (zeit > 0) {
        punkte++;
        document.getElementById("punkte").innerHTML = "Punkte: " + punkte;
    }
}

let timer = setInterval(function() {
    zeit--;
    document.getElementById("zeit").innerHTML = "Zeit: " + zeit;

    if (zeit <= 0) {
        clearInterval(timer);
        alert("Fertig! Deine Punkte: " + punkte);
    }
}, 1000);
</script>

</body>
</html>
