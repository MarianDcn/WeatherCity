# Neon Nocturn

Un oraș cyberpunk în pixel art, privit de la fereastra unui apartament. Scena e conectată la realitate: ora, răsăritul, apusul și vremea vin din locația ta.

- **Ora locală** decide cerul (noapte, zori, zi, apus) și ferestrele: se aprind treptat după apus și se sting una câte una până spre 3 noaptea. Câțiva se trezesc devreme, iar unele birouri rămân aprinse peste program.
- **Vremea reală** (Open-Meteo, fără cheie API), actualizată la 10 minute. Scena nu folosește doar codul meteo, ci valorile măsurate: intensitatea ploii în mm/h, ninsoarea în cm/h, vizibilitatea în metri (pentru pâclă și ceață), acoperirea cu nori, viteza și direcția vântului, rafalele, umiditatea și temperatura.
- **16 condiții:** senin, parțial noros, înnorat, pâclă, ceață densă, burniță, ploaie, ploaie torențială, ploaie înghețată (polei), lapoviță, ninsoare, viscol, furtună, furtună cu grindină, vânt puternic, caniculă. Fiecare are efecte proprii: grindină care ricoșează pe geam, chiciură pe sticlă la ger, geam aburit la umiditate mare, frunze și hârtii purtate de vânt, rafale care pulsează, cer încins la caniculă.
- **Card meteo** pe PC (panou lângă ceas) și pe telefon (panou jos care se deschide la atingere): temperatură și senzație termică, max/min, nowcast pe 15 minute („Ploaia se oprește în ~30 min”), vânt cu direcție și rafale, umiditate și punct de rouă, precipitații, vizibilitate, presiune, indice UV, prognoză pe 24 de ore cu iconițe pixel art și o bară răsărit–apus.
- **Detalii vii:** mașini zburătoare (trafic mai rar noaptea târziu), o navă cu ecran care afișează orașul, temperatura și ora, un billboard cu ceas, neoane care pâlpâie (unele se închid după 3), reflectoare, luna cu faza reală, picături pe geam, abur din cană și o pisică pe pervaz.
- **Sunet ambiental** generat în browser (ploaie, oraș, vânt, tunete), pornit din buton.

Totul e un singur fișier `index.html`, fără build și fără dependențe.

## Publicare pe GitHub Pages

1. Creează un repo nou, de exemplu `neon-nocturn`.
2. Urcă `index.html` (și opțional acest README) în rădăcina repo-ului.
3. **Settings → Pages → Build and deployment:** Source = *Deploy from a branch*, Branch = `main`, folder `/ (root)` → Save.
4. După un minut, pagina e la `https://<utilizator>.github.io/neon-nocturn/`.

GitHub Pages servește prin HTTPS, deci geolocația din browser funcționează. Dacă vizitatorul refuză permisiunea, scena pornește cu Galați.

## Comenzi

| Tastă | Acțiune |
|---|---|
| `H` | ascunde / arată interfața |
| `S` | sunet on/off |
| `F` | ecran complet |
| `D` | panoul de setări |

Interfața dispare singură după câteva secunde fără mișcare (se poate opri din setări).

## Parametri în URL

| Parametru | Exemplu | Efect |
|---|---|---|
| `time` | `?time=03:30` | oră fixă |
| `timelapse` | `?timelapse` | 24 de ore în 2 minute |
| `weather` | `?weather=blizzard` | `clear`, `partly`, `cloudy`, `mist`, `fog`, `drizzle`, `rain`, `heavy`, `freezing`, `sleet`, `snow`, `blizzard`, `hail`, `storm`, `windy`, `heat` |
| `city` | `?city=Tokyo` | alt oraș (ora și vremea de acolo) |
| `lat`, `lon`, `name` | `?lat=44.43&lon=26.10&name=București` | coordonate exacte |
| `hud` | `?hud=0` | fără interfață (mod wallpaper) |
| `seed` | `?seed=42` | alt oraș generat |

Exemplu: `?city=Tokyo&weather=storm&time=23:00`

## Ca wallpaper animat

**Wallpaper Engine** (Steam) sau **Lively Wallpaper** (gratuit, Windows) acceptă pagini web ca fundal. Folosește linkul GitHub Pages cu `?hud=0`.

## Date

- Vreme, răsărit, apus și geocodare: [Open-Meteo](https://open-meteo.com) (gratuit pentru uz necomercial).
- Numele orașului din coordonate: BigDataCloud reverse geocoding (client-side).
- Font: VT323 (Google Fonts).
