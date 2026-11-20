FLAME – taal- en barcodescanner herstel (tussenversie)

Aangepast:
- Smart Coach-adviezen geven nu antwoord in de geselecteerde app-taal (Nederlands, Engels of Spaans).
- Coach-schema labels en gegenereerde preview zijn gelokaliseerd. Een open preview wordt vernieuwd bij taalwijziging.
- Meer Coach-onderdelen toegevoegd aan de vertaalwoordenboeken.
- Barcodescanner vraagt expliciet de achtercamera aan, controleert veilige context en toont bruikbare foutmeldingen.
- ZXing-lader probeert twee CDN-bronnen met timeout; BarcodeDetector wordt gebruikt wanneer Android WebView dit ondersteunt.
- Barcode-invoer controleert op 8–14 cijfers en Open Food Facts-fouten worden afgehandeld.

BELANGRIJK: dit is een broncode-update, geen APK. De JavaScript-syntaxis is gecontroleerd. Een volledige Android-build en fysieke test van cameratoestemming/scannen moeten nog op een Android-toestel plaatsvinden. ZXing-fallback vereist internettoegang als BarcodeDetector niet beschikbaar is. Productopzoeken vereist internet en een product in Open Food Facts.
