# Code zonder functies

### Hoger lager spel

We hebben een voorbeeldcode geschreven voor het spelletje 'Hoger Lager'. Je gaat een getal raden en je krijgt steeds een hint of je te hoog zit, te laag zit of precies goed.

In deze versie van de code hebben we geen gebruik gemaakt van functies. Lees de code eens door en kijk of het duidelijk is wat er allemaal gebeurt. Daarna gaan we het programma opdelen in functies.

Je vindt deze code ook hier: [https://repl.it/@hakkas/Python-2-Uitleg](https://repl.it/@hakkas/Python-2-Uitleg)

```python
import random

print("Welkom bij dit spel!\n"
      "\n"
      "We spelen hoger/lager\n"
      "Kun jij het getal snel raden?\n")

naam = input("Hoe heet je? ")
doorgaan = True
aantal_keer = 0
MAX_KEER = 6

while doorgaan:
  geheim = random.randint(1, 129)
  print("Welkom " + naam + "\n"
        "We gaan spelen!\n"
        "Raad een geheel getal\n"
        "Het is minimaal 1 en maximaal 129\n"
        "Je mag " + str(MAX_KEER) + " keer raden\n"
        "\n"
        "Succes!\n")

  raden = True
  while raden:
    # Eruit?
    try:
      gok = int(input("Wat denk je dat het is? "))
    except:
      print("Geef een geheel getal...")
      continue

    aantal_keer += 1

    if gok == geheim:
      print("Gefeliciteerd", naam, "je hebt het in", aantal_keer, "geraden!")
      raden = False
    else:
      if aantal_keer >= MAX_KEER:
        print("Helaas, je hebt al", MAX_KEER, "geraden. Het was:", geheim)
        raden = False
      else:
        if gok < geheim:
          print("Te laag!")
        else:
          print("Te hoog!")
          
        print("Je hebt nu", aantal_keer, "keer geraden.")
    
  keuze = input("Wil je nog een keer? (ja/nee)").lower()
  if not keuze == "ja":
    doorgaan = False
```

### Hoger lager spel met functies



