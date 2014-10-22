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
