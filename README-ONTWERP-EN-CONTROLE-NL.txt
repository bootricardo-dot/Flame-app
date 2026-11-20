FLAME v1.2 – ontwerpupdate

Deze update voegt een visuele premium-laag toe aan de bestaande FLAME-interface:
- donker zwart/antraciet kleurgebruik met rode accenten
- vernieuwde kaarten, knoppen, tabbladen, invoervelden en navigatie
- verbeterde typografie, tussenruimte, randen en schaduwen
- compactere mobiele weergave voor smalle schermen
- bestaande vijf hoofdonderdelen behouden: Vandaag, Voeding, Training, Progressie en Profiel
- bestaande Training-subtabs behouden: Schema, Oefeningen, Historie en Smart Coach

Controle uitgevoerd:
- JavaScript-bron uit index.html geëxtraheerd en `node --check` geslaagd.
- HTML-ID's gecontroleerd op dubbele waarden: geen duplicaten gevonden.
- projectbestanden en GitHub Actions-workflow aanwezig.
- ZIP-archief wordt na het maken gecontroleerd.

Niet uitgevoerd / nog handmatig testen:
- volledige Android APK-build: Gradle is niet beschikbaar in deze omgeving.
- echte Android-toesteltest, camera/barcodescanner en runtime-permissies.
- alle interacties en vertalingen end-to-end.
- individuele oefeningsfoto's zijn niet in deze ontwerpupdate toegevoegd; de bestaande oefeningencatalogus en weergave blijven behouden.

Bouwen:
Upload de inhoud van deze map naar de hoofdmap van de GitHub-repository en laat de bestaande workflow “Build FLAME APK” uitvoeren.
