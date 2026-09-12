## Додаткове завдання - збери групу

Скористайся радіо, щоб створити micro:bit групу!

Один micro:bit гратиме **мелодію**.
Інший micro:bit гратиме **бас**.

\--- task ---

## Налаштування

Відкрий меню `Змінні`{:class='microbitvariables'} та натисни **Створити змінну**.

Назви нову змінну `інструмент`.

\--- /task ---

\--- task ---

Перенеси з меню `Текст`{:class='microbittext'} порожній блок всередину `0`.

```microbit
instrument = "" 
playing = false
```

\--- /task ---

\--- task ---

Додай цей код, він:

- Вказуватиме micro:bit що зараз нічого не грає.
- Налаштує радіо групу, щоб micro:bit могли спілкуватись один з одним. Обидва micro:bit мають бути в одній **радіо групі**.
- Set the volume and show a sleepy face.

```microbit
instrument = "" 
playing = false
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

\--- /task ---

\--- task ---

### Натисни 'A' що б заграла мелодія

Переконайся що micro:bit _не_ налаштований як інструмент **мелодія**.

```microbit
input.onButtonPressed(Button.A, function () {
    if (instrument != "Melody") {
        instrument = "Melody"
        playing = true
        basic.showString("M")
    }
})
```

\--- /task ---

\--- task ---

**Тест**: Натисни на кнопку А що б запустити мелодію.
The micro:bit will show ‘M’.

\--- /task ---

\--- task ---

### Натисни 'B' що б заграв бас

Додай код, що б при натисканні на кнопку В інший micro:bit грав басову партію.

```microbit
input.onButtonPressed(Button.B, function () {
    radio.sendString("Bass")
})
```

\--- /task ---

\--- task ---

### Отримуємо відповідь басу

If a micro:bit is not doing anything and receives the bass message, it starts the bass part.

Check that the micro:bit is not set to an instrument.
If it receives the bass message, it starts the bass and shows ‘B’.

```microbit
radio.onReceivedString(function (receivedString) {
    if (receivedString == "Bass" && instrument == "") {
        instrument = "Bass"
        playing = true
        basic.showString("B")
    } else {
    }
})
```

\--- /task ---

\--- task ---

### Play instruments together

1. The melody micro:bit plays its tune, then sends a signal to tell the bass micro:bit when to play.

You can use the melody you created in the last step!

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

### The bass joins in

When the bass micro:bit receives 'newBar', it plays in time with the melody.

This bass works well with our melody — but you can try making your own!

Add these blocks inside the 'else' in `on radio received`{:class="microbitradio"}:

```microbit
radio.onReceivedString(function (receivedString) {
    if (receivedString == "Bass" && instrument == "") {
        instrument = "Bass"
        playing = true
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

**Тест**

- Press A to start the melody
- Press B to start the bass on another micro:bit

\--- /task ---

\--- task ---

### Pause and play again

Check whether the micro:bits are set as instruments.

If either of them are, change the playing state.

```microbit
input.onGesture(Gesture.Shake, function () {
    if (instrument != "") {
        playing = !(playing)
        basic.showIcon(IconNames.Asleep)
    }
})
```

\--- /task ---

\--- task ---

**Тест**:

- Shake the micro:bit to pause the music and show a sleepy face
- Shake again to start

\--- /task ---

Поділись з нами своєю мелодією!

[[[microbit-share]]]
