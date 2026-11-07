## Jouer et arrêter

\--- task ---

### Bouton A

Dans le menu `Entrée`{:class='microbitinput'}, fais glisser un bloc `lorsque le bouton`{:class='microbitinput'} vers le panneau de l'éditeur de code.

```microbit
input.onButtonPressed(Button.A, function () {
})
```

\--- /task ---

\--- task ---

### Ajouter une variable

Utilise une variable pour suivre si la mélodie est en train de jouer.

Ouvre le menu `Variables`{:class='microbitvariables'} et clique sur **Créer une variable**.

Nomme ta nouvelle variable 'joue'.

\--- /task ---

\--- task ---

### Joue ou ne joue pas

Dans le menu `Variables`{:class='microbitvariables'}, fais glisser un bloc `définir joue`{:class='microbitvariables'} à l'intérieur du bloc `lorsque le bouton`{:class='microbitinput'}.

```microbit
input.onButtonPressed(Button.A, function () {
    joue = (0)
})
```

\--- /task ---

Utilise un bloc `non`{:class='microbitlogic'} pour changer `joue` entre vrai et faux.

\--- task ---

Dans le menu `Logique`{:class='microbitlogic'}, fais glisser un bloc `non`{:class='microbitlogic'} à l'intérieur du bloc `0`.

```microbit
input.onButtonPressed(Button.A, function () {
    joue = !(vrai)
})
```

\--- /task ---

\--- task ---

Dans le menu `Variables`{:class='microbitvariables'}, fais glisser le bloc `joue`{:class='microbitvariables'} à l'intérieur du bloc `non`{:class='microbitlogic'}.

```microbit
input.onButtonPressed(Button.A, function () {
    joue = !(joue)
})
```

\--- /task ---

\--- task ---

### Jouer la mélodie lorsque joue est vrai

Dans le menu `Logique`{:class='microbitlogic'}, fais glisser un bloc `si`{:class='microbitlogic'} à l'intérieur de ton bloc `toujours`{:class='microbitbasic'}.

```microbit
basic.forever(function () {
    if (true) {
    	
    }
    music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
})
```

\--- /task ---

\--- task ---

Place ta mélodie à l'intérieur du bloc `si`{:class='microbitlogic'}.

```microbit
basic.forever(function () {
    if (true) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

**Remarque** : la mélodie sera jouée car `vrai` est la valeur par défaut.

\--- /task ---

\--- task ---

Dans le menu `Variables`{:class='microbitvariables'}, fais glisser le bloc `joue`{:class='microbitvariables'} dans le bloc `si`{:class='microbitlogic'}.

```microbit
basic.forever(function () {
    if (joue) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

Maintenant, la mélodie ne sera jouée que si la variable 'joue' est définie à `vrai` par le bouton.

\--- /task ---

\--- task ---

**Test** :

Appuie sur le bouton A pour définir 'joue' à `vrai` (démarrage de la mélodie).

Appuie à nouveau sur le bouton A pour définir 'joue' à `faux` (arrêter la mélodie).

\--- /task ---

Partage ta musique avec nous !

[[[microbit-share]]]
