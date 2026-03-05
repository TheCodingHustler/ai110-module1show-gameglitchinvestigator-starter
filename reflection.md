## 💭 Reflection: Game Glitch Investigator

### 1. What was broken when you started?
When I first ran the game, several things were not working correctly. The New Game button didn’t reset the game properly, so the player couldn’t start a new round after losing. The hints were also sometimes wrong because the secret number was being compared as a string instead of a number. Another issue I noticed was that the attempts counter started at 1, which meant the player lost an attempt before even making a guess.

### 2. How did you use AI as a teammate?
I used Claude inside the VS Code IDE to help analyze bugs and understand parts of the code that were confusing. One suggestion that helped was pointing out that the comparison was happening between a string and an integer, which caused incorrect hints. I verified this by checking the variable types and fixing the comparison. One suggestion that didn’t help at first was changing a condition that wasn’t actually related to the bug. I tested it and realized the problem was somewhere else in the code.

### 3. Debugging and testing your fixes
To make sure the bugs were fixed, I ran the game multiple times and tested different scenarios. For example, I changed the difficulty settings and checked that the correct number range was used each time. I also ran `pytest` in the terminal to confirm that all the automated tests passed. AI helped me understand some of the test failures so I could identify the problem faster.

### 4. What did you learn about Streamlit and state?
The secret number kept changing because Streamlit reruns the entire script every time the user interacts with the app. Since the secret number was created in the script itself, it was being regenerated on each rerun. Session state allows Streamlit to store values so they stay the same between reruns. I fixed the issue by saving the secret number in `st.session_state`, which kept the number stable during the game.

### 5. Looking ahead: your developer habits
One habit I want to continue using is testing each fix right after making it. This helped me figure out which changes actually solved the bugs. Next time I work with AI on a coding project, I will double-check its suggestions and test them carefully instead of assuming they are correct. This project showed me that AI can be a helpful partner for debugging, but it still needs verification from the developer.
