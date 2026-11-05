# tesla-pagina

Een klein openbaar adres voor de Tesla-koppeling van Core (4.3.0). De site van Energie thuis op Base44 is privé
(alles vraagt om inloggen), dus Tesla kan daar niet kijken. Deze map zet je als geheel op GitHub Pages, in een
openbare repo met de naam `roelvveen-alt.github.io` (dan staat hij op `https://roelvveen-alt.github.io/`).

- `.well-known/appspecific/com.tesla.3p.public-key.pem`: de openbare sleutel. Tesla kijkt hier bij het aanmelden
  van de app (partner_accounts). Alleen de openbare helft staat hier. De privésleutel is bij het maken meteen
  weggegooid en staat nergens: die is alleen nodig om de auto commando's te sturen, en dat doet Core nooit (alleen
  lezen). Ooit wel commando's? Dan een nieuw paar maken en deze sleutel vervangen.
- `tesla/index.html`: de pagina waar Tesla na het inloggen naartoe gaat (het redirect-adres
  `https://roelvveen-alt.github.io/tesla/`). Hij laat de code uit de adresbalk zien met een knop "Kopieer", zodat je
  hem in Core plakt. Geen scripts van buiten, niets bewaard, niets doorgestuurd.
- `.nojekyll`: zodat GitHub Pages de map `.well-known` meeneemt.

Zie `node brug.mjs tesla` (brug/teslaInstellen.mjs) en `brug/tesla.mjs`.
