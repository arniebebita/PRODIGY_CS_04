# PRODIGY_CS_04
Prodigy Cyber Security Internship - Task 4 - Simple Keylogger

Create a basic keylogger program that records and logs keystrokes. Focus on logging the keys pressed and saving them to a file. Note: Ethical considerations and permissions are crucial for projects involving keyloggers.

[Please do check out the attached keylogger.py file.]

This Python script is a basic keylogger, which records the keys pressed on the keyboard and writes them to a file named “keylog.txt”. Here’s a step-by-step breakdown of what the code does:

from pynput import keyboard: This line imports the keyboard module from the pynput library, which allows the script to monitor and control the user’s keyboard.

def keyPressed(key): This function is defined to handle a key press event. It takes one argument, key, which represents the key pressed.

print(str(key)): This line prints the string representation of the pressed key to the console.

try: char = key.char: This line attempts to get the character representation of the key pressed. If the key pressed does not have a character representation (like a function key), it raises an AttributeError.

except AttributeError: print("Error getting char"): This line catches the AttributeError raised when the key pressed does not have a character representation, and prints an error message to the console.

with open("keylog.txt", 'a') as logkey: logkey.write(char): This line opens the file “keylog.txt” in append mode (‘a’), and writes the character representation of the key pressed to the file. The file is automatically closed after the write operation due to the use of the with statement.

if __name__=="__main__":: This line checks if the script is being run directly (not being imported as a module). If it is, the code within this block is executed.

with keyboard.Listener(on_press=keyPressed) as listener: listener.join(): This line creates a keyboard.Listener object that listens for key press events. When a key is pressed, it calls the keyPressed function. The listener.join() method starts the event loop and blocks the main thread until the listener stops, which in this case is when the script is terminated. The with statement ensures that the listener is properly cleaned up when it’s no longer needed.
