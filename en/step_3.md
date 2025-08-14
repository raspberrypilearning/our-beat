## Play and stop

--- task ---
### Button A

From the `Input`{:class='microbitinput'} menu, drag an `on button`{:class='microbitinput'} block to the code editor panel.

```microbit
input.onButtonPressed(Button.A, function () {
})
```

--- /task ---

--- task ---
### Add a variable

Use a variable to track if the melody is playing.

Open the `Variables`{:class='microbitvariables'} menu and click **Make a Variable**.

Name your new variable `playing`. 

--- /task ---

--- task ---
### Playing or not playing

From the `Variables`{:class='microbitvariables'} menu, drag a `set playing`{:class='microbitvariables'} block inside the `on button`{:class='microbitinput'} block. 

```microbit
input.onButtonPressed(Button.A, function () {
    playing = (0)
})
```

--- /task ---

Use a `not`{:class='microbitlogic'} block to change `playing` between true and false.

--- task ---

From the `Logic`{:class='microbitlogic'} menu, drag a `not`{:class='microbitlogic'} block inside the `0`.

```microbit
input.onButtonPressed(Button.A, function () {
    playing = !(true)
})
```

--- /task ---

--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag the `playing`{:class='microbitvariables'} block inside the `not`{:class='microbitlogic'} block. 

```microbit
input.onButtonPressed(Button.A, function () {
    playing = !(playing)
})
```

--- /task ---

--- task ---
### Play the melody when playing is true

From the `Logic`{:class='microbitlogic'} menu, drag an `if`{:class='microbitlogic'} block inside your `forever`{:class='microbitbasic'} block.

```microbit
basic.forever(function () {
    if (true) {
    	
    }
    music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
})
```

--- /task ---

--- task ---

Place your melody inside the `if`{:class='microbitlogic'} block.

```microbit
basic.forever(function () {
    if (true) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

**Notice**: The melody will play because `true` is the default.

--- /task ---

--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag the `playing`{:class='microbitvariables'} block inside the `if`{:class='microbitlogic'} block. 

```microbit
basic.forever(function () {
    if (playing) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
    }
})
```

Now, the melody will only play if the 'playing' variable is set to `true` by the button.

--- /task ---

--- task ---

**Test**:

Press button A to set 'playing' to `true` (starting the melody).

Press button A again to set 'playing' to `false` (stopping the melody).

--- /task ---

Share your tune with us!

[[[microbit-share]]]
