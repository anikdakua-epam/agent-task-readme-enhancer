# Quiz CLI

## High-Level Description

Quiz CLI is an interactive command-line quiz game built with Node.js. It loads quiz questions from a JSON file, lets the user choose a category and number of questions, and then walks through each question one by one. The application uses ES modules, the built-in Node.js `fs`, `path`, `url`, and `readline` APIs, and a small color utility to make the terminal output more readable.

The repository contains a single CLI application located in `test-app/`.

## Features

- Interactive terminal quiz experience
- Category selection from the available question groups:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Question count selection:
  - All questions
  - 3 questions
  - 5 questions
- Randomized question order within a quiz session
- Immediate correct/incorrect feedback after each answer
- Explanations shown for questions when available
- Final score summary with performance message
- Review of incorrect answers at the end of the quiz
- ANSI color styling for terminal output without external dependencies
- Node.js ES module structure with separated input, quiz, and color utilities

## Project Structure

```text
README.md

test-app/
├── data/
│   └── questions.json
├── index.js
├── package.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File overview

- `test-app/index.js` - Application entry point. Loads questions, handles the main game loop, and coordinates category and question selection.
- `test-app/src/quiz.js` - Quiz game logic, including shuffling questions, tracking score, rendering progress, and showing results.
- `test-app/src/input.js` - Readline-based helpers for prompting, selecting options, confirming choices, and waiting for Enter.
- `test-app/src/colors.js` - ANSI color helpers used for terminal styling.
- `test-app/data/questions.json` - Quiz content organized by category.
- `test-app/package.json` - Project metadata, scripts, module type, and Node.js engine requirement.

## Getting Started

### Prerequisites

- Node.js 18.0.0 or newer

### Run the application

From the `test-app/` directory:

```bash
npm start
```

This runs:

```bash
node index.js
```

### Available scripts

- `npm start` - Starts the quiz CLI
- `npm test` - Runs Node.js tests with `node --test`

### How it works

1. The app loads quiz data from `data/questions.json`.
2. You choose a category.
3. You choose how many questions to answer.
4. The quiz asks each question in sequence.
5. Results are shown at the end, including a review of incorrect answers.

### Notes

- The project uses ES modules (`"type": "module"` in `package.json`).
- Questions are stored in JSON and are loaded at runtime.
- Terminal colors are handled with built-in ANSI escape codes.
