Funcții și clase
================

Funcția este o secvență de cod care poate fi apelată în mod repetat.

.. code:: python

    def foo(n):
        return "you called 'foo' with argument %s" % n

    print foo(13)


Argumentele funcției pot fi transmise după nume și pot avea valori default.

.. code:: python

    def say_hello(name, greeting="Hello", count=1)
        for _ in range(count):
            print "%s, dear %s" % (greeting, name)

    say_hello("friend")
    # Hello, dear friend

    say_hello("friend", "Hi", 3)
    # Hi, dear friend
    # Hi, dear friend
    # Hi, dear friend

    say_hello("you", count=3)
    # Hello, dear you
    # Hello, dear you
    # Hello, dear you

    say_hello(greeing="Hi", name="dude")
    # Hi, dear dude


Clasele sunt folositoare când vrem să izolăm un anumit tip de informație
(the state) și să o prelucrăm prin intermediul a câteva funcții (interfață,
API).

Funcțiile se numesc metode, și primesc, ca prim argument, obiectul curent
``self``. La crearea unui obiect se apelează funcția ``__init__``.

.. code:: python

    class Person:

        def __init__(self, name):
            self.name = name

        def greet(self, greeting="Hello"):
            print "Hello, %s" % self.name

    mihai = Person("Mihai")
    mihai.greet()
    # Hello, Mihai
    mihai.greet("Hi")
    # Hi, Mihai


Exerciții
---------

1. Scrie câte o funcție pentru algoritmii `cmmdc`, `cmmmc`, `factorial`.

2. Scrie o funcție care returnează un dicționar cu frecvența cuvintelor
   dintr-un text dat.

3. Scrie o funcție care primește un text și îl returnează cu liniile ordonate
   alfabetic.

4. Scrie o funcție `pret` care calculează prețul cazării la o pensiune.
   Argumentele vor fi numărul de nopți, prețul pe noapte, costul curățeniei
   (se aplică o singură dată, indiferent de durata șederii), și dacă se
   aplică TVA (argument boolean opțional).

5. Scrie o clasă `Pensiune` care să rețină prețul pe noapte și taxa de
   curățenie. Clasa va avea o metodă `pret` care primește ca argument doar
   numărul de nopți și, opțional, dacă se aplică TVA.

6. Crează un dicționar cu pensiuni:

   .. code:: python

        pensiuni = {
            "Ana": Pensiune(80, 50),
            "Bradul": Pensiune(100, 60),
            "Cocosul": Pensiune(120, 65),
        }

   Crează și o listă cu 10 rezervări la pensiuni, sub forma
   ``(nume_pensiune, nopti, tva)``. Afișează prețul pentru fiecare rezervare
   și venitul total al fiecărei pensiuni.

7. Adaugă o funcție `print_oferta` la pensiune. Aceasta va afișa un text care
   descrie prețurile pensiunii.

8. Crează o clasă care codează și decodează conform cifrului Cezar. Numărul
   de poziții al deplasării să fie configurabil.
