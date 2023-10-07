Mein kunterbunter Bastelkasten

Cookie-Code
__________________

var "xxxx" = "CookieName"; 
    -> Erstellung einer Variable ("xxxx"), die den Namen ("CookieName") des Cookies festlegt

var name = "xxxx" + "=";
    -> Erstellung einer Variable namens 'name', die Namen des Cookies mit einem Gleichheitszeichen enthält, damit später danach gesucht werden kann

var decodedCookie = decodeURIComponent(document.cookie);
    -> Inhalt des 'document.cookie' wird dekodiert und in neuer Variable names 'decodedCookie' gespeichert

var cookieArray = decodedCookie.split(';');
    -> 'decodedCookie' string wird in Array aus Cookie-Strings aufgeteilt
    -> jedes Element im Array entspricht einzelnem Cookie

for (var i = 0; i < cookieArray.length; i++) {
    -> Beginn der Schleife, die von Cookie Elementen durchlaufen wird, um den gewünschten zu finden

var cookie = cookieArray[i];
    -> aktuelles Cookie aus dem Array wird in neuer Variable namens 'cookie' gespeichert 

while (cookie.charAt(0) == ' ') {
    cookie = cookie.substring(1);
}
    -> Schleife entfernt Leerzeichen am Anfang des cookie-strings

if (cookie.indexOf(name) == 0) {
    -> Überprüfung, ob cookie-string mit gesuchtem Namen ('name') beginnt
    -> wenn ja wird folgender Block ausgeführt

var cookieValue = cookie.substring(name.length, cookie.length);
    -> wenn gesuchter Cookie gefunden wurde, wird hier Wert aus dem Cookie-String extrahiert und in der Variable 'cookieValue' gespeichert

alert("Der Wert des Cookies ist " + cookieValue);
    -> alert Fenster zur Ausgabe des Wertes

return;
}
}
    -> nach Anzeige des gesuchten Cookies wird die Schleife beendet

Beispielcode Gesamt:
document.getElementById("CookieMonster").addEventListener("click", function () {
    var PEPKEZ = "IhrCookieName"; // Geben Sie hier den Namen Ihres Cookies an
    var name = PEPKEZ + "=";
    var decodedCookie = decodeURIComponent(document.cookie);
    var cookieArray = decodedCookie.split(';');
    for (var i = 0; i < cookieArray.length; i++) {
        var cookie = cookieArray[i];
        while (cookie.charAt(0) == ' ') {
            cookie = cookie.substring(1);
        }
        if (cookie.indexOf(name) == 0) {
            var cookieValue = cookie.substring(name.length, cookie.length);
            alert("Der Wert des Cookies " + PEPKEZ + " ist: " + cookieValue);
            return;
        }
    }
    alert("Der Cookie wurde nicht gefunden");
____________________________________________________________________________________________________________________________________________________-

Beispiel für checkCookie

<script>
            function checkCookie() {
                let user = getCookie("PEPKEZ");
                if (user != "") {
                    alert("Es sind " + PEPKEZ);
                } 
                else {
                    alert("Kaputt diese")
                }

            }
        </script>
_____________________________________________________________________________________________
Leerer Cookie, der erstellt wird, wenn die Seite geladen wird


        <button id="Erstellen">Erstellen</button>

 window.onload = function erstellen() {
                var cname = "KEP";
                var cvalue;
                document.cookie = cname + cvalue;    
            };
______________________________________________________________________________________________
Einfacher alert (kann nach Fertigstellung der Cookie Ausgabe gelöscht werden)

  alert("Der Wert des Cookies " + PEPKEZ + " ist: " + cookieValue); 