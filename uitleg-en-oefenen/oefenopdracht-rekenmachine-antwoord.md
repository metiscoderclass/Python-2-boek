# Oefenopdracht Rekenmachine: Antwoord

Hieronder volgt een voorbeeldantwoord van de oefenopdracht rekenmachine. Jouw antwoord kan natuurlijk anders zijn! Let er op dat je een vergelijkbare opdeling in functies hebt.

```python
## Rekenmachine

getal1 = 0
getal2 = 0
operator = ""
antwoord = 0

def print_welkom():
  boodschap = '''
  Welkom bij deze rekenmachine!
  Je kunt hier twee getallen optellen, aftrekken.
  Je kunt ook vermenigvuldigen en delen.
'''
  print(boodschap)

def vraag_input():
  global getal1, getal2, operator

  getal1 = int(input("Geef het eerste getal "))
  getal2 = int(input("Geef het eerste getal "))
  operator = input("Kies een operator uit + - * / : ")

def bereken_antwoord():
  global antwoord 

  if operator == '-':
    antwoord = getal1 - getal2
  elif operator == '+':
    antwoord = getal1 + getal2
  elif operator == '*':
    antwoord = getal1 * getal2
  elif operator == '/':
    antwoord = getal1 / getal2

def print_antwoord():
  print("Je hebt gevraagd om te bereken: ")
  print(getal1, operator, getal2)
  print("Antwoord:", antwoord)

def rekenmachine():
  print_welkom()

  doorgaan = True

  while doorgaan:
    vraag_input()
    bereken_antwoord()
    print_antwoord()
    
    if input("Wil je nog een berekening? ") == 'nee':
      doorgaan = False

rekenmachine()
```

Je vindt het antwoord ook hier:

{% embed url="https://repl.it/@hakkas/Python-2-Rekenmachine" %}



