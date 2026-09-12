## Uitdaging — drumloop met de micro:bit V2

De micro:bit V2 heeft drumgeluiden die je kunt gebruiken. Deze zijn niet beschikbaar voor de micro:bit V1.

Maak een drumritme en gebruik de knoppen om basnoten te spelen.

\--- task ---

### Bepaal het tempo!

Er is geen patrooneditor voor drums, maar je kunt nog steeds een drumbeat creëren!

Sleep vanuit het menu `Muziek`{:class='microbitmusic'} een `zet tempo op`{:class='microbitmusic'} blok naar het `bij opstarten`{:class='microbitbasic'} blok in het bewerkingspaneel.

```microbit
music.setTempo(120)
```

\--- /task ---

\--- task ---

### Laat de drums klinken!

Sleep vanuit het menu `Invoer`{:class='microbitinput'} een `bij logo ingedrukt`{:class='microbitinput'} blok naar het bewerkingspaneel.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
})
```

\--- /task ---

\--- task ---

### Drum loop

Sleep vanuit het menu `Lussen`{:class='microbitloops'} een `terwijl`{:class='microbitloops'} blok naar het `bij logo ingedrukt`{:class='microbitinput'} blok.

Verander `onwaar`{:class='microbitlogic'} in `waar`{:class='microbitlogic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
    }
})
```

\--- /task ---

\--- task ---

### Als eerste, de bassdrum

Vanuit de micro:bit V2 sectie van het `Muziek`{:class='microbitmusic'} menu, sleep een `speel (🎵 ---)`{:class='microbitmusic'} blok en plaats het in het `terwijl`{:class='microbitloops'} blok.

Klik op het 🎵-symbool, vervolgens op 'Galerij' en kies de kick drum.

Wijzig `tot het klaar is`{:class='microbitmusic'} naar `op de achtergrond`{:class='microbitmusic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
    }
})
```

\--- /task ---

\--- task ---

### Voeg een pauze toe

Vanuit het `Basis`{:class='microbitbasic'} menu sleep je een `pauzeer`{:class='microbitbasic'} blok onder je basdrum-geluid.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(500)
    }
})
```

\--- /task ---

\--- task ---

Sleep vanuit het menu `Muziek`{:class='microbitmusic'} een `1 beat`{:class='microbitmusic'} blok naar de positie `500`.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
    }
})
```

\--- /task ---

\--- task ---

### Een vierkwartsmaat

Kopieer je `speel (🎵 ---)`{:class='microbitmusic'} en `pauzeer`{:class='microbitbasic'} blokken drie keer, zodat je vier beats en vier pauzes hebt.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
    }
})
```

\--- /task ---

\--- task ---

**Test**: Druk op het aanraaklogo en luister naar je beat.

\--- /task ---

\--- task ---

Verander het geluid van de 2e en 4e drum van basdrum (kick drum) naar een snaar (snare drum).

\--- /task ---

\--- task ---

**Test**: Druk op het aanraaklogo en luister naar je beat.

\--- /task ---

### Maak je eigen beat!

\--- task ---

Experimenteer met verschillende pauzes en drumgeluiden.

**Let op:** Je pauzes moeten in totaal altijd 4 tellen duren.

Hier is een voorbeeld:

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
        music.play(music.createSoundExpression(WaveShape.Noise, 100, 1500, 100, 0, 10, SoundExpressionEffect.None, InterpolationCurve.Linear), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Quarter))
        music.play(music.createSoundExpression(WaveShape.Noise, 523, 1, 255, 0, 100, SoundExpressionEffect.Warble, InterpolationCurve.Logarithmic), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
        music.play(music.createSoundExpression(WaveShape.Noise, 100, 1500, 100, 0, 10, SoundExpressionEffect.None, InterpolationCurve.Linear), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Quarter))
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
        music.play(music.createSoundExpression(WaveShape.Noise, 100, 1500, 100, 0, 10, SoundExpressionEffect.None, InterpolationCurve.Linear), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Quarter))
        music.play(music.createSoundExpression(WaveShape.Noise, 523, 1, 255, 0, 100, SoundExpressionEffect.Warble, InterpolationCurve.Logarithmic), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
        music.play(music.createSoundExpression(WaveShape.Noise, 100, 1500, 100, 0, 10, SoundExpressionEffect.None, InterpolationCurve.Linear), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Quarter))
    }
})
```

\--- /task ---

\--- task ---

**Probeer**: Wijzig de waarde van het tempo.

**Test**: Druk op het aanraaklogo en luister naar je beat.

\--- /task ---

\--- task ---

### Voeg wat bastonen toe

Sleep vanuit het menu `Invoer`{:class='microbitinput'} twee `wanneer knop wordt ingedrukt`{:class='microbitinput'} blokken naar het code-editorpaneel.

Wijzig één optie om de B-knop te gebruiken.

```microbit
input.onButtonPressed(Button.A, function () {
})
input.onButtonPressed(Button.B, function () {
})
```

\--- /task ---

\--- task ---

Sleep vanuit het menu `Muziek`{:class='microbitmusic'} twee `speel toon`{:class='microbitmusic'} blokken en plaats er één in elk `wanneer knop wordt ingedrukt`{:class='microbitinput'} blok.

We hebben 'Lage C' en 'Lage F' gebruikt, maar je kunt elke toon gebruiken die je wilt!

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(131, music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
input.onButtonPressed(Button.B, function () {
    music.play(music.tonePlayable(175, music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

\--- /task ---

\--- task ---

**Test**: Raak het logo aan om je drumloop af te spelen en druk op de A- en B-knop op de maat van de beat!

\--- /task ---

\--- task ---

### Licht en beweging

**Probeer**: Vervang de toon (bijv. 'Lage C') door het `lichtniveau`{:class='microbitinput'} zodat de toon verandert wanneer je je hand over je micro:bit beweegt.

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.lightLevel(), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

Of gebruik de waarde `versnelling (mg) x`{:class='microbitinput'} om de toon te veranderen terwijl je hem beweegt!

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.acceleration(Dimension.X), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

\--- /task ---

Deel je melodie met ons!

[[[microbit-share]]]
