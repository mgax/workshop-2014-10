Exerciții
---------

1. Crează un `virtualenv` în home-ul tău. Instalează pachetul ``openpyxl``.

2. Transformă un fișier `xlsx` în CSV folosind modulele `openpyxl` și `csv`.

3. Generează un fișier `xlsx`, care să conțină o listă cu fișierele dintr-un
   director, împreună cu mărimea lor în bytes. Adaugă la sfârșit o celulă
   care face suma mărimilor fișierelor. Deschide fișierul cu Excel,
   LibreOffice sau Google Docs și verifică dacă a fost generat corect.

4. Adaugă în fișier un grafic cu valorile din coloana cu mărimea fișierelor.
   (https://openpyxl.readthedocs.org/en/latest/charts.html#creating-a-chart)

5. Modifică celula cu suma mărimilor, să apară "bold". Adaugă un chenar
   (border) în jurul zonei cu numele fișierelor și mărimea lor.

6. Generează un fișier `xlsx`, cu numele fișierelor și mărimea lor, dintr-un
   director cu foarte multe fișiere (de exemplu ``/usr``). Folosește metoda
   optimizată pentru generat fișiere mari
   (https://openpyxl.readthedocs.org/en/latest/optimized.html#optimized-writer).

7. Citește fișierul `xlsx` generat la pasul anterior. Folosește metoda
   optimizată pentru citit fișiere mari
   (https://openpyxl.readthedocs.org/en/latest/optimized.html#optimized-reader).
   Însumează, în Python, mărimile fișierelor, și afișează rezultatul.
