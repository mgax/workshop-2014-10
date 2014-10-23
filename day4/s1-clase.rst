Clase
-----

Clasele sunt folositoare când vrem să izolăm un anumit tip de informație
(the state) și să o accesăm prin intermediul a câteva funcții (interfață,
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

1. Scrie o clasă ``DateFormat`` care primește la inițializare, și reține pe
   ``self``, un `format de dată
   <https://docs.python.org/2/library/datetime.html#strftime-strptime-behavior>`_.
   Adaugă-i două metode, ``format(d)`` (care transformă un obiect datetime
   la string) și ``parse(t)`` (care transformă un obiect string la datetime).

2. Scrie o clasă ``DateRange`` care primește, la inițializare, o valoare
   `start` și o valoare `end`. Adaugă-i o metodă ``contains(d)`` care
   returnează ``True`` doar dacă argumentul se află în intervalul `[start,
   end)` (închis la `start`, deschis la `end`). Ce s-ar întâmpla dacă metoda
   s-ar numi ``__contains__``?

3. Scrie o clasă ``Hotel`` care primește, la inițializare, un preț pe noapte
   și un preț de curățenie. Adaugă o metodă ``price(dr)``, care primește o
   valoare de tip ``DateRange``, și returnează prețul de cazare pentru acel
   interval (numărul de nopți înmulțit cu prețul pe noapte la care se adaugă
   o singură dată taxa de curățenie).

4. Să presupunem că ``Hotel`` are o singură cameră. Modifică clasa să
   memoreze o listă de rezervări. Scrie o metodă ``book(dr)`` care adaugă
   o rezervare și altă metodă ``available(dr)`` care ne spune dacă hotelul
   este disponibil în acel interval.

5. Scrie o clasă ``CsvDictReader`` care citește rânduri dintr-un fișier CSV.
   Presupunem că primul rând al fișierului conține numele coloanelor. Adaugă
   o metodă ``lines()`` care returnează conținutul fișierului CSV, linie cu
   linie (``yield``), sub formă de dicționare.

6. Modifică clasa ``CsvDictReader`` să numere rândurile pe care le parcurge.
   Adaugă-i o metodă ``count()`` care returnează numărul curent.

7. Crează o clasă ``Rectangle`` care conține coordonatele (stânga-sus) și
   mărimea (lățime, înălțime) unui dreptunghi. Adaugă-i metode: ``area()``
   (returnează suprafața), ``center()`` (returnează o pereche ``(x, y)``
   cu coordonatele centrului dreptunghiului), și ``clamp(r)`` (translatează
   dreptunghiul astfel întcât să fie în interiorul dreptunghiului ``r``).
