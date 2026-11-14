## Додаткове завдання - барабанна петля microbit V2

В micro:bit V2 є звуки барабанів, якими ти можеш скористатись. Вони недоступні для micro:bit V1.

Створи барабанний ритм та залучити.

\--- task ---

### Задай темп!

Тут немає редактора барабанних петель, але ти можеш створити барабанний ритм!

Перенеси з меню `Музика`{:class='microbitmusic'} блок `встановити темп на рівні`{:class='microbitmusic'} всередину блоку `при запуску`{:class='microbitbasic'} на панель редактор коду.

```microbit
music.setTempo(120)
```

\--- /task ---

\--- task ---

### Запускай барабани!

Перенеси з меню `Вхідні дані`{:class='microbitinput'} блок `on logo`{:class='microbitinput'} на панель редактора коду.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
})
```

\--- /task ---

\--- task ---

### Барабанна петля

Перенеси з меню `Цикли`{:class='microbitloops'} блок `поки`{:class='microbitloops'} всередину блоку `on logo`{:class='microbitinput'}.

Зміни `хибне` {: class='microbitlogic'} на `істина`{:class='microbitlogic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
    }
})
```

\--- /task ---

\--- task ---

### Спочатку бас-барабан

З секції micro:bit V2 з меню"Музика`{:class='microbitmusic'} перетягни блок "грати (🎵 -)`{:class='microbitmusic'} і розмістити його в блоці `while`{:class='microbitloops'}.

Натисни на символ 🎵, потім «Галерея» та обери бас-барабан.

Зміни `until done`{:class='microbitmusic'} на `in background`{:class='microbitmusic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
    }
})
```

\--- /task ---

\--- task ---

### Додай паузи

Перетягни з меню `Basic`{:class='microbitbasic'} блок `pause`{:class='microbitbasic'} під доріжку твого бас-барабана.

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

Перетягни з меню `Music`{:class='microbitmusic'} блок `1 beat`{:class='microbitmusic'} та помісти його в `500`.

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

### Ритм чотири чверті

Скопіюй блоки `play (🎵 ---)`{:class='microbitmusic'} та `pause`{:class='microbitbasic'} тричі, щоб вийшло чотири удари та чотири паузи.

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

**Тест**: Обери touch в on logo та прослухай свій біт.

\--- /task ---

\--- task ---

Зміни звук 2-го та 4-го барабанів з бас-барабана на малий барабан.

\--- /task ---

\--- task ---

**Тест**: Обери touch в on logo та прослухай свій біт.

\--- /task ---

### Напиши власний ритм!

\--- task ---

Експериментуй, обери різні паузи та барабани.

**Примітка**: Твої паузи повинні вкладатись у 4 ударів.

Ось, наприклад:

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

**Спробуй**: Зміни значення темпу.

**Тест**: Обери touch в on logo та прослухай свій біт.

\--- /task ---

\--- task ---

### Додати трохи басів

Перенеси з меню `Input`{:class='microbitinput'} два блоки `on button`{:class='microbitinput'} на панель редактора коду.

Зміни один, щоб він використовував кнопку B.

```microbit
input.onButtonPressed(Button.A, function () {
})
input.onButtonPressed(Button.B, function () {
})
```

\--- /task ---

\--- task ---

Перенеси з меню `Music`{:class='microbitmusic'} два блоки `play tone`{:class='microbitmusic'} та постав по одному в кожен блок `on button`{:class='microbitinput'}.

Ми взяли «Басову До» та «Басову Фа», але ти можеш обрати будь-який тон, який тобі до вподоби!

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

**Тест**: Натисни on logo щоб запустити твою барабанну петлю, та натискай кнопки A та B у такт ритму!

\--- /task ---

\--- task ---

### Висота та позиція

**Спробуйте**: Зміни тон (наприклад, «Басовий До») на `першу октаву`{:class='microbitinput'}, щоб тон змінювався коли ти міняєш позицію micro:bit.

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.lightLevel(), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

Або зміни значення `acceleration (mg) x`{:class='microbitinput'}, щоб міняти тон при зміні позиції!

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.acceleration(Dimension.X), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

\--- /task ---

Поділися з нами своєю мелодією!

[[[microbit-share]]]
