# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
The purpose of the game is to let users guess a randomly generated secret number within a limited number of attempts. The game provides hints after each guess, tracks the player's score, and allows difficulty levels with different ranges and attempt limits.
- [ ] Detail which bugs you found.
I found that the game sometimes displayed incorrect hints, showing "Go HIGHER" when it should have shown "Go LOWER" (and vice versa). Then I found that the displayed range and remaining attempts were not always synchronized with the current game state, causing confusing or incorrect information to appear. I also found that changing the difficulty during a game did not properly reset the game state, which would result in wrong attempt counts and game behavior.
- [ ] Explain what fixes you applied.
I corrected the hint logic by making sure guesses were compared consistently against the secret number, which fixed the wrong high/low feedback. I updated the range and attempts display so that the information shown to the user always reflects the current game state. I modified the difficulty selection logic so that changing the difficulty resets the game state, including the secret number, attempts, score, and history, preventing state inconsistencies.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. <!-- Describe this step -->
User starts a new game on Normal difficulty.
2. <!-- Describe this step -->
User enters a guess of 40.
3. <!-- Describe this step -->
The game displays "Too Low" and updates the score.
4. <!-- Describe this step -->
User enters a guess of 70.
5. <!-- Add more steps as needed -->
The game displays "Too High".
6. User continues guessing until the correct number is entered.
7. The game displays a win message and final score.
8. Changing the difficulty resets the game and generates a new secret number.
**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
# ========================= X passed in 0.XXs =========================
```
python3 -m pytest -q
3 passed in 0.01s

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
