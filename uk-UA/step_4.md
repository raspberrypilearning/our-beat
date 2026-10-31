## Додаткове завдання — збери групу

Скористайся радіо, щоб створити групу з micro:bit!

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

Додай цей код, який:

- Вказуватиме micro:bit що зараз нічого не грає.
- Налаштує радіогрупу, щоб micro:bit могли спілкуватись один з одним. Обидва micro:bit мають бути в одній **радіогрупі**.
- Контролюватиме гучність та показуватиме сумне обличчя.

```microbit
instrument = "" 
playing = false
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

\--- /task ---

\--- task ---

### Натисни кнопку A, щоб заграла мелодія

Переконайся, що micro:bit _не_ налаштований як інструмент **мелодія**.

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

**Протестуй**: натисни на кнопку А, щоб запустити мелодію.
The micro:bit will show ‘M’.

\--- /task ---

\--- task ---

### Натисни кнопку B, щоб заграв бас

Додай код, що б при натисканні на кнопку В інший micro:bit грав басову партію.

```microbit
input.onButtonPressed(Button.B, function () {
    radio.sendString("Bass")
})
```

\--- /task ---

\--- task ---

### Отримуємо відповідь басу

Якщо micro:bit нічим не зайнятий і отримує сигнал від баса, він запустить басову лінію.

Переконайся, що micro:bit не встановлено як інструмент.
Якщо він отримує сигнал від баса, то починається відтворення басової лінії зі значенням "В".

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

### Запусти всі інструменти разом

1. Мелодійний micro:bit відтворює свою мелодію, а потім надсилає сигнал басовому micro:bit, щоб вказати, коли грати.

Ви можете використовувати власну мелодію, створену на останньому кроці!

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

### Приєднується бас

Коли басовий micro:bit отримує вказівку 'newBar', він зіграє в такт мелодії.

Ця басова лінія добре поєднується з нашою мелодією, але можеш спробувати написати свій власний!

Додай ці блоки в 'else' в `on radio received`{:class="microbitradio"}:

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

**Протестуй**

- Натисни A, щоб запустити мелодію
- Натисни B, щоб запустити бас на іншому micro:bit

\--- /task ---

\--- task ---

### Пауза та відтворення

Перевір, чи вказані micro:bits як інструменти.

Якщо жодний не вказаний - зміни налаштування відтворення.

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

**Протестуй**:

- Струсни micro:bit щоб призупинити музику і побачити сонне обличчя
- Струсни ще раз, щоб почати

\--- /task ---

Поділися з нами своєю мелодією!

[[[microbit-share]]]
