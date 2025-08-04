## Challenge: build a band

Use radio to build a micro:bit band!

One micro:bit will play the **Melody**.
The other micro:bit will play the **Bass**.

--- task ---
## Set up

1. Open the `Variables`{:class='microbitvariables'} menu and click **Make a Variable**.

Name your new variable `instrument`. 

--- /task ---

--- task ---

2. From the `Text`{:class='microbittext'} menu, drag a blank string block inside the `0`.

```microbit
instrument = "" 
playing = false
```

--- /task ---

--- task ---
3. Add this code, which will: 
- Tell the micro:bit that nothing is playing yet.
- Set a radio group so the micro:bits can talk to each other. Both micro:bits must be in the same **radio group**.
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
### Press A for melody

4. Check the micro:bit is _not_ set to be a **Melody** instrument.

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

5. **Test**: Press Button A to start playing the melody.
The micro:bit will show ‘M’.

--- /task ---


--- task ---
### Press B for bass

6. Add code so that you can press Button B to ask another micro:bit to be the Bass.

```microbit
input.onButtonPressed(Button.B, function () {
    radio.sendString("Bass")
})
```

--- /task ---


--- task ---
### Receive the Bass message

If a micro:bit is not doing anything and hears 'Bass', it starts the Bass part.

7. Check the micro:bit is not set to an instrument.
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

--- task ---
### Play instruments together

8. The Melody micro:bit plays its tune, then sends a signal to tell the Bass when to play.

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

9. When Bass receives 'newBar', it plays in time with the melody.

This Bass works well with our Melody - you can make your own!

Add these blocks inside the else in `on radio received`{:class="microbitradio"}:

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

10. **Test**
+ Press A to start the melody.
+ Press B to start the bass on another micro:bit.

--- /task ---

--- task ---
### Pause and play again

11. Check if a micro:bit is set as an instrument.

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

12. **Test**: 
- Shake the micro:bit to pause the music and show a sleepy face..
- Shake again to start.
--- /task --- 

Share your tune with us!

[[[microbit-share]]]