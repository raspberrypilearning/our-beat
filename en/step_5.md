## micro:bit V2 Drum loop

The micro:bit V2 has drum sounds you can use. These are not available in the micro:bit V1.

Create a drum pattern and use buttons to play bass notes.

### Set the tempo!

There is no pattern editor for drums, but you can still create a drum beat!

--- task ---

From the `Music`{:class='microbitmusic'} menu, drag a `set tempo`{:class='microbitmusic'} block inside the `on start`{:class='microbitbasic'} block on the Editor panel.

--- /task ---

### Trigger the drums!

--- task ---

From the `Input`{:class='microbitinput'} menu, drag a `on logo`{:class='microbitinput'} block to the Editor panel.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
})
```

--- /task ---

### Drum loop

--- task ---

From the `Loops`{:class='microbitloops'} menu, drag a `while`{:class='microbitloops'} block inside the `on logo`{:class='microbitinput'} block.

Change `false`{:class='microbitlogic'} to `true`{:class='microbitlogic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
    }
})
```

--- /task ---

### First - the kick drum

--- task ---

From the micro:bit (V2) section of the `Music`{:class='microbitmusic'} menu, drag a `play (🎵 ---)`{:class='microbitmusic'} block and place it in the `while`{:class='microbitloops'} block.

Click the 🎵 symbol, then 'Gallery' and choose the 'Kick Drum'.

Change `until done`{:class='microbitmusic'} to `in background`{:class='microbitmusic'}.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
    }
})
```

--- /task ---

### Add a pause 

--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag a `pause`{:class='microbitbasic'} block under your Kick Drum sound.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(500)
    }
})
```

--- /task ---

--- task ---

From the `Music`{:class='microbitmusic'} menu, drag a `1 beat`{:class='microbitmusic'} block and place it in the `500`.

```microbit
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    while (true) {
        music.play(music.createSoundExpression(WaveShape.Square, 200, 1, 255, 0, 100, SoundExpressionEffect.None, InterpolationCurve.Curve), music.PlaybackMode.InBackground)
        basic.pause(music.beat(BeatFraction.Whole))
    }
})
```

--- /task ---

### A four-four beat

--- task ---

Copy your `play (🎵 ---)`{:class='microbitmusic'} and `pause`{:class='microbitbasic'} blocks three times, so you have four beats and four pauses.

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
--- /task --- 

--- task ---

**Test**: Press the touch logo and listen to your beat.
  
--- /task --- 

--- task ---

Change the 2nd and 4th drum sound from 'Kick Drum' to 'Snare'

--- /task ---

--- task ---

**Test**: Press the touch logo and listen to your beat.
  
--- /task --- 

### Make the beat your own!

--- task ---

Experiment with different pauses and drum sounds.

**Note**: Your pauses should always add up to 4 beats.

Here is an example:

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

--- /task ---

--- task ---

**Try**: Change the tempo value 

**Test**: Press the touch logo and listen to your beat.

--- /task ---

### Add some bass tones

Trigger the bass tones with buttons.

--- task ---

From the `Input`{:class='microbitinput'} menu, drag two `on button`{:class='microbitinput'} blocks to the Editor panel.

Change one to use Button 'B'.

```microbit
input.onButtonPressed(Button.A, function () {
})
input.onButtonPressed(Button.B, function () {
})
```

--- /task ---

--- task ---

From the `Music`{:class='microbitmusic'} menu, drag two `play tone`{:class='microbitmusic'} blocks and place one in each `on button`{:class='microbitinput'} block.

We have used 'Low C' and 'Low F', but you can use any tone you like!

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(131, music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
input.onButtonPressed(Button.B, function () {
    music.play(music.tonePlayable(175, music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

--- /task ---

--- task ---

**Test**: Touch the logo to play your drum loop and press the A and B buttons in time with the beat!

--- /task ---

### Light and movement

--- task ---

**Try**: Replace the tone (e.g. 'Low C') with the `light level`{:class='microbitinput'} so the tone changes as you move your hand over your micro:bit. 

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.lightLevel(), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

Or, use the `acceleration (mg) x`{:class='microbitinput'} value to change the tone as you move it!

```microbit
input.onButtonPressed(Button.A, function () {
    music.play(music.tonePlayable(input.acceleration(Dimension.X), music.beat(BeatFraction.Whole)), music.PlaybackMode.InBackground)
})
```

--- /task --- 

Share your tune with us!

[[[microbit-share]]]