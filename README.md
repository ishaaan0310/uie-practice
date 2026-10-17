# UIE Practice

A simple quiz app for revising **NPTEL – Understanding Incubation and Entrepreneurship (UIE)**. It covers weeks 0–12 with 230 multiple-choice questions, quick revision notes, a practice mode with instant feedback, and a test mode that works like the real exam.

The whole app is a single `index.html` file. There's no build step, no framework and no backend.

## Features

- **230 questions across 13 weeks**
  - 130 questions from the course assignments (weeks 0–12)
  - 100 extra "likely" questions on the same weekly topics, tagged **New** in the app
  - Original and New sets can be switched on or off independently. Pick no week to use all weeks, for example to practise only the New set
- **Practice mode** checks each answer right away and shows the correct option in green. Correct answers move on automatically; wrong ones wait so you can read the right answer.
  - **Show answers**: revision view with every correct answer already highlighted
- **Test mode** shows no answers until you finish, then gives your score, time taken and a review of every mistake.
  - **Shuffle questions**: ask questions in a random order
  - **Shuffle answer options**: mix up the option order ("All of the above" always stays last)
  - **Show answers instantly**: mark each answer right or wrong as soon as you pick it
- **Mock test**: 65 random questions from the full bank, like the final exam
- **Quick notes**: key ideas for every week, plus tactics for tackling questions you haven't seen before
- **Retry mistakes**: re-practise only the questions you got wrong
- **Multi-answer questions**: the app tells you how many to pick
- **Progress is saved**, so a refresh or accidental close puts you back on the same question
- **Week picker**: practise one week, a few weeks, or everything
- **Light and dark mode**, following your device setting
- **Keyboard shortcuts**: `1`–`4` to choose, `Enter` for next, `←` / `→` to move between questions
- Works on phones, tablets and desktop

## Run it locally

Open `index.html` in any modern browser. That's it.

To serve it instead:

```bash
npx serve .
# or
python -m http.server 8000
```

## Deploy

The repo is ready for static hosting as-is.

- **Vercel**: import the repo, keep the framework preset as **Other**, and deploy. Every push to `main` redeploys automatically.
- **GitHub Pages**: Settings → Pages → deploy from the `main` branch, root folder.
- **Netlify**: drag the folder into the Netlify dashboard, or connect the repo.

## Editing questions

Questions live near the top of the `<script>` block in `index.html`:

- `ORIGINAL` holds the 130 course questions
- `EXTRA` holds the 100 additional questions

Each question is one line:

```js
[week, "Question text", ["Option A", "Option B", "Option C", "Option D"], [correctIndex]]
```

Indexes start at 0. For questions with more than one correct answer, list every correct index:

```js
[4, "Which strategies increase awareness?", ["A", "B", "C", "D"], [0, 2, 3]]
```

Add, remove or fix a line, save, and refresh. Week chips and question counts update on their own.

## Note on the extra questions

The 100 extra questions are practice material written around the weekly topics: Lean Startup, TRL levels, patents and IPR, design thinking, Synectics, Business Model Canvas, Lean Canvas, funding and incubation, beachhead markets, and more. They are not official NPTEL questions. If an answer looks wrong, check it against the lecture material.

## License

Free to use for personal study.
