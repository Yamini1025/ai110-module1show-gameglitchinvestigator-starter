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
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
