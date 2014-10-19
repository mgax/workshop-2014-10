Argumente command-line
======================

Folosim biblioteca `argparse
<https://docs.python.org/2/library/argparse.html>`_ din standard library. Mai
există `getopt` (vechi) și `optparse` (subset al `argparse`).

Exemplu cu un singur argument:

.. code:: python

    import argparse

    parser = argparse.ArgumentParser()
    parser.add_argument('foo')

    args = parser.parse_args()
    print args.foo

Exemplu de flag. Dacă lipsește, valoarea este ``False``. Dacă este prezent,
valoarea este ``True``.

.. code:: python

   import argparse

    parser = argparse.ArgumentParser()
    parser.add_argument('-f', action='store_true')

    args = parser.parse_args()
    print args.f


Exerciții
---------

1. Crează un program care afișează numărul de apariții ale cuvântului dat în
   textul "zen of python".

2. Crează un program care afișează factorialul unui număr dat.

3. Crează un program care primește ca argument numărul de nopți și afișează
   prețul cazării. Prețul pe noapte este 100 iar curățenia costă 60.

4. Adaugă un flag, dacă se aplică TVA.

5. Adaugă un argument inițial, numele pensiunii pentru care se calculează
   prețul. Folosește lista de pensiuni de la capitolul anterior.

6. Adaugă helptext la toate opțiunile.
