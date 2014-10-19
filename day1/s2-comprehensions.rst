Expresii care generează liste și dicționare
===========================================

Putem crea o listă sau un dicționar folosind o sintaxă simplificată numită
"list comprehension" sau "dict comprehension".

.. code:: python

    print [n * 2 for n in range(10)]
    # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

    print {n: n * 2 for n in range(3)}
    # {0: 0, 1: 2, 2: 4}

Expresia poate conține și o condiție:

.. code:: python

    print [n for n in range(10) if n % 3 != 0]
    # [1, 2, 4, 5, 7, 8]


Exerciții
---------

1. Plecând de la dicționarul de la capitolul precedent, generează o listă cu
   numele firmelor, folosind "list comprehension". Pe poziția N din listă se
   va regăsi numele firmei de la acel etaj, sau valoarea ``None`` dacă etajul
   este liber.

2. Folosind lista de la exercițiul `1`, și funcția ``enumerate``, generează
   o listă de perechi ``(etaj, nume_firma)`` care să conțină doar etajele
   ocupate.

3. Transformă textul "zen of python" într-o listă de cuvinte. Generează o
   listă cu indecșii, în lista de cuvinte, la care apare cuvântul "better".

   Hint: funcția ``text.split()``, fără argumente, împarte după whitespace.
   Primele două numere din lista generată ar trebui să fie 2 și 7.

4. Plecând de la lista cu perechi ``(nume_firma, etaj)``, generează un
   dicționar, folosind "dict comprehension", în care cheia este etajul și
   valoarea este numele firmei.

5. Calculăm un preț, "chirie lunară", ca suma codurilor ASCII ale literelor
   din numele firmei (hint: funcțiile ``sum``, ``ord``). Generează un
   dicționar în care cheia este numele firmei și valoarea este prețul pe
   12 luni. Calculează venitul anual al proprietarului clădirii, adăugând TVA
   24%.

6. Afișează cele 3 firme cu cele mai mari chirii. Hint: o listă de perechi va
   fi sortată în funcție de prima valoare a fiecărei perechi.

7. Construiește un dicționar pentru decodarea `cifrului Cezar
   <http://en.wikipedia.org/wiki/Caesar_cipher>`_. Decodează mesajul
   ``'f pelria rpb molmbo bkzovmqflk kbuq qfjb'``.
