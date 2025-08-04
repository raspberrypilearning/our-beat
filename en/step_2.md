## A simple melody

Create your first tune!

--- task ---

1. Open the MakeCode editor at [makecode.microbit.org](https://makecode.microbit.org){:target="_blank"}.

--- /task ---

### First micro:bit project?

[[[makecode-tour]]]

--- task ---
### Create your project

2. Create and name your project: 

Click on the **New Project** button.

<img src="images/new-project-button.png" alt="The New Project button inside MakeCode." width="250"/>

--- /task ---

--- task ---

3. Give your new project a name (e.g. 'Our Club') and click **Create**.

--- /task ---

--- task ---
### Make a melody

4. From the `Music`{:class="microbitmusic"} menu, drag the `play melody ... at tempo 120 (bpm) [until done]`{:class="microbitmusic"} block and place it inside the `forever`{:class="microbitbasic"} block.

```microbit
basic.forever(function () {
    music.play(music.stringPlayable("- - - - - - - - ", 120), music.PlaybackMode.UntilDone)
})
```

--- /task ---

--- task ---

5. Click on the melody to open the Editor.

--- /task ---

--- task ---

6. Switch to the Gallery and choose a melody.

See the melody pattern in the Editor. 

--- /task ---

--- task ---

7. Click the Play ▶️ button to hear the chosen melody.

See the melody pattern in the Editor. 

--- /task ---

--- task ---
### Listen and Tune

8. **Test**
- Try different melodies and hear the changes.
- Change the notes to change the melody

--- /task ---

--- task ---

9. Keep experimenting until you hear a melody you like.

--- /task ---

--- task ---

10. When you make a change to a code block in the code editor panel, the simulator will restart.

**Test**
- The melody should play until it is done (and then loop because of the `forever`{:class="microbitbasic"} block)

--- /task --- 
