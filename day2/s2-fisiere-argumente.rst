Fișiere
-------

Putem deschide fișiere pentru scriere folosind modul `wb`. Nu uita să
închizi fișierul la sfârșit.

.. code:: python

    f = open('out.txt', 'wb')
    f.write("hello, ")
    f.write("world\n")
    f.close()

Dacă lucrăm cu fișiere mari, nu este eficient să le încărcăm complet în
memorie, și atunci putem să le prelucrăm linie cu linie:

.. code:: python

    f = open('out.txt', 'rb')
    for line in f:
        print "%d caractere" % len(line)
    f.close()


Argumente command-line
----------------------

Preluăm argumentele command-line, primite de programul nostru, folosind
biblioteca `argparse <https://docs.python.org/2/library/argparse.html>`_
din standard library. Mai există `getopt` (vechi) și `optparse` (subset
al `argparse`) pe care nu le vom folosi.

Exemplu cu un singur argument:

.. code:: python

    import argparse

    parser = argparse.ArgumentParser()
    parser.add_argument('foo')

    args = parser.parse_args()
    print args.foo

Putem cere un număr variabil de argumente (de exemplu o listă de fișiere
care trebuie prelucrate). ``nargs='*'`` înseamnă oricâte valori;
``nargs='+'`` înseamnă minim o valoare.

.. code:: python

    import argparse

    parser = argparse.ArgumentParser()
    parser.add_argument('files', nargs='+')

    args = parser.parse_args()
    print args.files

Exemplu de flag. Am specificat ``action='store_true'``, așa că, dacă flag-ul
este prezent, `f` are valoarea ``True``, altfel este ``False``.

.. code:: python

    import argparse

    parser = argparse.ArgumentParser()
    parser.add_argument('-f', action='store_true')

    args = parser.parse_args()
    print args.f


Exerciții
---------

1. Crează un program, care afișează conținutul unui singur director,
   folosind funcția ``ls`` de la capitolul precedent.

2. Modifică programul astfel încât să accepte zero sau mai multe argumente;
   dacă primește zero, afișează conținutul directorului curent; dacă primește
   mai multe, apelează funcția ``ls`` pentru fiecare din ele.

3. Adaugă opțiunile ``-F`` (pentru "classify") și ``-R`` (pentru "recursive")
   la programul de mai sus.

4. Crează un program de tip ``cat``, care primește unul sau mai multe fișiere
   ca argumente, le citește pe rând, linie cu linie, și le afișează.

5. Adaugă o opțiune la programul ``cat``, de forma ``--out /path/to/out.txt``,
   care direcționează output-ul către un fișier.

6. Crează un program, pe baza funcției ``grep`` din capitolul precedent, care
   primește ca argumente: cuvântul (``needle``), și o listă de fișiere și
   directoare în care trebuie să caute. Pentru directoare se va face căutare
   recursivă.

7. Adaugă documentație (help) la programele de mai sus și la argumentele și
   opțiunile lor.
