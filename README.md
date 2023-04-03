<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body> 
    <button onclick="dodajSat()">Dodaj sat</button>
    <h1 id="vreme">00:00:00</h1>
    <script>
       
       let vreme = document.getElementById("vreme");
       const interval = setInterval(tick, 1);
       let secondsPassed = 0;
        
       let seconds = 0, minutes = 0, hours = 0;

       function dodajSat(){
            secondsPassed += 3600;
       }



         
       function tick(){ 
            secondsPassed ++;

            seconds = secondsPassed % 60;
            minutes = parseInt(secondsPassed / 60) % 60 ;
            hours= parseInt(secondsPassed / 3600) % 24;

            vreme.innerHTML = "";


            // pisemo sate - proveravamo za vodece nule
            if(hours < 10){
                vreme.innerHTML += "0" + hours + ":";
            }
            else{
                vreme.innerHTML += hours + ":";
            }
            // pisemo minute - proveravamo za vodece nule
            if(minutes < 10){
                vreme.innerHTML += "0" + minutes + ":";
            }
            else{
                vreme.innerHTML += minutes + ":";
            }
            // pisemo sekunde - takodje proveravamo za vodece nule
            if(seconds < 10){
                vreme.innerHTML += "0" + seconds;
            }
            else{
                vreme.innerHTML += seconds;
            }
        
     /* 
          DOMACI ZADATAK
          Postaviti pozadinsku boju body-ja u zavisnosti od toga koliko ima sati: 
            0 - 4  : tamnoplava pozadina
            5 - 8  : crvenkasta
            9 - 14 : svetloplava
            15 - 18 : i dalje svetla ali malo tamnija plva
            19 - 21 : svetla, tamnoplava
            22 - 24 : indigo
        
     */

            if (hours >= 0 && hours <= 4) {
             document.body.style.backgroundColor = "#03254B";
            }
            
            else if (hours >= 5 && hours <= 8) {
            document.body.style.backgroundColor = "#8f1818";
            } 

            else if (hours >= 9 && hours <= 14) {
             document.body.style.backgroundColor = "#BDC8D6";
            }

            else if (hours >= 15 && hours <= 18) {
            document.body.style.backgroundColor = "#5A7699";
            }

            else if (hours >= 19 && hours <= 21) {
              document.body.style.backgroundColor = "#234B64";
            }
            
            else {
            document.body.style.backgroundColor = "#3F1673";
            }
 
       }
    </script>
</body>
</html>
