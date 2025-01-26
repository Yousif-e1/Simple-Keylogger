# Simple-Keylogger
- This Program listens for keyboard events (key presses and releases) using the pynput library, and logs the pressed keys into a file called keylogs.txt.

# How it Work
1) Key Press Event (on_press function):
- The on_press(key) function is called whenever a key is pressed.
- It tries to access the key.char attribute, which represents the character corresponding to the key. If the key is a regular alphanumeric character (like 'a', '1', etc.), it is written to the keylogs.txt file.
- If the key doesn't have a char attribute (for example, special keys like Shift, Ctrl, etc.), it writes the string representation of the key (key) to the file. This includes special keys such as keyboard.Key.space for the spacebar.

2) Key Release Event (on_release function):
- The on_release(key) function is called when any key is released.
- If the Escape key (keyboard.Key.esc) is pressed, the listener stops listening for further keyboard events and the program exits by returning False.

3) Listener Setup:
- The keyboard.Listener object listens for keyboard events. It takes two arguments:
- on_press: A callback function that is called on key press.
- on_release: A callback function that is called on key release.
- listener.join() ensures the listener will continuously listen for events until the program is stopped, either manually or when the Escape key is pressed.

### Key Points:
- Logging: Key presses are logged into keylogs.txt. Every time a key is pressed, the corresponding character (or special key name) is written to the file.
- Escape to Stop: Pressing the Escape key will stop the listener and exit the program.
- File Handling: The file is opened in append mode ("a"), so the new keypresses are added to the end of the file, preserving previous logs.
