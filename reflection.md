# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

  The game was not properly responding to user input when giving “Too High” or “Too Low” feedback. It often gave incorrect responses. The “New Game” button was not fully resetting the game state. It only reset the secret number, but did not reset the guess history or attempt count. The debug history had an issue where the first entry was ignored or not recorded properly. The history would only start behaving correctly after the second or third entry. Ideally, the first entry should be stored correctly.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

  I used Claude within VScode. I did not explicitly rely on AI suggestions for this project. I mainly solved the issues myself while coding in the IDE. I did not use AI in a way that produced incorrect suggestions, so I do not have an example here.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

  Manual testing by interacting with the app

Running pytest tests, especially focusing on the parts marked with FIXME in app.py. I tested the core game logic using pytest. AI helped me better understand how testing works conceptually, even though I didn’t directly rely on it to generate tests.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

Streamlit reruns the entire script every time the user interacts with the app. Since the secret number was not stored in session state, it kept getting regenerated on every rerun. Streamlit works by rerunning the whole script whenever something changes (like a button click). Without session state, it forgets everything and starts fresh each time. Session state acts like memory, allowing the app to keep important values between reruns.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

I want to continue using testing and session state effectively, and focus on solving one problem at a time. I would always verify AI suggestions, but always test and confirm they work correctly.
