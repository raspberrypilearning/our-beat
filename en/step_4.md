## Challenge — Build a band

Use radio to build a micro:bit band!

One micro:bit will play the **melody**.
The other micro:bit will play the **bass**.

--- task ---
## Setup

Open the `Variables`{:class='microbitvariables'} menu and click **Make a Variable**.

Name your new variable `instrument`. 

--- /task ---

--- task ---

From the `Text`{:class='microbittext'} menu, drag a blank string block inside the `0`.

```microbit
instrument = "" 
playing = false
```

--- /task ---

--- task ---
Add this code, which will: 
- Tell the micro:bit that nothing is playing yet.
- Set a radio group so that the micro:bits can communicate with each other. Both micro:bits must be in the same **radio group**.
- Set the volume and show a sleepy face.

```microbit
instrument = "" 
playing = false
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

--- /task ---

--- task ---
### Press 'A' for melody

Check that the micro:bit is _not_ set to be a **melody** instrument.

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

**Test**: Press button A to start playing the melody.
The micro:bit will show ‘M’.

--- /task ---


--- task ---
### Press 'B' for bass

Add code so that you can press button B to tell another micro:bit to be the bass.

```microbit
input.onButtonPressed(Button.B, function () {
    radio.sendString("Bass")
})
```

--- /task ---


--- task ---
### Receive the bass message

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

--- /task ---

--- task ---
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

--- /task ---

--- task ---
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

--- /task ---

--- task ---

**Test**
+ Press A to start the melody
+ Press B to start the bass on another micro:bit

--- /task ---

--- task ---
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

--- /task ---

--- task ---

**Test**: 
- Shake the micro:bit to pause the music and show a sleepy face
- Shake again to start
--- /task --- 

Share your tune with us!

[[[microbit-share]]]
