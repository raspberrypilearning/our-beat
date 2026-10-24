## Uitdaging - Maak een band

Gebruik de radio om een micro:bit band te maken!

Eén micro:bit speelt de **melodie** af.
De andere micro:bit zal de **bas** spelen.

\--- task ---

## Opzetten

Open het `Variabelen`{:class="microbitvariables"} menu en klik op **Maak een variabele**.

Geef je nieuwe variabele de naam `instrument`.

\--- /task ---

\--- task ---

Sleep vanuit het menu `Tekst`{:class='microbittext'} een leeg tekenreeksblok naar de `0`.

```microbit
instrument = "" 
afspelen = false
```

\--- /task ---

\--- task ---

Voeg deze code toe, die het volgende zal doen:

- De micro:bit vertellen dat er nog niets wordt afgespeeld.
- Een radiogroep instellen zodat de micro:bits met elkaar kunnen communiceren. Beide micro:bits moeten zich in dezelfde **radiogroep** bevinden.
- Stel het volume in en toon een slaperig gezicht.

```microbit
instrument = "" 
afspelen = false
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

\--- /task ---

\--- task ---

### Druk op 'A' voor de melodie

Controleer of de micro:bit _niet_ is ingesteld als **melodie**-instrument.

```microbit
input.onButtonPressed(Button.A, function () {
    if (instrument != "Melodie") {
        instrument = "Melodie"
        afspelen = true
        basic.showString("M")
    }
})
```

\--- /task ---

\--- task ---

**Test**: Druk op knop A om de melodie af te spelen.
De micro:bit zal 'M' weergeven.

\--- /task ---

\--- task ---

### Druk op 'B' voor bas

Voeg wat code toe zodat je op knop B kunt drukken om een andere micro:bit de bas te laten spelen.

```microbit
input.onButtonPressed(Button.B, function () {
    radio.sendString("Bas")
})
```

\--- /task ---

\--- task ---

### Ontvang het bas-bericht

Als een micro:bit niets aan het doen is en het basbericht ontvangt, start hij het basgedeelte.

Controleer of de micro:bit niet is ingesteld als een instrument.
Als het het bassignaal ontvangt, start het de bas en geeft het 'B' weer.

```microbit
radio.onReceivedString(function (receivedString) {
    if (receivedString == "Bas" && instrument == "") {
        instrument = "Bas"
        afspelen = true
        basic.showString("B")
    } else {
    }
})
```

\--- /task ---

\--- task ---

### Samen instrumenten bespelen

1. De melodie-micro:bit speelt zijn melodie en stuurt vervolgens een signaal naar de bas-micro:bit om te laten weten wanneer die moet spelen.

Je kunt de melodie gebruiken die je in de vorige stap hebt gemaakt!

```microbit
basic.forever(function () {
    if (instrument == "Melodie" && afspelen) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
        radio.sendString("nieuweMaat")
    }
})
```

\--- /task ---

\--- task ---

### De bas valt in

Wanneer de bas micro:bit het signaal 'nieuweMaat' ontvangt, speelt deze synchroon met de melodie.

Deze baslijn past goed bij onze melodie, maar je kunt natuurlijk ook je eigen baslijn maken!

Voeg deze blokken toe binnen de 'anders' in `wanneer de radio ontvangt`{:class="microbitradio"}:

```microbit
radio.onReceivedString(function (receivedString) {
    if (receivedString == "Bas" && instrument == "") {
        instrument = "Bas"
        afspelen = true
        basic.showString("B")
    } else {
        if (receivedString == "nieuweMaat" && playing && instrument == "Bas") {
            music.play(music.stringPlayable("C - C - - C - C ", 120), music.PlaybackMode.UntilDone)
        }
    }
})
```

\--- /task ---

\--- task ---

**Test**

- Druk op A om de melodie te starten
- Druk op B om de bas op een andere micro:bit te starten

\--- /task ---

\--- task ---

### Pauzeer en speel opnieuw af

Controleer of de micro:bits zijn ingesteld als instrumenten.

Als dat voor een van beide het geval is, wijzig dan de afspeelstatus.

```microbit
input.onGesture(Gesture.Shake, function () {
    if (instrument != "") {
        afspelen = !(afspelen)
        basic.showIcon(IconNames.Asleep)
    }
})
```

\--- /task ---

\--- task ---

**Test**:

- Schud de micro:bit om de muziek te pauzeren en een slaperig gezichtje te tonen
- Schud opnieuw om te beginnen

\--- /task ---

Deel je melodie met ons!

[[[microbit-share]]]
