# Programma met functies

We hebben nu functies gemaakt om de code van ons hoger lager spel beter te structureren. Bekijk hierover het volgende filmpje:

{% embed url="https://youtu.be/f1Llvi6TKyk" %}

Je kunt het spel ook hier bekijken proberen:  [https://repl.it/@hakkas/Python-2-Uitleg-Met-functies\#main.py](https://repl.it/@hakkas/Python-2-Uitleg-Met-functies#main.py)



{% embed url="https://repl.it/@hakkas/Python-2-Uitleg-Met-functies" %}

### Volledige programmacode

```python
import random

MAX_KEER = 6
gok = 0

def print_welkom_spel():
  print("Welkom bij dit spel!\n"
        "\n"
        "We spelen hoger/lager\n"
        "Kun jij het getal snel raden?\n")

def print_welkom_ronde():
  print("Welkom " + naam + "\n"
        "We gaan spelen!\n"
        "Raad een geheel getal\n"
        "Het is minimaal 1 en maximaal 129\n"
        "Je mag " + str(MAX_KEER) + " keer raden\n"
        "\n"
        "Succes!\n")

def lees_check_input():
  global gok
  correct = False

  while not correct:
    gok = input("Wat denk je dat het is? ")

    if not gok.isdigit():
      print("Voer een geheel getal in!")
    else:
      gok = int(gok)
      correct = True

def verwerk_gok():
  global raden

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

print_welkom_spel()
naam = input("Hoe heet je? ")
doorgaan = True

while doorgaan:
  aantal_keer = 0
  print_welkom_ronde()
  geheim = random.randint(1, 129)
  
  raden = True
  while raden:
    lees_check_input()
    aantal_keer += 1
    verwerk_gok()
    
  keuze = input("Wil je nog een keer? (ja/nee)").lower()
  if not keuze == "ja":
    doorgaan = False
```

