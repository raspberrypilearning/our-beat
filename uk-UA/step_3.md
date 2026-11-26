## Відтворити та зупинити

\--- task ---

### Кнопка А

Перенеси з меню `Вхідні дані`{:class='microbitinput'} блок `на клавішу`{:class='microbitinput'} на панель редактора коду.

```microbit
input.onButtonPressed(Button.A, function () {
})
```

\--- /task ---

\--- task ---

### Додай змінну

За допомогою змінної ти можеш відстежувати, чи відтворюється мелодія.

Відкрий меню `Змінні`{:class='microbitvariables'} та натисни **Створити змінну**.

Назви нову змінну `грає`.

\--- /task ---

\--- task ---

### Грає чи не грає

Перенеси з меню `Змінні`{:class='microbitvariables'} блок `задати грає`{:class='microbitvariables'} у блок `на клавішу`{:class='microbitinput'}.

```microbit
input.onButtonPressed(Button.A, function () {
    playing = (0)
})
```

\--- /task ---

Візьми блок `не`{:class='microbitlogic'}, який перемикатиме значення змінної `грає` між істиною та хибним.

\--- task ---

Перемісти з меню `Логіка`{:class='microbitlogic'} блок `не`{:class='microbitlogic'} на місце `0`.

```microbit
input.onButtonPressed(Button.A, function () {
    playing = !(true)
})
```

\--- /task ---

\--- task ---

Перенеси з меню `Змінні`{:class='microbitvariables'} блок `грає`{:class='microbitvariables'} всередину блоку `не`{:class='microbitlogic'}.

```microbit
input.onButtonPressed(Button.A, function () {
    playing = !(playing)
})
```

\--- /task ---

\--- task ---

### Відтворювати мелодію, коли змінна «грає» є істиною

Перенеси з меню `Логіка`{:class='microbitlogic'} блок `якщо`{:class='microbitlogic'} всередину блоку `постійно`{:class='microbitbasic'}.

```microbit
basic.forever(function () {
    if (true) {
    	
    }
    music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
})
```

\--- /task ---

\--- task ---

Помісти свою мелодію всередину блоку `якщо`{:class='microbitlogic'}.

```microbit
basic.forever(function () {
    if (true) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

**Примітка**: мелодія гратиме, бо за замовчуванням значення дорівнює `істині`.

\--- /task ---

\--- task ---

Перенеси з меню `Змінні`{:class='microbitvariables'} блок `грає`{:class='microbitvariables'} всередину блоку `якщо`{:class='microbitlogic'}.

```microbit
basic.forever(function () {
    if (playing) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

Тепер мелодія гратиме, тільки коли змінна «грає» отримує значення `істина` натисненням кнопки.

\--- /task ---

\--- task ---

**Протестуй**:

Натисни кнопку А, щоби надати змінній «грає» значення `істина` (щоб запустити мелодію).

Ще раз натисни кнопку А, щоб надати змінній «грає» значення `хибне` (щоб зупинити мелодію).

\--- /task ---

Поділися з нами своєю мелодією!

[[[microbit-share]]]
