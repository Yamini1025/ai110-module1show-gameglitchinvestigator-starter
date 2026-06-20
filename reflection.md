# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
The game had a simple UI with instructions to enter a number between 1 and 10. It also displayed how many attempts
were left, with a text box and buttons to submit the user's guess and start a new game. It also had a toggle button to show hints. 
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
  The hints were showing opposite to what they were supposed to show, and as I tried more attempts I noticed that the game ended before the last attempt.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
Guess of | Go HIGHER hint   |  Go LOWER hint  |     none
20       |                  |                 |

Switched | Reset game and   |  Continued with |   none
to another |   attempts     |  same # attempts |
difficulty

Clicked   | Display updated  |  Did not change   |   none
Submit    |  attempts        | attempts left #    |
button
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used Copilot on this project.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
The AI tool suggested to switch the 'Go LOWER' and 'Go HIGHER' statements in the check_guess method. I verified the result mainly by rerunning the app and submitting inputs, and I saw that the error had been fixed.
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
The AI initially treated the negative attempts display as a UI problem and suggested only preventing negative values from being shown. This was misleading because the root cause was a game-state synchronization issue when changing difficulty levels. I verified this by testing different difficulty changes in the running application and observing that the attempt count was not being reset correctly.


---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I considered a bug fixed only after testing it in the Streamlit application and confirming that the incorrect behavior didn't happen any more. I compared the expected behavior with the actual behavior after making changes and verified that the results matched what the game was supposed to do.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  I used pytest to test the check_guess function. I created tests to verify that a guess greater than the secret number return "Too High", a guess lower than the secret number returned "Too Low", and a correct guess returned "Win". All tests passed, which confirmed that the core game logic was working correctly.
- Did AI help you design or understand any tests? How?
Yes, AI helped generate simple pytest test cases for the check_guess function. The generated tests gave me a starting point for verifying the game logic, and I used the test results together with manual testing to confirm that my fixes worked correctly.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
I learned that Streamlit reruns the entire script whenever a user interacts with the app, such as clicking a button or changing a setting. Because the script restarts frequently, variables would normally reset each time. Session state acts like memory for the application and allows values such as the secret number, score, and attempt count to persist across reruns. Without session state, the game would lose its progress every time the page updated.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
  One strategy I want to reuse is isolating bugs and focusing on one issue at a time. Creating separate AI chats for individual problems made it easier to understand each bug and evaluate the AI's suggestions.
- What is one thing you would do differently next time you work with AI on a coding task?
Next time, I would verify AI suggestions earlier and more frequently instead of assuming that a proposed fix addresses the root cause. I learned that some suggestions only fixed symptoms rather than the actual problem.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
This project showed me that AI-generated code can be helpful for debugging and generating ideas, but it still requires careful review and testing. AI is a useful teammate, but the developer is ultimately responsible for verifying that the code is correct.
