FLAME AI COACH – ECHTE AI-BACKEND INTEGRATIE

De AI Coach heeft nu twee echte AI-functies via een beveiligde backend:
- Persoonlijk weekschema genereren op basis van doelen, niveau, beschikbare tijd, apparatuur, oefeningencatalogus en recente trainingshistorie.
- Vragen stellen aan de AI Coach.
- Een gegenereerd schema blijft een voorstel en wordt pas toegepast na jouw goedkeuring.

INSTALLATIE
1. Upload de volledige repository naar GitHub.
2. Deploy de map ai-backend als aparte Node.js 20+ webservice. Zie ai-backend/README-NL.txt.
3. Stel OPENAI_API_KEY als geheime omgevingsvariabele in op de backend-host. Stel eventueel OPENAI_MODEL in.
4. Test de backend via /health.
5. Open FLAME > Training > AI Coach. Vul het HTTPS-serveradres in bij AI-serveradres. Dit adres wordt lokaal op het toestel bewaard.
6. Genereer een schema of stel een vraag.

VEILIGHEID EN KOSTEN
De geheime sleutel staat niet in de Android-app of frontend. OpenAI API-verbruik kan kosten met zich meebrengen. Stel limieten in op je API-account. De meegeleverde backend is een basisimplementatie; voeg voor publiek gebruik authenticatie, rate limiting, loggingbeleid en een strikte CORS-origin toe.

CONTROLE
De JavaScript- en Node.js-syntaxis zijn gecontroleerd. De AI kan pas echt antwoorden nadat de backend is gedeployed en voorzien van een geldige API-sleutel. De volledige Android-build en een live API-test zijn nog niet uitgevoerd.
