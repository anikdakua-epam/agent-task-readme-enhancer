# Quiz CLI

A small Node.js command-line quiz app for practicing JavaScript, Node.js, and general programming knowledge. The app is educational and demonstrates Node.js concepts such as `async/await`, `readline`, file I/O, ES modules, and ANSI colors.

## Features

- Interactive terminal quiz experience
- Category selection:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Configurable question count: all, 3, or 5 questions
- Randomized question order
- Score tracking and final results summary
- Explanations shown after each answer
- Progress bar during the quiz
- Review of incorrect answers at the end
- Colorized terminal output
- No external dependencies

## Prerequisites

- Node.js 18 or newer

## Installation

1. Clone the repository.
2. Open the `test-app/` directory.
3. Make sure Node.js 18+ is installed.

No external packages are required.

## Usage

From the `test-app/` directory, run:

```bash
npm start
```

The app will:

1. Show the available quiz categories
2. Let you choose how many questions to answer
3. Present questions one by one in random order
4. Show explanations and your score at the end
5. Offer a chance to play again

## Available scripts

Defined in `test-app/package.json`:

- `npm start` — runs `node index.js`
- `npm test` — runs `node --test`

## Project structure

```text
test-app/
├── index.js
├── package.json
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### Key files

- `test-app/index.js` — application entry point and main quiz flow
- `test-app/src/input.js` — terminal input helpers built with Node.js `readline`
- `test-app/src/quiz.js` — quiz logic, scoring, progress, and results display
- `test-app/src/colors.js` — ANSI color helpers
- `test-app/data/questions.json` — quiz questions and answers
- `test-app/package.json` — project metadata and scripts

## How it works / implementation notes

- The app uses ES modules (`import` / `export`) throughout.
- `index.js` loads quiz data from `data/questions.json` using `node:fs/promises`.
- User interaction is handled with Node.js `readline` wrappers in `src/input.js`.
- `src/quiz.js` shuffles questions, tracks score, renders a progress bar, and reviews incorrect answers.
- `src/colors.js` provides ANSI escape-based terminal styling without third-party packages.
- The quiz is intentionally simple and focused on core Node.js concepts.

## Adding or editing questions

All quiz content lives in `test-app/data/questions.json`.

- Add new categories by following the existing `categories` structure.
- Add questions with the same shape used by the current entries:
  - `question`
  - `options`
  - `answer`
  - `explanation`
- Keep `answer` aligned with the index of the correct option.

## Contributing

This repository does not include a `CONTRIBUTING.md` file, so there are no repository-specific contribution guidelines documented here.

## License

MIT