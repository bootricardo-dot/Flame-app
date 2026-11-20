# FLAME – bijgewerkte broncode

Deze versie bevat:
- taalkeuze bij de eerste start (Nederlands, English, Español);
- taal wijzigen via Profiel;
- uitgebreidere vertalingen voor de hoofdschermen, instellingen, formulieren en veelvoorkomende meldingen;
- waterregistratie in stappen van 250 ml met toevoegen en verwijderen;
- koppeling met de openbare wger-oefeningendatabase voor beschikbare oefeningsafbeeldingen.

## Belangrijke teststatus
- De JavaScript in `app/src/main/assets/www/index.html` is gecontroleerd met `node --check`.
- Een volledige Android APK-build en praktijktest op een Android-toestel zijn in deze omgeving niet uitgevoerd: Gradle/Android SDK zijn hier niet beschikbaar.
- De live beschikbaarheid van oefeningsafbeeldingen is hier niet bevestigd omdat de externe wger-server vanuit deze omgeving niet bereikbaar was. De app gebruikt een terugval-icoon als er geen afbeelding geladen kan worden.
- Teksten die de gebruiker zelf invoert (zoals eigen oefeningnamen) blijven in de ingevoerde taal.

## APK bouwen
Upload de inhoud van deze map naar de hoofdmap van de GitHub-repository `Flame-app` en laat de GitHub Actions-workflow `Build FLAME APK` uitvoeren. Download daarna het artifact `FLAME-debug-apk`.
