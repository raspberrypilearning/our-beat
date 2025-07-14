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
// Start as a blank instrument
playing = false
// Tell the micro:bit that nothing is playing yet.
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

--- /task ---

### Create your project

Create and name your project. 

--- task ---

Click on the **New Project** button.

<img src="images/new-project-button.png" alt="The New Project button inside MakeCode." width="250"/>

--- /task ---

--- task ---

Give your new project a name (e.g. 'Our Club') and click **Create**.

--- /task ---

--- task ---

From the `Music`{:class="microbitmusic"} menu, drag the `play melody ... at tempo 120 (bpm) [until done]`{:class="microbitmusic"} block and place it inside the `forever`{:class="microbitbasic"} block.

```microbit
instrument = ""
playing = false
radio.setGroup(22)
music.setVolume(127)
basic.showIcon(IconNames.Asleep)
```

--- /task ---

--- task ---

Click on the melody to open the Editor.

--- /task ---

--- task ---

Switch to the Gallery and choose a melody.

See the melody pattern in the Editor. 

--- /task ---

--- task ---

Press the Play ▶️ button to hear the chosen melody.

See the melody pattern in the Editor. 

--- /task ---

--- task ---

**Test**
+ Try different melodies and hear the changes.
+ Change the notes to change the melody

--- /task ---

--- task ---

Keep experimenting until you hear a melody you like.

--- /task ---

--- task ---

When you make a change to a code block in the code editor panel, the simulator will restart.

**Test**
+ The melody should play until it is done (and then loop because of the `forever`{:class="microbitbasic"} block)

--- /task --- 

--- task ---

TODO:

SHARE

--- /task ---