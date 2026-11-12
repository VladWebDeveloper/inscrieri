# ASEM · Înscrieri 17–18 noiembrie 2026

Platformă publică găzduită pe **GitHub Pages**: https://vladwebdeveloper.github.io/inscrieri/

## Important

- Proiect **separat** în organizația VladWebDeveloper; nu atinge AlviTravel.
- Interfața păstrează designul original ASEM și formularele existente.
- Datele personale **nu sunt stocate în acest repository**. Înscrierile se salvează în Google Sheets prin backendul Google Apps Script, care continuă să deservească și vechiul URL.
- Sistemul verifică numărul de locuri sub un server-side lock, astfel încât ultimul loc nu poate fi depășit de înscrieri simultane.
- La Jeopardy, culorile deja rezervate dispar din formular și serverul refuză rezervări duplicate.
- `index.html` conține logo-urile ASEM integrate (fără cereri externe de imagine).

## Flux tehnic

1. Catalogul public (fără date personale): JSONP `?api=catalog`.
2. Înregistrare: POST `application/x-www-form-urlencoded` cu identificator aleatoriu de cerere.
3. Confirmare: JSONP `?api=status&requestId=...`, fără date personale în URL. Backendul deduplică cererile repetate.
4. Rezultatul este înscris în foaia **Inscrieri** din Google Sheets; câmpul P păstrează identificatorul tehnic al cererii.

Dacă Google Apps Script nu răspunde, formularul nu pretinde fals că înscrierea a reușit.

## Publicare

GitHub → Settings → Pages → Deploy from a branch → `main` → `/ (root)`.

## Păstrarea datelor

Nu adăuga în GitHub copii ale tabelului, adrese de email, numere de telefon sau alte date ale participanților. Tabelul rămâne privat.
