####Video link:

####MEMORY KART####

##Game description:

The python code creates a memory and reaction-based game on a Raspberry Pi using the following GPIO components: LEDs, buttons, and a buzzer. The game consists of 5 levels and you start the game pressing the start button after running the program, with each level presenting a random sequence of LED lights and corresponding Morse code sounds using the buzzer to indicate the next round. Players must memorize the sequence as it plays, then replicate it by pressing the relevant buttons. If the player accurately reproduces the sequence, they move up to the next level with the next levels number in Morse code in beep form as feedback. If they make a mistake, the game ends with “You lose” in Morse code beep form. The goal is to complete all rounds without errors, and if successful, players receive congratulations with “You win” in Morse code beep form. The game can be interrupted at any time by pressing Ctrl+C, and it ensures that the program quits.

##Who does what?
Rainouw: Design, build.

Almarie: Design, build.

Tara: Document, build, code creator, code reviewer.

Keagan:  Code creator, build, document assistant, code reviewer.


##What each function does:

1. **Imports**: The code starts by importing the necessary modules from the `gpiozero` library, including ‘LED’, ‘Button’, ‘Buzzer’, ‘Time’ and ‘Random’, that allows us to control the lights and buttons on the Raspberry Pi.

2. **Initialization**: LEDs, buttons, and the buzzer locations on the GPIO pins.

3. **morse_code_dict Dictionary**: Morse code is placed in a dictionary to be used when called.

4. **blink_morse_code Function**: The morse code dictionary is called in this function. The for loop loops through the letters or numbers being printed and using the buzzer the correct symbol will be called to beep out the message.

5. **Declared basic variables to ensure functionality of game**: game_over- If the game is over the variable will be true and the program will stop otherwise it will carry on. Wait- The program waits for the user to press the button. Rounds- It declares that there are only 5 rounds. Index- Keeps track of the response to be compared to button index later on and if they are equal you move onto the next round. Allowed- Will be used to check within an if statement if the user is allowed to press the button after the lights have flashed. 

6. **play_sequence Function**: This function takes a sequence of colors as input and plays them. It turns on the corresponding LEDs to create a visual and auditory pattern for the player to memorize.

7. **colourSequence Function**: Returns an array of random selected LED’s.

8. **buttons 0-4 Variables**: Checks if correct button is pressed for each light using an unnamed function and in that function it uses the ‘checkIfCorrect’ function. If we don’t do it that way it will be initialized and we don’t want that.

9. **While true**: This is used for when you press the start button. It will ask the user to press start to start the game. 

10. **after the start button**: The score is set to 0. The first for loop sets the first level to 1 and the morse code 1 will beep to indicate the first round and the light sequence will start by calling the ‘play_sequence’ function.

11. **for loop inside the for loop**: It allows the user to press the buttons a set amount of times to the length of the sequence. 

12. **if score >= rounds**: It compares the score to the set amount of rounds and if the score is less than the rounds the morse code for ‘You lost’ will beep out of the buzzer but if the score is equal to the rounds it will beep out ‘You won’.
 
##Citation:

Chat Gpt – We used Chat Gpt to fix a few inconveniences this includes the lambda function with the buttons when_pressed and the colourSequence function was inspired by chatGpt it also fixed the issue related to variable scope in checkIfCprrect function where it said to use the global keyword.
