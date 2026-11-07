# kmem

Aniversări, comemorări și remindere, într-un singur fișier text, cu o pagină de ansamblu.

- Pagina: https://zeromem0.github.io/kmem/
- Datele: [`kmem.txt`](kmem.txt) ([editează](https://github.com/zeromem0/kmem/edit/main/kmem.txt))

Pagina arată ce urmează în următoarele 30 de zile (sau câte zile ceri cu `?zile=60`), reminderele
trecute și tot anul curent, pe luni.

## Formatul lui `kmem.txt`

Câte un eveniment pe rând: data, apoi textul.

```
# aniversări
21.12.1972   Calin              în fiecare an, cu numărul de ani
02.09        Andrei             în fiecare an, fără an de pornire

# remindere
lunar 25            Întreținerea     în fiecare lună (31 = ultima zi a lunii)
o dată 01.04.2027   ITP mașină       o singură dată
```

- `# titlu` începe o secțiune (aniversări, comemorări, remindere sau orice altceva); titlul apare
  ca etichetă lângă evenimente.
- `// ...` e comentariu, la început de rând sau după un spațiu la capătul rândului.
- `?` în loc de dată: dată necunoscută. Evenimentul nu apare în calendar, doar în tabelul persoanelor.
- Din secțiunile al căror titlu conține „naștere” și din cele cu „deces” / „comemorări”, pagina face
  la sfârșit un tabel cu fiecare persoană: data nașterii, data decesului, cât a trecut de atunci și
  vârsta la deces. Nașterea și decesul aceleiași persoane se potrivesc după text, deci numele
  trebuie scris la fel în ambele locuri.
- `29.02` cade pe 28.02 în anii nebisecți.
- Rândurile pe care pagina nu le înțelege apar sus, cu roșu, cu numărul rândului.

## Offline

Pune `index.html` și `kmem.txt` într-un folder și deschide `index.html` în browser. Deschisă direct
din fișier, pagina nu poate citi singură `kmem.txt` (restricție a browserului), așa că arată un
buton „Alege kmem.txt”; poți și să tragi fișierul peste pagină.

Fără să alegi fișierul de fiecare dată, merge cu un server local, din folderul proiectului:

```bash
python -m http.server
```

apoi http://localhost:8000.
