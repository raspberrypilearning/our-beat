## micro:bit band

Use radio to build a micro:bit band!

One micro:bit will play the **Melody**.
The other micro:bit will play the **Bass**.
Both micro:bits must be in **Radio Group 22**.

## Set up

Get the micro:bits ready.

--- task ---

- Tell the micro:bit that nothing is playing yet.
- Set a radio group so the micro:bits can talk to each other.
- Set the volume to full and show a sleepy face.

```microbit
instrument = "" 
playing = false
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

--- /task ---

### Press A for melody

--- task ---

Check the micro:bit is _not_ set to be a **Melody** instrument.

```microbit
input.onButtonPressed(Button.A, function () {
    if (instrument != "Melody") {
        instrument = "Melody"
        playing = true
        basic.showString("M")
    }
})
```

--- /task ---

--- task ---

**Test**: 
Press Button A to start playing the melody.
The micro:bit will show ‘M’.

--- /task ---

### Press B for bass

Press Button B to ask another micro:bit to be the Bass.

--- task ---

```microbit
input.onButtonPressed(Button.B, function () {
    radio.sendString("Bass")
})
```

--- /task ---

### Receive the Bass message

If a micro:bit is not doing anything and hears "Bass", it starts the Bass part.

--- task ---

Check the micro:bit is not set to an instrument.
If it hears 'Bass', it starts the Bass and shows ‘B’.

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

--- /task ---

### Play instruments together

Melody micro:bit plays its tune, then send a signal to tell the Bass when to play.

--- task ---

You can use the melody you created in the last step!

```microbit
basic.forever(function () {
    if (instrument == "Melody" && playing) {
        music.play(music.stringPlayable("G F G A G F A E ", 120), music.PlaybackMode.UntilDone)
        radio.sendString("newBar")
    }
})
```

--- /task ---

### The bass joins in

When Bass receives 'newBar', it plays in time with the melody.

This Bass works well with our Melody - you can make your own!

--- task ---

Add these blocks inside the else in `on radio received`{class:"microbitradio"}.

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

--- /task ---

--- task ---

**Test**
+ Press A to start the melody.
+ Press B to start the bass on another micro:bit.

--- /task ---

### Pause and play again

--- task ---

Check if a micro:bit is set as an instrument.

If it is, change the playing state.

```microbit
input.onGesture(Gesture.Shake, function () {
    if (instrument != "") {
        playing = !(playing)
        basic.showIcon(IconNames.Asleep)
    }
})
```

--- /task ---

--- task ---

**Test**: 
- Shake the micro:bit to pause the music and show a sleepy face..
- Shake again to start.
--- /task --- 

--- task ---

TODO:

SHARE

--- /task ---