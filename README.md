![CI](https://github.com/grzegorz-aleksander-klementowski/zdanowicz-strona-sieciowa/actions/workflows/ci.yml/badge.svg)
![W3C Validation](https://github.com/grzegorz-aleksander-klementowski/zdanowicz-strona-sieciowa/actions/workflows/w3c-validation.yml/badge.svg)

# Zdanowicz Podnośniki

Marketingowa strona statyczna promująca wynajem podnośników koszowych dla firm i mieszkańców regionu Wojcieszów – Jelenia Góra. Layout opiera się na szablonie **Start Bootstrap Agency**, rozszerzonym o lokalne treści, zasoby zdjęciowe oraz dedykowane podstrony usługowe.

## Podgląd na żywo
- Strona główna: [https://zdanowicz-podnosniki.pl/](https://zdanowicz-podnosniki.pl/)
- Podstrona Jelenia Góra: [https://zdanowicz-podnosniki.pl/jelenia-gora.html](https://zdanowicz-podnosniki.pl/jelenia-gora.html)

## Najważniejsze elementy
- 🎯 **Personalizowane treści** – sekcje o usługach, referencjach i FAQ przygotowane pod lokalne zapytania SEO.
- 🗺️ **Lokale landing page’e** – dedykowana podstrona dla Jeleniej Góry z mapą dojazdu oraz CTA kierującymi do wyceny.
- 🧭 **Udoskonalony UX** – animacje „reveal on scroll”, efekt hover „lift”, przycisk powrotu do góry i responsywny układ.
- ✅ **Automatyczne testy jakości** – workflow GitHub Actions sprawdzający zgodność HTML/CSS z normami W3C.
- ♻️ **Automatyczna aktualizacja roku** – skrypty JS pobierają aktualny rok, eliminując ręczne poprawki w stopce.

## Stos technologiczny
- HTML5 + Bootstrap 5 (Start Bootstrap Agency)
- Niestylowany JS (ES5) dla interakcji i animacji
- Pojedynczy arkusz `css/styles.css` z nadpisaniami i efektami
- GitHub Pages / dowolny hosting statyczny (w repo znajduje się `CNAME`)

## Struktura projektu
- `index.html` – strona główna z sekcjami usług, portfolio, FAQ i kontaktem.
- `jelenia-gora.html` – landing page dla miasta i okolic.
- `css/styles.css` – arkusz oparty na szablonie Agency z dodatkowymi klasami UI/UX.
- `js/scripts.js` – logika: shrink nav, scrollspy, animacje wejścia, przycisk scroll-top, rok w stopce.
- `assets/` – zdjęcia, ikony, favicony.
- `sitemap.xml` – mapa witryny zgłaszana w Google Search Console.
- `.github/workflows/` – konfiguracje CI i walidacji W3C.

## Uruchomienie lokalne
1. Sklonuj repozytorium i przejdź do katalogu projektu.
2. Uruchom prosty serwer statyczny:
   ```bash
   python3 -m http.server 8080
   # lub
   npx --yes serve .
   ```
3. Otwórz w przeglądarce `http://localhost:8080/index.html` (podstronę znajdziesz pod `/jelenia-gora.html`).

> Strona nie wymaga backendu ani kompilacji – wystarczy dowolna współczesna przeglądarka.

## Kontrola jakości
- Workflow **W3C Validation** uruchamia kontener `ghcr.io/validator/validator` w celu sprawdzenia zgodności HTML i CSS.
- Te same kontrole możesz uruchomić lokalnie:
  ```bash
  docker run --rm -v "$(pwd)":/site ghcr.io/validator/validator:latest \
    /vnu-runtime-image/bin/vnu --errors-only --no-verbose \
    /site/index.html /site/jelenia-gora.html /site/css/styles.css
  ```
- Dodatkowe kontrole (opcjonalnie – wymagają własnych konfiguracji):
  ```bash
  npx --yes html-validator-cli --file index.html --format text
  npx --yes stylelint "css/**/*.css"
  npx --yes eslint "js/**/*.js"
  npx --yes prettier --check .
  ```

## Wdrożenie
Repozytorium działa jako strona statyczna (np. GitHub Pages + CNAME). Aby wdrożyć zmiany:
1. Zbuduj lub skopiuj zawartość repo do katalogu na serwerze/hostingu.
2. Upewnij się, że `sitemap.xml` oraz `robots.txt` zostały zaktualizowane (szczególnie po dodaniu nowych podstron).
3. W Google Search Console:
   - zgłoś nowy adres URL do indeksacji (np. `jelenia-gora.html`),
   - prześlij mapę witryny ponownie.

## Wkład i utrzymanie
- Aktualizując treści miejskie dodawaj nowe podstrony oraz linki w `sitemap.xml`.
- Wszystkie prace nad strukturą HTML/CSS warto weryfikować przez workflow W3C.
- Jeśli dodajesz narzędzia lintujące, rozbuduj `.github/workflows/ci.yml` i dopisz odpowiednie konfiguracje.

## Licencje i atrybucje
- Treści (tekst, zdjęcia, modyfikacje) © Piotr Zdanowicz Firma Usługowo Handlowa / Grzegorz Aleksander Klementowski, licencja MIT – patrz `LICENSE`.
- Szablon **Start Bootstrap – Agency v7.0.12** © Start Bootstrap LLC (MIT). Przy dalszym wykorzystaniu zachowaj oryginalne nagłówki licencyjne.

---
Jeśli masz pytania dotyczące wdrożenia, optymalizacji SEO lub kolejnych podstron (np. dla innych miast), śmiało otwórz zgłoszenie lub skontaktuj się z opiekunem projektu.
