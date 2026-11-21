## Défi — boucle de batterie microbit V2

Le micro:bit V2 possède des sons de batterie que tu peux utiliser. Ceux-ci ne sont pas disponibles pour le micro:bit V1.

Crée un modèle de batterie et utilise des boutons pour jouer des notes de basse.

\--- task ---

### Définir le tempo !

Il n'y a pas d'éditeur de motifs pour la batterie, mais tu peux quand même créer un rythme de batterie !

Dans le menu `Musique`{:class='microbitmusic'}, fais glisser un bloc `régler le tempo`{:class='microbitmusic'} à l'intérieur du bloc `au démarrage`{:class='microbitbasic'} sur le panneau de l'éditeur de code.

```microbit
music.setTempo(120)
```

\--- /task ---

\--- task ---

### Déclencher les batteries !

Dans le menu `Entrée`{:class='microbitinput'}, fais glisser un bloc `sur le logo`{:class='microbitinput'} vers le panneau de l'éditeur de code.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
})
```

\--- /task ---

\--- task ---

### Boucle de batterie

Dans le menu `Boucles`{:class='microbitloops'}, fais glisser un bloc `tant que`{:class='microbitloops'} à l'intérieur du bloc `sur le logo`{:class='microbitinput'}.

Change `faux`{:class='microbitlogic'} en `vrai`{:class='microbitlogic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
    }
})
```

\--- /task ---

\--- task ---

### La grosse caisse en premier

Dans la section V2 de micro:bit du menu `Musique`{:class='microbitmusic'}, fais glisser un bloc `jouer (🎵 ---)`{:class='microbitmusic'} et place-le dans le bloc `tant que`{:class='microbitloops'}.

Clique sur le symbole 🎵 puis sur 'Galerie' et choisis kick drum.

Change `jusqu'à la fin`{:class='microbitmusic'} en `en arrière-plan`{:class='microbitmusic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
    }
})
```

\--- /task ---

\--- task ---

### Ajouter une pause

Dans le menu `Base`{:class='microbitbasic'}, fait glisser un bloc `pause`{:class='microbitbasic'} sous ton son de batterie kick drum.

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

Dans le menu `Musique`{:class='microbitmusic'}, fais glisser un bloc `1 temps`{:class='microbitmusic'} et place-le dans le `500`.

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

### Un rythme de quatre-quatre

Copie tes blocs `jouer (🎵 ---)`{:class='microbitmusic'} et `pause`{:class='microbitbasic'} trois fois, tu as donc quatre temps et quatre pauses.

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

**Test** : appuie sur le logo tactile et écoute ton rythme.

\--- /task ---

\--- task ---

Change le son de la 2ème et de la 4ème batterie, en remplaçant la grosse caisse par la caisse claire.

\--- /task ---

\--- task ---

**Test** : appuie sur le logo tactile et écoute ton rythme.

\--- /task ---

### Approprie-toi le rythme !

\--- task ---

Expérimente avec différentes pauses et sons de batterie.

**Remarque** : tes pauses doivent toujours totaliser 4 temps.

Voici un exemple :

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

**Essaie** : change la valeur du tempo.

**Test** : appuie sur le logo tactile et écoute ton rythme.

\--- /task ---

\--- task ---

### Ajouter quelques notes de basse

Dans le menu `Entrée`{:class='microbitinput'}, fais glisser deux blocs `lorsque le bouton`{:class='microbitinput'} vers le panneau de l'éditeur de code.

Modifies-en un pour utiliser le bouton B.

```microbit
input.onButtonPressed(Button.A, function () {
})
input.onButtonPressed(Button.B, function () {
})
```

\--- /task ---

\--- task ---

Dans le menu `Musique`{:class='microbitmusic'}, fais glisser deux blocs `jouer tonalité`{:class='microbitmusic'} et place-en un dans chaque bloc `lorsque le bouton`{:class='microbitinput'}.

Nous avons utilisé le 'Do grave' et le 'Fa grave', mais tu peux utiliser n'importe quelle note que tu préféres !

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

**Test** : touche le logo pour jouer ta boucle de batterie et appuie sur les boutons A et B en rythme avec le beat !

\--- /task ---

\--- task ---

### Lumière et mouvement

**Essaie** : remplace la tonalité (par exemple 'Do grave') par le `niveau d'intensité lumineuse`{:class='microbitinput'} afin que la tonalité change lorsque tu déplaces ta main au-dessus de ton micro:bit.

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.lightLevel(), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

Ou, utilise la valeur `acceleration (mg) x`{:class='microbitinput'} pour changer la tonalité pendant que tu le déplaces !

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.acceleration(Dimension.X), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

\--- /task ---

Partage ta musique avec nous !

[[[microbit-share]]]
