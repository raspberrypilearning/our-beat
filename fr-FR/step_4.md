## Défi — Former un groupe

Utilise la radio pour créer un groupe de musique micro:bit !

Un micro:bit jouera la **mélodie**.
L'autre micro:bit jouera la **basse**.

\--- task ---

## Configuration

Ouvre le menu `Variables`{:class='microbitvariables'} et clique sur **Créer une variable**.

Nomme ta nouvelle variable 'instrument'.

\--- /task ---

\--- task ---

Depuis le menu `Texte`{:class='microbittext'}, fais glisser un bloc de chaîne vide à l'intérieur du `0`.

```microbit
instrument = "" 
joue = faux
```

\--- /task ---

\--- task ---

Ajoute ce code, qui permettra de :

- Dire au micro:bit que rien ne joue encore.
- Configurer un groupe radio pour que les micro:bits puissent communiquer entre eux. Les deux micro:bits doivent appartenir au même **groupe radio**.
- Régler le volume et afficher un visage endormi.

```microbit
instrument = "" 
joue = faux
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

\--- /task ---

\--- task ---

### Appuyer sur 'A' pour la mélodie

Vérifie que le micro:bit n'est _pas_ configuré comme un instrument **mélodique**.

```microbit
input.onButtonPressed(Button.A, function () {
    if (instrument != "Melody") {
        instrument = "Melody"
        joue = vrai
        basic.showString("M")
    }
})
```

\--- /task ---

\--- task ---

**Test** : appuie sur le bouton A pour commencer à jouer la mélodie.
Le micro:bit affichera ‘M’.

\--- /task ---

\--- task ---

### Appuyer sur 'B' pour la basse

Ajoute du code pour que tu puisses appuyer sur le bouton B pour dire à un autre micro:bit qu'il est la basse.

```microbit
input.onButtonPressed(Button.B, function () {
    radio.sendString("Bass")
})
```

\--- /task ---

\--- task ---

### Recevoir le message des basses

Si un micro:bit ne fait rien et reçoit le message de basse, il lance la partie basse.

Vérifie que le micro:bit n'est pas configuré comme un instrument.
S'il reçoit le message de basse, il démarre la basse et affiche 'B'.

```microbit
radio.onReceivedString(function (receivedString) {
    if (receivedString == "Bass" && instrument == "") {
        instrument = "Basse"
        joue = vrai
        basic.showString("B")
    } else {
    }
})
```

\--- /task ---

\--- task ---

### Jouer des instruments ensemble

1. Le micro:bit mélodique joue sa mélodie, puis envoie un signal pour indiquer au micro:bit basse quand jouer.

Tu peux utiliser la mélodie que tu as créée à l'étape précédente !

```microbit
basic.forever(function () {
    if (instrument == "Melody" && playing) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
        radio.sendString("newBar")
    }
})
```

\--- /task ---

\--- task ---

### La basse se joint à la fête

Lorsque le micro:bit basse reçoit le signal 'newBar', il joue en rythme avec la mélodie.

Cette basse fonctionne bien avec notre mélodie — mais tu peux essayer de créer la tienne !

Ajoute ces blocs à l'intérieur du 'sinon' dans `quand une donnée est reçue par radio`{:class="microbitradio"}:

```microbit
radio.onReceivedString(function (receivedString) {
    if (receivedString == "Bass" && instrument == "") {
        instrument = "Bass"
        joue = vrai
        basic.showString("B")
    } else {
        if (receivedString == "newBar" && playing && instrument == "Bass") {
            music.play(music.stringPlayable("C - C - - C - C ", 120), music.PlaybackMode.UntilDone)
        }
    }
})
```

\--- /task ---

\--- task ---

**Test**

- Appuie sur A pour démarrer la mélodie
- Appue sur B pour commencer la basse sur un autre micro:bit

\--- /task ---

\--- task ---

### Pause et lecture à nouveau

Vérifie si les micro:bits sont définis comme instruments.

Si l'un ou l'autre l'est, modifie l'état de lecture.

```microbit
input.onGesture(Gesture.Shake, function () {
    if (instrument != "") {
        joue = !(joue)
        basic.showIcon(IconNames.Asleep)
    }
})
```

\--- /task ---

\--- task ---

**Test** :

- Secoue le micro:bit pour mettre la musique en pause et montrer un visage endormi
- Secoue à nouveau pour démarrer

\--- /task ---

Partage ta musique avec nous !

[[[microbit-share]]]
