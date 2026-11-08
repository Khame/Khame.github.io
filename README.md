# Khame.github.io

Strona domowa: <https://khame.github.io/> — pakiety i programy dla Void Linuxa, po polsku i po angielsku.

W repo są tylko gotowe pliki HTML. Nie ma builda, menedżera pakietów ani frameworka: GitHub Pages serwuje katalog główny gałęzi `main`, więc każdy push od razu publikuje stronę.

## Struktura

| Ścieżka | Rola |
| --- | --- |
| `index.html` | Strona polska, kanoniczny adres `/` |
| `en/index.html` | Strona angielska, kanoniczny adres `/en/` |
| `assets/` | Zrzut menu sensei310-tray (AVIF + WebP) i podgląd do social mediów (JPEG) |
| `ARCHITECTURE.md` | Opis budowy strony i zasad utrzymania |

## Podgląd lokalny

```sh
python3 -m http.server 8000
```

Potem <http://localhost:8000>. Strona otworzy się też prosto z dysku, ale wtedy adresy kanoniczne i linki językowe nie działają poprawnie.

## Jak to działa

- Język wybiera przeglądarka: polski → PL, każdy inny → EN. Ręczny wybór z przełącznika PL/EN zapisuje się w `localStorage["khame-language"]`.
- Wejście bezpośrednio na `/en/` zostaje po angielsku, bo przekierowanie odpala się tylko na stronie polskiej.
- Każda strona jest samodzielna: CSS i JavaScript siedzą w środku pliku. Zmiana treści wymaga edycji obu plików, `index.html` i `en/index.html`.

## Publikacja

Push do `main`. GitHub Pages buduje z gałęzi `main`, katalog `/`, bez osobnego kroku deploy.

## Licencja

Brak pliku licencji. Kod i treści tej strony są moje. Jeśli chcesz czegoś użyć, napisz.
