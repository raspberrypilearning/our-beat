## A simple melody

Create your first tune!

\--- task ---

Open the MakeCode editor at [makecode.microbit.org](https://makecode.microbit.org){:target="_blank"}.

\--- /task ---

### ¿Primer proyecto de micro:bit?

[[[makecode-tour]]]

\--- task ---

### Crea tu proyecto

Create and name your project:

Click on the **New Project** button.

<img src="images/new-project-button.png" alt="The New Project button inside MakeCode." width="250"/>

\--- /task ---

\--- task ---

Give your new project a name (e.g. 'Our Club') and click **Create**.

\--- /task ---

\--- task ---

### Make a melody

From the `Music`{:class="microbitmusic"} menu, drag the `play melody ... at tempo 120 (bpm) [until done]`{:class="microbitmusic"} block and place it inside the `forever`{:class="microbitbasic"} block.

```microbit
basic.forever(function () {
    music.play(music.stringPlayable("- - - - - - - - ", 120), music.PlaybackMode.UntilDone)
})
```

\--- /task ---

\--- task ---

Click on the melody to open the Editor.

\--- /task ---

\--- task ---

Switch to the Gallery and choose a melody.

See the melody pattern in the Editor.

\--- /task ---

\--- task ---

Click the play ▶️ button to hear the chosen melody.

See the melody pattern in the Editor.

\--- /task ---

\--- task ---

### Listen and tune

**Test**

- Try different melodies and hear the changes
- Change the notes to change the melody

\--- /task ---

\--- task ---

Keep experimenting until you hear a melody you like.

\--- /task ---

\--- task ---

Cuando haces un cambio a un bloque de codigo en el panel del editor de codigo, el simulador se reiniciara.

**Test**

- The melody should play until it is done (and then loop because of the `forever`{:class="microbitbasic"} block)

\--- /task ---
