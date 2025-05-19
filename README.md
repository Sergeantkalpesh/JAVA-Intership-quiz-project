1. Login Screen
The application starts with a Login window, where I used Java Swing components like JFrame, JLabel, JTextField, and JButton. The user is asked to enter their name in a text field. When the "Next" button is clicked, an ActionListener captures the event, retrieves the user’s name from the text field, and moves to the next screen. This interaction is handled through event-driven programming.

How it works:

A JFrame is created for the login screen.

A JTextField accepts user input.

Clicking the button triggers an ActionEvent, and the program stores the name and proceeds to the Rules screen.

2. Rules Screen
After logging in, the user is taken to a new screen displaying the quiz rules. I used a JTextArea or JLabel to display the rules, and two buttons: "Start" to begin the quiz and "Back" to return to the login screen.

How it works:

This screen is another JFrame with multiple components laid out using layout managers (like BorderLayout or null for custom positioning).

Clicking "Start" opens the quiz screen.

Clicking "Back" disposes the current frame and reopens the login screen.

3. Quiz Screen
This is the main part of the application. The quiz has 10 questions (randomly selected from a pool of 50, if you've added that feature), each with four options. I used JRadioButton components grouped with a ButtonGroup to ensure only one answer is selected at a time. The questions and options are displayed using JLabel and JRadioButton.

How it works:

Each question is displayed on a JLabel.

Four JRadioButtons display the answer options.

A ButtonGroup groups them so only one can be selected at a time.

A "Next" button shows the next question.

An array stores the selected answer, and the index moves forward on each "Next" click.

A "Submit" button appears on the last question to finish the quiz.

4. Timer Functionality
Each question is given a 15-second timer. I implemented this using Java’s Timer class or by overriding the paint() method and using a countdown with Thread.sleep() and repaint().

How it works:

A timer runs on a separate thread.

It updates a countdown on the screen.

If time runs out before the user answers, the application automatically moves to the next question and saves the answer as blank.

5. 50-50 Lifeline
I included a lifeline feature where the user can eliminate two wrong answers for a question. I added a "Lifeline" button which, when clicked, disables two incorrect JRadioButton options.

How it works:

I hardcoded which two options to disable for specific questions.

On click, the button disables two incorrect radio buttons using .setEnabled(false).

The lifeline can only be used once, tracked using a boolean flag.

6. Answer Storage & Evaluation
As the user navigates through the quiz, their selected answers are stored in an array. Another array holds the correct answers for each question.

How it works:

On each "Next" or "Submit" click, the selected radio button’s value is stored.

After submission, a loop compares user answers with correct answers and calculates the total score.

7. Result Screen
Once the quiz ends, the application shows the final score in a new window using JLabel.

How it works:

A new JFrame displays the total score.

It fetches the user’s name and score and shows a thank-you message.

Summary of Concepts Used:
Swing components: JFrame, JLabel, JTextField, JRadioButton, ButtonGroup, JButton

Event Handling: ActionListener

Layout Managers: for arranging components

Multithreading or Timers: for the countdown feature

Arrays/Lists: for storing questions, options, and answers

Conditional Logic: for evaluating answers and managing the lifeline
