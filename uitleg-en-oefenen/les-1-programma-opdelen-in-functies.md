# Hoofdstuk 1 - Programma opdelen in functies

Je hebt tot nu toe steeds heel kleine programma’s geschreven van misschien maximaal 20 regels code. Als je grotere programma’s gaat schrijven zul je zien dat code al snel onoverzichtelijk en onduidelijk wordt. Om toch weer structuur aan te brengen ga je nu leren hoe je een programma kunt opdelen in functies.

### Voordelen van functies

Je hebt al kennis gemaakt met functies in Python, denk maar eens aan de tekenvierkant functie in Python 0:

```python
def tekenvierkant(lengte):
  for _ in range(4):
    turtle.forward(lengte)
    turtle.left(90)

tekenvierkant(50)
tekenvierkant(100)
```

  De functie heeft hier meerdere voordelen:

* In de naam van de functie kun je ziet wat hij doet \(overzicht\)
* Je kunt de code in de functie steeds opnieuw gebruiken
* Als je iets wilt wijzigen hoef je dat maar op een plek te doen \(minder kans op foutjes\)

Voor de structuur van je programma is de eerste eigenschap heel belangrijk:

* De naam van een functie vertelt je wat deze doet.

Waarom is dat nou belangrijk? Code die gemaakt wordt meestal maar 1 keer geschreven en daarna heel vaak gelezen. Door jezelf, maar ook door anderen!  
Goed leesbare code is veel makkelijker te onderhouden.  


### Voorbeeldprogramma: Todolijstje

#### Introductie

Voor het maken van een todolijstje kun je bijvoorbeeld het volgende doen:

```python
herhaal steeds:
  vraag om een todo item
  voeg todo item aan lijstje toe
  print het lijstje

  vraag of je door wilt gaan of stoppen
```

Hier zie je in stapjes wat je programma gaat doen. Vaak kun je dat dan direct omzetten in functies!  
Dus het hoofddeel van je programma ziet er dan zo uit:

```python
doorgaan = True

while doorgaan:
  vraag_item()
  voeg_item_toe()
  print_lijst()

  if input("Wil je doorgaan? ") == "nee":
    doorgaan = False
```

Simpel he?  


#### Volledige programma: Todolijst

Wat we nu nog moeten doen is het maken van de functies en ons todolijstje en de items.

```python
# We houden het lijstje bij in een string
todolijst = ""

# Hier onthouden we het laatste item dat moet worden toegevoegd
item = ""

def vraag_item():
  # global hebben we nodig omdat we item willen bewerken
  global item
  item = print("Welk item wilt u toevoegen? ")

def voeg_item_toe():
  global todolijst
  # Zet een komma tussen de items
  # Behalve als het het eerste item is
  if todolijst == "":
    todolijst = item
  else:
    todolijst = todolijst + ", " + item

def print_lijst():
  print("Je hebt de volgende todolijst: ")
  print(todolijst)
  print()
  print("Veel succes ermee!")

doorgaan = True

while doorgaan:
  vraag_item()
  voeg_item_toe()
  print_lijst()

  if input("Wil je doorgaan? ") == "nee":
    doorgaan = False
```

Je ziet nu onderin je code welke stappen het programma zet. Dit zijn maar 7 regels code dus erg overzichtelijk. Erboven kun je dan zien hoe de functies de stapjes precies uitvoeren.

#### Sleutelwoord: global

Je ziet een nieuw woord in de code staan:  `global`. Dit is in dit programma nodig omdat we geen parameters hebben gebruikt. `global` zorgt ervoor dat je variabelen die je bovenin je programma hebt gedefinieerd kunt veranderen in je functie. In de volgende Python module ga je leren hoe je dit netter kan doen zonder `global`te gebruiken.

In deze module verder niet in waarom we dat precies nodig hebben. Als je wilt weten hoe het met global kan, ga dan eens zoeken op `parameters`, `return`, lokale en globale variabelen. Of vraag het aan je docent!

### Nawoord: Veel meer code?

Natuurlijk hadden we veel minder code kunnen gebruiken als we geen functies hadden gemaakt. Een todolijstje maken is ook een simpel probleem. Dus we proberen je hier te leren hoe je een probleem opdeelt in stukjes en het programma leesbaar houdt. 

