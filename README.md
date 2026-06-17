# Quiz CLI

Quiz CLI is an interactive terminal-based quiz game built with Node.js. It lets users choose a quiz category, select how many questions to answer, track their score and progress, and review incorrect answers with explanations at the end.

## Features

- Interactive command-line experience in the terminal
- Category-based quizzes:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Choice of question count:
  - All questions
  - 3 questions
  - 5 questions
- Progress display while answering questions
- Score summary and feedback at the end of each run
- Review of incorrect answers with correct responses
- Question explanations shown during the quiz
- Built using only Node.js built-in APIs
- No external dependencies

## Prerequisites

- Node.js **18 or newer**
- A terminal capable of running Node.js CLI applications

## Installation

This project has no external npm dependencies.

From the repository root, go to the application directory:

```bash
cd test-app
```

If you want to install dependencies or create a lockfile, you can still run:

```bash
npm install
```

## Running the App

Start the quiz game with:

```bash
npm start
```

This runs:

```bash
node index.js
```

### What to expect

- A welcome banner appears in the terminal
- You select a category
- You choose how many questions to answer
- You answer multiple-choice questions by entering a number
- Your score and progress are shown
- You can choose to play again after finishing

## Testing

Run the test suite with:

```bash
npm test
```

This runs:

```bash
node --test
```

## How to Add or Edit Questions

Quiz content is stored in:

```text
data/questions.json
```

Each category contains:

- a `name`
- a `questions` array

Each question includes:

- `question` — the prompt text
- `options` — the multiple-choice answers
- `answer` — the index of the correct option
- `explanation` — feedback shown after the question

### Example structure

```json
{
  "categories": {
    "example": {
      "name": "Example Category",
      "questions": [
        {
          "question": "Your question here?",
          "options": ["Option A", "Option B", "Option C", "Option D"],
          "answer": 0,
          "explanation": "Why this answer is correct."
        }
      ]
    }
  }
}
```

### Notes when editing

- Keep `answer` aligned with the zero-based index of the correct option
- Make sure each question has a valid `options` array
- Add new categories under `categories`
- The app loads the JSON file at runtime, so changes are reflected on the next run

## Project Structure

```text
test-app/
├── data/questions.json   # Quiz categories and questions
├── src/colors.js         # ANSI styling helpers for terminal output
├── src/input.js          # Readline helpers for prompts and selections
├── src/quiz.js           # Core quiz logic, scoring, progress, results
├── index.js              # CLI entry point and app flow
└── package.json          # Scripts, metadata, and Node.js engine requirement
```

## Notes

- The app is fully interactive and runs in the terminal
- It uses ES Modules
- It relies only on built-in Node.js APIs:
  - `fs/promises`
  - `url`
  - `path`
  - `readline`
- The repository currently does not include a separate `README.md`
- `package.json` lists the project license as **MIT**, but no standalone `LICENSE` file is present in the repository

## Contributing

Contributions are welcome. If you want to improve the quiz:

- add new questions or categories
- refine terminal output styling
- improve quiz flow or feedback messaging
- expand test coverage

Please keep changes consistent with the current Node.js 18+ and no-external-dependencies setup.

## License

License information is not confirmed by a standalone `LICENSE` file in the repository.  
`package.json` currently lists the project as **MIT**.
