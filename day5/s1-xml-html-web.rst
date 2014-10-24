Exerciții
---------

1. Descarcă `acest feed RSS <http://xkcd.com/atom.xml>`_, folosind
   biblioteca ``requests``, și extrage o listă cu articolele, fiecare
   articol având titlu și dată de publicare.

2. Descarcă `acest fișier CSV
   <https://docs.google.com/spreadsheets/d/1tg6F9YUuXBe7avmvybSVDWxbh5t3m4xmUeQUOehp1P0/export?format=csv>`_ folosind biblioteca ``requests`` în modul `stream`:

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
