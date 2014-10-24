requests
--------

Putem accesa pagini de pe web cu biblioteca `requests`:

.. code:: python

    import requests
    resp = requests.get('http://xkcd.com/')
    print resp.content  # conținutul nemodificat
    print resp.text  # conținutul, interpretat ca unicode


lxml
----

Cu biblioteca `lxml` putem citi documente `xml` și le putem parcurge folosind
`xpath`:

.. code:: python

    import requests, lxml.etree
    resp = requests.get('http://xkcd.com/atom.xml')
    doc = lxml.etree.fromstring(resp.content)
    doc.xpath(...)

Putem citi și documente `html`, unde avem, în plus, opțiunea să le parcurgem
folosind selectori `css``:

.. code:: python

    import requests, lxml.html
    resp = requests.get('https://pypi.python.org/pypi/pathlib')
    doc = lxml.html.fromstring(resp.content)
    doc.cssselect(...)


Exerciții
---------

1. Descarcă `acest feed RSS <http://xkcd.com/rss.xml>`_, folosind
   biblioteca ``requests``, și extrage o listă cu articolele, fiecare
   articol având titlu și dată de publicare.

2. Descarcă `acest fișier CSV
   <https://gist.githubusercontent.com/mgax/9a0c2cc94aa1564c4966/raw/f95717eeeea261958f95a0ca47206a795ed847f1/migrari.csv>`_ folosind biblioteca ``requests`` în modul `stream`:

   .. code:: python

      resp = requests.get(url, stream=True)
      f = resp.raw  # `f` este un fisier

3. Descarcă informații despre un pachet de la `PyPI` folosind o adresă
   de forma ``https://pypi.python.org/pypi/{pachet}/json``. Interpretează
   răspunsul de tip JSON folosind metoda ``resp.json()`` și calculează suma
   numerelor de download de la toate versiunile (folosește valorile din
   secțiunea "releases", nu din "info" / "downloads").

4. Generează un document `HTML` care conține o listă cu titlurile articolelor
   din feed-ul RSS de mai sus. Documentul va avea formatul:

    .. code:: html

        <ul>
          <li>titlu 1</li>
          <li>titlu 2</li>
          ...
        </ul>

5. Descarcă pagina principală a documentației pacheetului `requests` și
   extrage secțiunile principale din cuprins ("Introduction", "Installation",
   "Quickstart" ...).

6. Descarcă o pagină normală a unui pachet din `PyPI` (versiunea HTML, nu
   versiunea JSON) și extrage link-ul de download al pachetului.
