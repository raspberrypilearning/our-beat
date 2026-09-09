## Afspelen en stoppen

\--- task ---

### Knop A

Sleep vanuit het menu `Invoer`{:class='microbitinput'} een `wanneer knop wordt ingedrukt`{:class='microbitinput'} blok naar het bewerkingspaneel.

```microbit
input.onButtonPressed(Button.A, function () {
})
```

\--- /task ---

\--- task ---

### Een variabele toevoegen

Gebruik een variabele om bij te houden of de melodie wordt afgespeeld.

Open het `Variabelen`{:class="microbitvariables"} menu en klik op **Maak een variabele**.

Geef je nieuwe variabele de naam `afspelen`.

\--- /task ---

\--- task ---

### Aan het afspelen of niet aan het afspelen

Sleep vanuit het menu `Variabelen` een `stel afspelen in op`-blok naar het `wanneer knop wordt ingedrukt`-blok.

```microbit
input.onButtonPressed(Button.A, function () {
    afspelen = (0)
})
```

\--- /task ---

Gebruik een `niet`{:class='microbitlogic'} blok om `afspelen` te wijzigen tussen waar en onwaar.

\--- task ---

Sleep vanuit het menu `Logisch`{:class='microbitlogic'} een `niet`{:class='microbitlogic'} blok in de `0`.

```microbit
input.onButtonPressed(Button.A, function () {
    afspelen = !(true)
})
```

\--- /task ---

\--- task ---

Sleep vanuit het menu `Variabelen`{:class='microbitvariables'} het blok `afspelen`{:class='microbitvariables'} binnen het blok `niet`{:class='microbitlogic'}.

```microbit
input.onButtonPressed(Button.A, function () {
    afspelen = !(afspelen)
})
```

\--- /task ---

\--- task ---

### Speel de melodie af wanneer afspelen waar is

Sleep vanuit het menu `Logisch`{:class='microbitlogic'} een `als`{:class='microbitlogic'}-blok naar binnen je `de hele tijd`{:class='microbitbasic'}-blok.

```microbit
basic.forever(function () {
    if (true) {
    	
    }
    music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
})
```

\--- /task ---

\--- task ---

Plaats je melodie in het `als`{:class='microbitlogic'} blok.

```microbit
basic.forever(function () {
    if (true) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

**Let op:** De melodie wordt afgespeeld omdat `waar` de standaardwaarde is.

\--- /task ---

\--- task ---

Vanuit het `Variabelen`{:class='microbitvariables'} menu sleep je het `afspelen`{:class='microbitvariables'} blok in het `als`{:class='microbitlogic'} blok.

```microbit
basic.forever(function () {
    if (afspelen) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

De melodie wordt nu alleen afgespeeld als de variabele 'afspelen' door de knop op 'waar' is ingesteld.

\--- /task ---

\--- task ---

**Test**:

Druk op knop A om 'afspelen' op 'waar' te zetten (om de melodie te starten).

Druk nogmaals op knop A om 'afspelen' op 'onwaar' te zetten (om de melodie te stoppen).

\--- /task ---

Deel je melodie met ons!

[[[microbit-share]]]
