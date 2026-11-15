# 📚 QuizMaster

A lightweight, front-end-only quiz web app for exam practice. Pick an exam, choose a subject, answer timed multiple-choice questions, and review explanations and your progress, all in the browser with no backend or build step.

## Academic context

This project was built as a subject mini project during my 2nd semester of B.Tech.

## Features

- **Multiple exams and subjects**
  - **JEE**: Physics, Chemistry, Mathematics, Mixed
  - **GATE**: Aptitude, Technical, Mixed
  - **KEAM**: Physics, Chemistry, Mathematics, Mixed
  - **Class 11 and Class 12**: Physics, Chemistry, Mathematics, Biology, Mixed
- **Mixed mode**: draws a shuffled set of 20 questions across all subjects of an exam
- **Timed quizzes** with a live timer, progress bar and question counter
- **Previous / Next navigation**, with your selected answers kept as you move around
- **Results screen** showing score, correct and wrong counts, percentage and time taken
- **Answer review** with an explanation for every question
- **Performance analytics** (saved in your browser via `localStorage`):
  - total quizzes taken, average score, best score
  - study streak
  - recent quiz history
  - per-subject performance
- **Dark mode** toggle that remembers your choice
- **Responsive design** with a study-resources section (cheat sheets, textbooks, video lectures, previous papers)

## Tech stack

- HTML5
- CSS3
- Vanilla JavaScript (no frameworks, no dependencies)

## Project structure

```
QUIZ/
├── index.html   # Page layout: hero, quiz selection, analytics, resources, quiz overlay
├── styles.css   # Styling, animations, dark mode
└── script.js    # Question bank, quiz logic, timer, analytics
```

## Getting started

No installation is needed.

1. Clone the repository:
   ```bash
   git clone https://github.com/adithyannm67-crypto/QUIZ.git
   cd QUIZ
   ```
2. Open `index.html` in any modern browser.

Optionally, serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## How it works

1. Choose an exam card and a subject on the **Quizzes** section.
2. The quiz opens in a full-screen overlay with a timer running.
3. Select an option for each question and move through them with **Previous** and **Next**.
4. Submit on the last question to see your score, then open **View Answers & Explanations**.
5. Your result is stored in `localStorage` and reflected in the **Analytics** section.

## Adding or editing questions

All questions live in the `comprehensiveQuizData` object at the top of `script.js`, organized as `exam → subject → array of questions`:

```js
{
  question: "What is the SI unit of force?",
  options: ["Joule", "Newton", "Watt", "Pascal"],
  correct: 1,            // zero-based index of the correct option
  explanation: "The SI unit of force is Newton (N)..."
}
```

To add a new exam, add a new key to `comprehensiveQuizData` and a matching card with `startQuiz('<exam>', '<subject>')` buttons in `index.html`.

## Data and privacy

Quiz history, streaks and the dark-mode preference are stored only in your browser's `localStorage`. Clearing site data resets your analytics.

## Possible improvements

- Expand the question bank for every exam and subject
- Add per-question timers and negative marking
- Wire up the Study Resources links to real material
- Add user accounts and cloud-synced progress

## License

No license has been specified yet.
