# CodeLearnin
 BasicCodes
Anwendung mit grundlegender Website mit mehreren Buttons mit verschiedenen Funktionen

Button Design
    padding:            Abstand vom Text zum Rand vom Button
    font-size:          Größe Knopf
    background-color:   Farbe vom Knopf
    color:              Schriftfarbe
    border-width:       Rahmenbreite
    border-style:       Stil des Rahmens
    border-color:       Rahmenfarbe
    border-radius:      Abrundung der Ecken
    cursor:             Art des Cursors auf dem Knopf

Im Code wird ein Eingabefeld zugefügt, mit dem mit vorgegebenen Zahlen eine Rente berechnet werden kann (EP, ZF, RF, ARW)
Im selben Container wird nach Bestätigung der Eingabe eine Berechnung durchgeführt, die in einem neuen Fenster innerhalb des Containers
angezeigt werden soll.

Alter Code für Eingabe der Variablen, sollte neuer Code nicht funktionieren:
    <div class="container">
        <label for="v1">Entgeltpunkte:</label>
        <input type="text" id="v1Input">
        
        <label for="v2">Zugangsfaktor:</label>
        <input type="text" id="v2Input">

        <label for="v3">Rentenartfaktor:</label>
        <input type="text" id="v3Input">

        <label for="v4">Aktueller Rentenwert:</label>
        <input type="text" id="v4Input">

        <button onclick="setVariables()">Variablen festlegen</button>
        <button onclick="openResultWindow()">Ergebnis anzeigen</button>
    </div>
    
        <script>
                var v1Input = document.getElementById("v1Input");
                var v2Input = document.getElementById("v2Input");
                var v3Input = document.getElementById("v3Input");
                var v4Input = document.getElementById("v4Input");

                console.log("Entgeltpunkte: " + v1);
                console.log("Zugangsfaktor: " + v2);
                console.log("Rentenartfaktor: " + v3);
                console.log("Aktueller Rentenwert: " + v4);

                var v1 = v1Input.value;
                var v2 = v2Input.value;
                var v3 = v3Input.value;
                var v4 = v4Input.value;

                if (!isValidDecimal(v1, 4)) {
                    alert("Dies ist kein gültiger Wert für Entgeltpunkte");
                    return;
                }

                if (!isValidDecimal(v2, 4)) {
                    alert("Dies ist kein gültiger Wert für den Zugangsfaktor");
                    return;
                }

                if (!isValidDecimal(v3, 4)) {
                    alert("Dies ist kein gültiger Wert für den Rentenartfaktor");
                    return;
                }

                if (!isValidDecimal(v4, 4)) {
                    alert("Dies ist kein gültiger aktueller Rentenwert");
                    return;
                }
            
            function calculateResults(v1, v2, v3, v4) {
                var result = parseFloat(v1) * parseFloat(v2) * parseFloat(v3) * parseFloat(v4);
                return result;
            }

            function setVariables() {
                var v1 = v1Input.Value;
                var v2 = v2Input.Value;
                var v3 = v3Input.Value;
                var v4 = v4Input.Value;
        
                var calculationResult = calculateResults(v1, v2, v3, v4);
                openResultWindow(calculationResult);
            }
            

            function openResultWindow(result)  {
            var resultWindow = window.open("", "Berechnungsergebnis", "width=400,height=300");
            resultWindow.document.write("<h2>Berechnungsergebnis<h2>");
            resultWindow.document.write("<p>Das Ergebnis der Berechnung ist: " + result + "</p>");
            resultWindow.document.close();
        }
       
        </script>

Ausgabebutton für Berechnung muss noch gemacht werden