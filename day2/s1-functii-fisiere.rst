Funcții
-------

Funcția este o secvență de cod care poate fi apelată în mod repetat.

.. code:: python

    def foo(n):
        return "you called 'foo' with argument %s" % n

    print foo(13)
    print foo("hey!")
    print foo([3, 4])


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


Directoare și fișiere
---------------------

Pentru operațiuni cu directoare și fișiere, vom folosi biblioteca
`pathlib <http://pathlib.readthedocs.org/en/pep428/>`_, care oferă un API
comod și lizibil:

.. code:: python

    from pathlib import Path

    incl = Path('/usr/include')
    print incl.is_dir()
    print [f.name for f in incl.iterdir()]
    print [f.name for f in incl.glob('**/*.h')]

Ca să citim conținutul unui fișier, îl deschidem cu funcția ``open``, și
apelăm funcția ``read()``:

.. code:: python

    f = open('/etc/issue')
    data = f.read()


Exerciții
---------

1. Implementează o funcție care returnează factorialul unui număr dat.

2. Implementează o funcție numită ``ls(p)`` care afișează conținutul
   directorului ``p``.

3. Specifică o valoare default pentru argumentul ``p``: dacă nu este prezent
   atunci se va afișa directorul curent (``Path.cwd()``).

4. Adaugă un argument opțional ``classify=False``. Dacă argumentul este
   adevărat, atunci va adăuga câte un caracter la numele fișierelor:
   ``/`` pentru directoare, ``@`` pentru symlink-uri, ``*`` pentru fișire
   executabile.

5. Adaugă un argument opțional ``recursive=False``. Dacă argumentul este
   adevărat, funcția se va auto-apela recursiv atunci când întâlnește un
   subdirector. Apelarea recursivă să aibă loc după ce s-a terminat afișarea
   conținutului directorului.

6. Implementează o funcție numită ``grep(needle, p)``, care citește toate
   fișierele dintr-un director, și returnează o listă cu căile acelor fișiere
   care conțin string-ul ``needle``.

7. Adaugă un argument ``any_case=False``. Dacă argumentul este adevărat,
   potrivirea se va face indiferent de litere mari sau mici.

8. Implementează o funcție ``largest(p)``, care citește toate fișierele
   dintr-un director, și returnează calea fișierului cu cele mai multe
   cuvinte.
