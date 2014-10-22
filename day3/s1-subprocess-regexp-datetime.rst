Subprocess
----------

Pentru a executa programe externe folosim, din biblioteca ``subprocess``,
funcțiile ``check_call`` și ``check_output``. A doua funcție capturează
standard output al programului (dar nu și standard error) și îl returnează.

.. code:: python

    import subprocess
    out = subprocess.check_output(['ls', '-l'])
    print "`ls -l` returned %r" % out


Expresii regulate
-----------------

Python are un engine de expresii regulate implementat în modulul ``re``
din biblioteca standard.

.. code:: python

    import re
    m = re.search(r' are (.*)', "ana are mere")
    print m.group(1)


Dates, times
------------

Pentru operațiuni cu valori de timp, folosim biblioteca ``datetime``.

.. code:: python

    from datetime import datetime, timedelta
    now = datetime.now()
    now_txt = now.strftime('%Y-%m-%d %H:%M:%S')
    parsed = datetime.strptime('%Y-%m-%d %H:%M:%S')
    parsed == now

    in_2_hrs = now + timedelta(hours=2)


Exerciții
---------

0. Scrie un program care verifică dacă argumentul primit este o adresă de
   mail plauzibilă (conține un caracter ``@`` și numele de domeniu conține o
   extensie între 2 și 4 caractere).

0. Scrie un program care calculează data în care putem ridica un permis de
   conducere suspendat. Programul primește două argumente: data deciziei de
   suspendare în format ISO (dd-mm-yyyy) și numărul de zile de suspendare.
   Suspendarea propriu-zisă începe la 15 zile de la decizie.

0. Scrie un program care calculează vârsta unui fișier, exprimată în zile,
   ore și minute.

0. Scrie un program care crează un zip cu conținutul unui director. Folosește
   comanda externă ``zip``, chiar dacă există biblioteca `zipfile` în Python.

0. Scrie un program care rulează comanda ``uptime``, preia output-ul, și
   extrage numărul de utilizatori și cele 3 valori pentru load average.

0. Scrie un program care downloadează arhiva zip cu materialele de curs
   (``https://github.com/mgax/workshop-2014-10/archive/master.zip``),
   folosind comanda ``curl``, cu opțiunile ``-O`` (salvează răspunsul într-un
   fișier) și ``-L`` (follow redirects). După aceea, programul trebuie să
   listeze fișierele din arhivă (``unzip -l <filename>``), și să extragă numele
   de fișier, lungimea necomprimată, și data (ca obiect `datetime`) pentru
   fiecare fișier din arhivă.
