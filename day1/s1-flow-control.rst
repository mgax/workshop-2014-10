Tipuri de date, flow control
============================

Vom folosi câteva tipuri de date de bază: numere, șiruri de caractere, liste,
tuple, dicționare.

.. code:: pycon

    >>> 1 + 1
    2

    >>> "as" + "df"
    'asdf'

    >>> l = [1, 2] + ["3"]
    [1, 2, '3']
    >>> len(l)
    3
    >>> l[0]
    1
    >>> l[-1]
    '3'

    >>> d = {1: "hi", "foo": 5}
    >>> d[1]
    'hi'
    >>> d['foo']
    5
    >>> len(d)
    2
    >>> d[3] = None
    >>> d
    {1: "hi", "foo": 5, 3: None}
    >>> d.keys()
    [1, 'foo', 3]]


Mai avem la dispoziție construcțiile ``if``, ``for`` și ``while``:

.. code:: python

    if a > 0:
        print 'da'
    else:
        print 'nu'

    for c in [1, 3, 5, 7]:
        print "c = %s" % c

    n = 0
    while True:
        print n
        n += 1
        if n > 5:
            break


Exerciții
---------

Rezolvă fiecare exercițiu într-un fișier separat.

1. Afișează mesajul ``"Hello world"`` de 100 de ori.

3. Pentru numerele de la 0 la 120, afișează câte un mesaj de forma
   ``"Numarul X are N cifre."``

2. Calculează `cmmdc
   <http://en.wikipedia.org/wiki/Monte_Carlo_method#Introduction>`_, `cmmmc
   <http://en.wikipedia.org/wiki/Monte_Carlo_method#Introduction>`_ al
   numerelor 2273321 și 4881557.

4. Numără de câte ori apare fiecare cuvânt în textul "zen of python". Afișează
   un raport, pe fiecare linie să fie câte un cuvânt și numărul de apariții.
   Poți copia textul în codul sursă al programului:

   .. code:: python

        text = """\
        Beautiful is better than ugly.
        Explicit is better than implicit.
        ...
        """

5. Ordonează alfabetic liniile din textul "zen of python".

6. În textul "zen of python", înlocuiește cuvintele `better` și `should` cu
   variantele lor upper-case.

7. Plecând de la o listă de perechi ``(nume_firma, etaj)``, generează un
   dicționar în care cheia este etajul și valoarea este numele firmei.
   Clădirea are 10 etaje; folosește dicționarul ca să afișezi etajele goale.

   .. code:: python

        companies = [
            ("Pixar", 2),
            ("Disney", 4),
            ("Warner Bros.", 9),
            ("Universal", 5),
            ("Reception", 0),
            ("Studio Ghibli", 8),
            ("DreamWorks", 6),
        ]

8. Estimează valoarea lui Pi folosind metoda Monte Carlo. Algoritmul este
   descris în `pagina de pe Wikipedia
   <http://en.wikipedia.org/wiki/Monte_Carlo_method#Introduction>`_. Pentru a
   genera numere random, folosește funcția ``random()``:

   .. code:: python

      from random import random
      print random()
