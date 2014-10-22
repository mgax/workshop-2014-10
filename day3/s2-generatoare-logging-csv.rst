Iteratoare, generatoare
-----------------------

Iteratorul este un obiect care produce o serie de valori. Acestea pot să vină,
de exemplu, dintr-o listă sau dintr-un fișier. Sunt utile atunci când vrem
să prelucrăm seria element cu element. Bucla `for` parcurge, întotdeauna,
un iterator.

Putem construi un iterator printr-o expresie asemănătoare cu
"list comprehension":

.. code:: python

    i = ("n=%d" % n for n in range(10))
    for v in i:
        print v

Sau putem scrie o funcție "generator":

.. code:: python

    def gen():
        for n in range(10):
            yield "n=%d" % n

    for v in gen():
        print v


Logging
-------

Python dispune de un sistem de logging în biblioteca standard.

.. code:: python

    import logging
    logging.basicConfig()
    logger = logging.getLogger('workshop')
    logger.warn("hello %s!", "world")
    try:
        0 / 0
    catch:
        logger.exception("operation failed")


CSV
---

Biblioteca ``csv`` ne ajută să citim și să generăm fișiere în format CSV
și TSV.

.. code:: python

    import csv

    with open('/tmp/workshop.csv', 'wb') as f:
        writer = csv.writer(f)
        writer.writerow(['n', 'n^3'])
        for c in range(10):
            writer.writerow([str(c), str(c ** 3)])

    with open('/tmp/workshop.csv', 'rb') as f:
        reader = csv.reader(f)
        for line in reader:
            print ', '.join(line)


Exerciții
---------

1. Scrie un program care citește un fișier CSV, verifică adresele de email
   din coloana "email", și scrie alt fișier CSV care conține doar rândurile
   cu adrese email valide.

2. Modifică programul astfel încât să citească de la standard input și să
   scrie la standard output. Acestea sunt disponibile ca fișiere ``sys.stdin``
   și ``sys.stdout`` după ce rulăm instrucțiunea ``import sys``.

3. Scrie o funcție de tip generator care produce înregistrări de forma
   ``[name, mime_type, size]`` pentru toate fișierele dintr-un director.
   Puteți afla mime-type-ul unui fișier rulând comanda
   ``file -bI <filename>``.

4. Preia rezultatul funcției generator și scrie-l într-un fișier CSV care
   să conțină un rând de header corespunzător.

5. Modifică programul astfel încât să genereze informație de logging: un mesaj
   de nivel INFO pentru începutul parcurgerii directorului, un mesaj de tip
   INFO pentru sfârșitul parcurgerii (care ne spune și numărul de fișiere
   vizitate), și câte un mesaj DEBUG pentru fiecare fișier vizitat.

6. Adaugă opțiuni la program care să configureze nivelul de logging. ``-v``
   (verbose) alege loglevel DEBUG, ``-q`` (quiet) alege loglevel WARN, și
   în mod normal nivelul de logging să fie INFO.

7. Modifică programele anterioare astfel încât să folosească
   ``csv.DictReader`` pentru citire și ``csv.DictWriter`` pentru scriere.

8. Modifică programul astfel încât să detecteze erori (de exemplu erori de
   permisiuni la citirea fișierelor), să le raporteze prin logging, și
   să continue execuția. Excepțiile se pot raporta folosind
   ``logger.exception("something failed")``; logger-ul va prelua informația
   despre excepția curentă.
