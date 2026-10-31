# Human Body Quiz

A Java quiz game with an animated **JavaFX login page** and a **console-based quiz**.

## Features
- **Login / Register** window built with JavaFX: particles that react to the cursor and a 3D beating heart that spins when you move the mouse near it
- Passwords stored as SHA-256 hashes (`users.txt`, created at runtime, not committed)
- 10 random questions per game from a Human Body question bank (shuffled options every game)
- 15-second limit per question, speed bonus, streak multiplier (up to x2)
- Lifelines: `F` = 50-50, `S` = Skip
- Fun fact after each answer, rank title at the end, Top 10 leaderboard

## Requirements
- JDK 17+
- Maven (or Eclipse/VS Code with the JavaFX 21 jars on the classpath)

## Run
```
mvn compile exec:java
```
Or open the project in Eclipse / VS Code and run `quiz.Main`.

## Project structure
```
src/main/java/quiz/
  Main.java          entry point: login window, then console quiz
  LoginApp.java      JavaFX login page (particles + 3D heart)
  ConsoleQuiz.java   console menu, quiz, scoring, leaderboard
  Question.java      question model
  QuestionBank.java  the questions (edit here to add more)
  UserManager.java   register / login / scores
src/main/resources/
  login.css          login page styling
```

## Adding questions
Add one line in `QuestionBank.java`:
```java
ALL.add(new Question("Question?", "Right answer", "Fun fact.", "Wrong 1", "Wrong 2", "Wrong 3"));
```
