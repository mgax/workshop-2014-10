virtualenv, pip
---------------

Dacă avem nevoie de biblioteci în afara colecției de biblioteci standard,
este recomandat să creem un `virtualenv
<http://virtualenv.readthedocs.org/en/latest/>`_ specific proiectului, și să
instalăm acolo pachetele, folosind `pip
<http://pip.readthedocs.org/en/latest/>`_. Vom rula programele folosind
executabilul ``python`` din virtualenv:

.. code:: sh

    $ virtualenv ./venv
    $ ./venv/bin/pip install pathlib
    $ ./venv/bin/python myscript.py

Comanda ``pip`` poate rula în mod offline dacă avem pachetele downloadate
într-un director local:

.. code:: sh

    $ pip install pathlib -f /path/to/dist

Tot procesul de instalat uneltele de packaging este descris pe pagina
https://python-packaging-user-guide.readthedocs.org/en/latest/current.html.


openpyxl
--------

`openpyxl` este o bibliotecă cu care putem citi și modifica documente în
format `xlsx` (Excel 2007).

Citire din `xlsx`:

.. code:: python

    from openpyxl import load_workbook
    wb = load_workbook('test.xlsx')

    # listăm numele worksheet-urilor
    print wb.get_sheet_names()

    # deschidem un worksheet după nume
    ws = wb.get_sheet_by_name('Sheet 1')

    # citim valoarea unei celule
    print ws['A1']

    # iterăm prin rânduri
    for row in ws.rows
        print row


Scriere în `xlsx`:

.. code:: python

    from openpyxl import Workbook
    wb = Workbook()
    ws = wb.active

    # scriem într-o celulă
    ws['A1'] = 42

    # adăugăm un rând nou
    ws.append([1, 2, 3])

    # adăugăm o dată
    import datetime
    ws['A2'] = datetime.datetime.now()

    # salvăm fișierul
    wb.save("sample.xlsx")

Pentru descrierea completă a funcționalităților, vezi `documentația pachetului
openpyxl <https://openpyxl.readthedocs.org/en/latest/>`_.


Exerciții
---------

1. Crează un `virtualenv` în home-ul tău. Instalează pachetul ``openpyxl``.

2. Transformă  fișierul `migrari.xlsx <./migrari.xlsx>`_ în CSV folosind
   modulele `openpyxl` și `csv`.

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
