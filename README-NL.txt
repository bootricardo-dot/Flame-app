FLAME – Android-project (GitHub APK build)

INHOUD
- Android WebView-app met de FLAME-interface.
- Foodlogboek met handmatige invoer en zoeken via Open Food Facts.
- Trainingslogboek met oefening, datum, gewicht, sets en herhalingen.
- Vergelijking van laatste registraties per oefening en berekening van trainingsvolume.
- Taalkeuze Nederlands, Engels en Spaans.
- Lokale opslag op het apparaat.

APK BOUWEN VIA GITHUB (ook mogelijk vanaf een Android-telefoon)
1. Download dit ZIP-bestand en pak het uit.
2. Maak op github.com een nieuw leeg repository aan.
3. Upload de INHOUD van de map FLAME-Android naar de hoofdmap van het repository. Maak daarna in GitHub via Add file > Create new file het bestand .github/workflows/build-apk.yml aan en plak de workflow hieronder uit het meegeleverde project.
4. Open het tabblad Actions en schakel Actions in als GitHub daarom vraagt.
5. Kies 'Build FLAME APK' en druk op 'Run workflow'. Je kunt ook een commit naar main pushen.
6. Wacht tot de workflow groen is.
7. Open de geslaagde workflow-run, ga naar Artifacts en download FLAME-debug-apk.
8. Pak het artifact-ZIP-bestand uit. Daarin staat app-debug.apk.
9. Open app-debug.apk op je Samsung en geef zo nodig toestemming om vanuit die bron te installeren.

TECHNISCHE VEREISTEN
- Android Gradle Plugin 8.7.3
- Gradle 8.9
- Java 17
- Android SDK platform 35 (wordt in de GitHub runner geïnstalleerd via de Android build tooling/runner setup indien vereist)

BELANGRIJKE BEPERKINGEN
- Dit is een debug-APK voor testen, geen Play Store-release.
- Product zoeken gebruikt de Open Food Facts API en vereist internet.
- Barcode-scannen gebruikt de WebView BarcodeDetector API. Niet elke Android/WebView-versie ondersteunt deze API; in dat geval moet je de zoekfunctie gebruiken. Cameratoestemming is vereist.
- Voedingswaarden zijn afhankelijk van de volledigheid en juistheid van Open Food Facts-productgegevens.
- De app slaat gegevens lokaal op in WebView-opslag. Verwijderen van appgegevens of herinstalleren kan lokale gegevens wissen; maak daarom zelf back-ups.
- Taalvertalingen zijn gedeeltelijk; sommige dynamisch gegenereerde of foutmeldingen kunnen nog Nederlands tonen.
- De progressievergelijking vergelijkt registraties per oefeningsnaam; voer dezelfde oefeningsnaam consequent in.
- Er is geen account/cloudsynchronisatie en geen automatische fotoherkenning van maaltijden.

PROJECT STRUCTUUR
Open FLAME-Android als projectmap in Android Studio als je lokaal wilt bouwen.
De GitHub Actions-workflow staat in .github/workflows/build-apk.yml.


WORKFLOW-INHOUD (plak in .github/workflows/build-apk.yml)

name: Build FLAME APK

on:
  workflow_dispatch:
  push:
    branches: [ main ]

permissions:
  contents: read

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Check out source
        uses: actions/checkout@v4

      - name: Set up Java 17
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '17'

      - name: Set up Gradle 8.9
        uses: gradle/actions/setup-gradle@v4
        with:
          gradle-version: '8.9'

      - name: Build debug APK
        working-directory: .
        run: gradle --no-daemon assembleDebug

      - name: Upload APK
        uses: actions/upload-artifact@v4
        with:
          name: FLAME-debug-apk
          path: app/build/outputs/apk/debug/app-debug.apk
          if-no-files-found: error
          retention-days: 30

