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

Скористайся змінною, щоб відстежувати чи відтворюється мелодія.

Відкрий меню `Змінні`{:class='microbitvariables'} та натисни **Створити змінну**.

Назви нову змінну `відтворюється`.

\--- /task ---

\--- task ---

### Грає чи не грає

Перенеси з меню `Змінні`{:class='microbitvariables'} блок `задати відтворюється`{:class='microbitvariables'} у блок `на клавішу`{:class='microbitinput'}.

```microbit
input.onButtonPressed(Button.A, function () {
    playing = (0)
})
```

\--- /task ---

Обери блок `не`{:class='microbitlogic'} для перемикання `відтворюється` між істиною та хибним.

\--- task ---

Перемісти з меню `Логіка`{:class='microbitlogic'} блок `не`{:class='microbitlogic'} на місце `0`.

```microbit
input.onButtonPressed(Button.A, function () {
    playing = !(true)
})
```

\--- /task ---

\--- task ---

Перенеси з меню `Змінні`{:class='microbitvariables'} блок `відтворюється`{:class='microbitvariables'} всередину блоку `не`{:class='microbitlogic'}.

```microbit
input.onButtonPressed(Button.A, function () {
    playing = !(playing)
})
```

\--- /task ---

\--- task ---

### Play the melody when playing is true

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

**Примітка**: Мелодія гратиме, бо за замовчуванням значення - `істина`.

\--- /task ---

\--- task ---

Перенеси з меню `Змінні`{:class='microbitvariables'} блок `відтворюється`{:class='microbitvariables'} всередину блоку `якщо`{:class='microbitlogic'}.

```microbit
basic.forever(function () {
    if (playing) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

Тепер мелодія гратиме тільки коли змінна 'відтворюється' встановлена кнопкою на `істина`.

\--- /task ---

\--- task ---

**Тест**:

Натисни клавішу А щоб встановити параметр 'відтворюється' як `істина` (щоб запустити мелодію).

Натисни клавішу А знову щоб встановити параметр 'відтворюється' як `хибне` (щоб зупинити мелодію).

\--- /task ---

Поділись з нами своєю мелодією!

[[[microbit-share]]]
