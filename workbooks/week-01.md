# Week 1

You are Kazibwe Joseph. Your mentor is Collin Rollingston.

This week you write the logic for four tools: a temperature converter, a quote generator, a stopwatch, and a todo list.

Work up to 6 hours each day. Stop when that day's **Done when** line is true. If 6 hours pass first, commit, push, and message your mentor with the command and the full output.

Read this file from the copy your mentor sent you. After you clone the repository, open `workbooks/week-01.md` in VS Code and continue from there.

## Every day

Answer these questions in `journey/week-01.md` under today's heading. Write in your own words.

1. Paste each command you ran and the full output.
2. For each tool you touched, write the input and the result you expected before you changed the code.
3. Write two or three sentences about what changed today.
4. Paste one error you hit. Write what you think it means.
5. Stop when today's Done when line is true.

AI rule: you may ask an AI what an error message means. Type every line of code yourself. Do not paste code from an AI into a file.

If a step fails, paste the full message into the journey, read it, and try the step again. If you are still stuck after 30 minutes, message your mentor with the command and the full output. Then stop that step.

Run every command in this workbook in **Windows PowerShell**. Edit every file in **VS Code**. Save every file before you run a command (`Ctrl+S`).

Stay in the project folder for every `git` and `node` command after Monday's clone. The project folder is `C:\dev\training`.

Start of Tuesday, Wednesday, Thursday, and Friday:

```powershell
cd C:\dev\training
git checkout main
git pull
```

If `git pull` says your branch is not `main`, run `git checkout main` and then `git pull` again.

If yesterday's pull request is still open, message your mentor and stop. Start the new day only after that pull request is merged.

End of each day:

```powershell
git status
git add .
git commit -m "PUT TODAY'S MESSAGE HERE"
git push -u origin PUT_TODAYS_BRANCH_HERE
```

Then open the repository on GitHub.

- If you see **Compare & pull request**, click it.
- If you do not, click **Pull requests**, then **New pull request**. Set base to `main` and compare to today's branch.

Title the pull request with the title in that day's steps. Click **Create pull request**. Do not click merge. Message your mentor with the pull request link.

The day's commit message and branch name are in that day's steps. Use them exactly.

## Monday — your computer

**Done when:** the journey contains the output of `git --version`, `node --version`, and `code --version`, and a pull request is open whose README shows your name.

**Branch:** `day-1-readme`

**Commit message:** `Add my name to the README`

**Pull request title:** `Day 1: add my name`

1. Open the Start menu. Type `PowerShell`. Press Enter.
2. Go to https://github.com/signup and create a GitHub account with an email you can open. Verify that email. Sign in.
3. Message your mentor your GitHub username. Stop until your mentor says you can open the repository.
4. Go to https://git-scm.com/download/win and download Git for Windows. Run the installer. Click **Next** on each screen. Leave every option as it is. Click **Install**. Click **Finish**.
5. Close PowerShell. Open it again.
6. Go to https://code.visualstudio.com/ and download the **Windows User Installer**. Run it. On the screen **Select Additional Tasks**, check **Add to PATH**. Finish the install.
7. Close PowerShell. Open it again.
8. Go to https://nodejs.org/ and download the **Windows Installer (.msi)** marked **LTS**. Run it. Leave every option as it is, including **Add to PATH**. Finish the install.
9. Close PowerShell. Open it again.
10. Run these commands, one at a time. Paste all three outputs into a note you can copy later into the journey.

```powershell
git --version
node --version
code --version
```

11. If any command says it is not recognized, close PowerShell, open it again, and run the command again. If it still fails, message your mentor and stop.
12. Run these three commands. Use your GitHub name and the email on your GitHub account.

```powershell
git config --global user.name "Kazibwe Joseph"
git config --global user.email "YOUR_GITHUB_EMAIL"
git config --global init.defaultBranch main
```

13. Run `mkdir C:\dev`. If PowerShell says the folder already exists, continue.
14. Run `cd C:\dev`.
15. On GitHub, open the repository your mentor named. Click the green **Code** button. Click **HTTPS**. Copy the URL.
16. Run the clone command with your URL pasted in place of the sample URL:

```powershell
git clone https://github.com/YOUR_MENTOR/YOUR_REPO.git training
cd training
```

17. If a sign-in window opens, sign in to GitHub, then return to PowerShell.
18. If `git clone` says permission denied, message your mentor and stop.
19. Run `pwd`. The path must end with `\training`. Paste it into your note.
20. Run:

```powershell
git checkout -b day-1-readme
code .
```

21. In VS Code, open `README.md`. Delete anything already in it. Type these lines. Save.

```markdown
# Training

Kazibwe Joseph
Week 1
```

22. In VS Code, create a folder named `journey`. Inside it, create `week-01.md`. Type the lines below. Paste the three version outputs and the `pwd` output under Monday. Save.

```markdown
# Week 1 journey

Kazibwe Joseph

## Monday

```

23. Run the end-of-day git steps. Use branch `day-1-readme` and commit message `Add my name to the README`.
24. Open the pull request. Title it `Day 1: add my name`.
25. Answer the five journey questions under `## Monday`. Save. If the journey changed after the commit, run the end-of-day git steps again with the same branch. If the branch is already pushed, use:

```powershell
git add .
git commit -m "Add my name to the README"
git push
```

## Tuesday — first tests

**Done when:** in `C:\dev\training`, `node --test` prints `pass 5` and `fail 0`, and a pull request is open.

**Branch:** `day-2-first-tests`

**Commit message:** `Add first tests for all four tools`

**Pull request title:** `Day 2: first tests`

1. Run the start-of-day git steps.
2. Run:

```powershell
git checkout -b day-2-first-tests
```

3. In the journey, add `## Tuesday`. Write one quote of at least 8 words. Set the author to `Kazibwe Joseph`. If you cannot think of a quote, use `I am learning to build a real product.`
4. In the project folder, create `convert.test.js`. Type this file. Save.

```js
const test = require("node:test");
const assert = require("node:assert/strict");
const { cToF, fToC } = require("./convert");

test("0 C is 32 F", () => {
  assert.equal(cToF(0), 32);
});

test("32 F is 0 C", () => {
  assert.equal(fToC(32), 0);
});
```

5. Run `node --test`. Paste the full output under Tuesday.
6. Create `convert.js`. Type this file. Save.

```js
function cToF(c) {}

function fToC(f) {}

module.exports = { cToF, fToC };
```

7. Run `node --test`. Paste the full output under Tuesday.
8. Change `cToF` so it returns `c * 9 / 5 + 32`.
9. Change `fToC` so it returns `(f - 32) * 5 / 9`.
10. Run `node --test`. Repeat step 8 and step 9 until both convert tests pass. Paste the passing output.
11. Create `quote.test.js`. Type this file. Replace both `PUT YOUR QUOTE HERE` strings with the quote from your journey. The two strings must match. Save.

```js
const test = require("node:test");
const assert = require("node:assert/strict");
const { nextQuote } = require("./quote");

test("index 0 returns the first quote", () => {
  const quotes = [
    { text: "PUT YOUR QUOTE HERE", author: "Kazibwe Joseph" },
  ];
  const result = nextQuote(quotes, 0);
  assert.equal(result.text, "PUT YOUR QUOTE HERE");
  assert.equal(result.author, "Kazibwe Joseph");
});
```

12. Run `node --test`. Paste the full output.
13. Create `quote.js`. Type this file. Save.

```js
function nextQuote(quotes, index) {}

module.exports = { nextQuote };
```

14. Run `node --test`. Paste the full output.
15. Change `nextQuote` so it returns the item in `quotes` at `index`. Return the whole item. Do not return only the text.
16. Run `node --test`. Change `nextQuote` until the quote test passes. Paste the passing output.
17. Create `stopwatch.test.js`. Type this file. Save.

```js
const test = require("node:test");
const assert = require("node:assert/strict");
const { elapsedSeconds } = require("./stopwatch");

test("3 seconds pass", () => {
  assert.equal(elapsedSeconds(1000, 4000), 3);
});
```

18. Run `node --test`. Paste the full output.
19. Create `stopwatch.js`. Type this file. Save.

```js
function elapsedSeconds(start, now) {}

module.exports = { elapsedSeconds };
```

20. Run `node --test`. Paste the full output.
21. Change `elapsedSeconds` so it returns `(now - start) / 1000`.
22. Run `node --test`. Change `elapsedSeconds` until the stopwatch test passes. Paste the passing output.
23. Create `todo.test.js`. Type this file. Save.

```js
const test = require("node:test");
const assert = require("node:assert/strict");
const { addTodo } = require("./todo");

test("add buy milk", () => {
  assert.deepEqual(addTodo([], "buy milk"), [
    { text: "buy milk", done: false },
  ]);
});
```

24. Run `node --test`. Paste the full output.
25. Create `todo.js`. Type this file. Save.

```js
function addTodo(items, text) {}

module.exports = { addTodo };
```

26. Run `node --test`. Paste the full output.
27. Change `addTodo` so it returns an array with one object. Set `text` to the text you were given. Set `done` to `false`.
28. Run `node --test`. Change `addTodo` until the todo test passes and the summary says `pass 5` and `fail 0`. Paste that output.
29. Answer the five journey questions under `## Tuesday`.
30. Run the end-of-day git steps. Open the pull request titled `Day 2: first tests`.

## Wednesday — more tests

**Done when:** `node --test` prints `pass 10` and `fail 0`, and a pull request is open.

**Branch:** `day-3-more-tests`

**Commit message:** `Add more tests for all four tools`

**Pull request title:** `Day 3: more tests`

1. Run the start-of-day git steps.
2. Run:

```powershell
git checkout -b day-3-more-tests
```

3. Add `## Wednesday` to the journey. Write two new quotes of at least 8 words each. Author for both: `Kazibwe Joseph`.
4. Open `convert.test.js`. Add these tests under the tests already there. Save.

```js
test("100 C is 212 F", () => {
  assert.equal(cToF(100), 212);
});

test("212 F is 100 C", () => {
  assert.equal(fToC(212), 100);
});
```

5. Run `node --test`. Paste the full output. If a convert test fails, change `cToF` or `fToC` until it passes.
6. Open `quote.test.js`. Add this test. Put your three quotes in the array, in the same order as the journey. The last `assert.equal` must use the text of quote number 3. Save.

```js
test("last index returns the last quote", () => {
  const quotes = [
    { text: "QUOTE 1", author: "Kazibwe Joseph" },
    { text: "QUOTE 2", author: "Kazibwe Joseph" },
    { text: "QUOTE 3", author: "Kazibwe Joseph" },
  ];
  const result = nextQuote(quotes, 2);
  assert.equal(result.text, "QUOTE 3");
  assert.equal(result.author, "Kazibwe Joseph");
});
```

7. Run `node --test`. Paste the full output. If the new quote test fails, change `nextQuote` until it passes.
8. Open `stopwatch.test.js`. Add this test. Save.

```js
test("no time passing is 0 seconds", () => {
  assert.equal(elapsedSeconds(2500, 2500), 0);
});
```

9. Run `node --test`. Paste the full output. If the new stopwatch test fails, change `elapsedSeconds` until it passes.
10. Open `todo.test.js`. Add this test. Save.

```js
test("keeps old items and adds the new one", () => {
  const items = [{ text: "buy milk", done: false }];
  const result = addTodo(items, "walk");
  assert.deepEqual(result, [
    { text: "buy milk", done: false },
    { text: "walk", done: false },
  ]);
  assert.equal(items.length, 1);
});
```

11. Run `node --test`. Paste the full output. This new todo test fails with Tuesday's `addTodo`.
12. Change `addTodo` with these steps:
    - Create a new array.
    - Copy the old items into it with `items.slice()`.
    - Add one object to that new array. Set `text` to the text you were given. Set `done` to `false`.
    - Return the new array.
    - Do not add the object onto the array that was passed in.
13. Run `node --test`. Change `addTodo` until the summary says `pass 10` and `fail 0`. Paste that output.
14. Answer the five journey questions under `## Wednesday`.
15. Run the end-of-day git steps. Open the pull request titled `Day 3: more tests`.

## Thursday — show each result

**Done when:** `node --test` still prints `pass 10` and `fail 0`, each show command prints the lines listed below, and a pull request is open.

**Branch:** `day-4-show-results`

**Commit message:** `Show each tool result from the command line`

**Pull request title:** `Day 4: show results`

1. Run the start-of-day git steps.
2. Run:

```powershell
git checkout -b day-4-show-results
```

3. Add `## Thursday` to the journey.
4. Create `show-convert.js`. Type this file. Save.

```js
const { cToF, fToC } = require("./convert");

console.log(cToF(0));
console.log(fToC(32));
```

5. Run `node show-convert.js`. The output must be:

```text
32
0
```

Paste the output. If it differs, change `show-convert.js` or the convert functions, then run `node --test` and `node show-convert.js` again.

6. Create `show-quote.js`. Replace the three quote strings with your three quotes from `quote.test.js`, in the same order. Save.

```js
const { nextQuote } = require("./quote");

const quotes = [
  { text: "QUOTE 1", author: "Kazibwe Joseph" },
  { text: "QUOTE 2", author: "Kazibwe Joseph" },
  { text: "QUOTE 3", author: "Kazibwe Joseph" },
];
const first = nextQuote(quotes, 0);
console.log(first.text);
console.log(first.author);
```

7. Run `node show-quote.js`. Line 1 must be your first quote. Line 2 must be `Kazibwe Joseph`. Paste the output.
8. Create `show-stopwatch.js`. Type this file. Save.

```js
const { elapsedSeconds } = require("./stopwatch");

console.log(elapsedSeconds(1000, 4000));
```

9. Run `node show-stopwatch.js`. The output must be:

```text
3
```

Paste the output.

10. Create `show-todo.js`. Type this file. Save.

```js
const { addTodo } = require("./todo");

const items = addTodo([], "buy milk");
console.log(items[0].text);
```

11. Run `node show-todo.js`. The output must be:

```text
buy milk
```

Paste the output.

12. Run `node --test`. The summary must still say `pass 10` and `fail 0`. Paste the output.
13. Answer the five journey questions under `## Thursday`.
14. Run the end-of-day git steps. Open the pull request titled `Day 4: show results`.

## Friday — bad input

**Done when:** `node --test` prints `pass 15` and `fail 0`, the journey has a `## Friday memory` section written with the AI closed, and a pull request is open.

**Branch:** `day-5-bad-input`

**Commit message:** `Reject bad input in all four tools`

**Pull request title:** `Day 5: bad input`

1. Run the start-of-day git steps.
2. Run:

```powershell
git checkout -b day-5-bad-input
```

3. Add `## Friday` to the journey.
4. Open `convert.test.js`. Add these tests. Save.

```js
test("words are invalid for C", () => {
  assert.equal(cToF("hot"), "invalid");
});

test("words are invalid for F", () => {
  assert.equal(fToC("cold"), "invalid");
});
```

5. Run `node --test`. Paste the full output.
6. Change `cToF` to this shape. Keep the return line you already wrote.

```js
function cToF(c) {
  if (typeof c !== "number") {
    return "invalid";
  }
  return c * 9 / 5 + 32;
}
```

7. Change `fToC` so it follows the same rule for `f`: if its type is not `"number"`, return `"invalid"`. Keep the return line you already wrote.
8. Run `node --test`. Change the two functions until both new convert tests pass. Paste the output.
9. Open `quote.test.js`. Add this test. Save.

```js
test("a missing index returns null", () => {
  const quotes = [
    { text: "I am learning to build a real product.", author: "Kazibwe Joseph" },
  ];
  assert.equal(nextQuote(quotes, 99), null);
  assert.equal(nextQuote(quotes, -1), null);
});
```

10. Run `node --test`. Paste the full output.
11. Change `nextQuote`. If `index < 0`, return `null`. If `index >= quotes.length`, return `null`. Otherwise return the item at `index`.
12. Run `node --test`. Change `nextQuote` until the new quote test passes. Paste the output.
13. Open `stopwatch.test.js`. Add this test. Save.

```js
test("time going backwards is invalid", () => {
  assert.equal(elapsedSeconds(5000, 1000), "invalid");
});
```

14. Run `node --test`. Paste the full output.
15. Change `elapsedSeconds`. If `now < start`, return `"invalid"`. Otherwise return `(now - start) / 1000`.
16. Run `node --test`. Change `elapsedSeconds` until the new stopwatch test passes. Paste the output.
17. Open `todo.test.js`. Add this test. Save.

```js
test("blank text does not add an item", () => {
  assert.deepEqual(addTodo([], ""), []);
  assert.deepEqual(addTodo([], "   "), []);
  const items = [{ text: "buy milk", done: false }];
  assert.deepEqual(addTodo(items, " "), [
    { text: "buy milk", done: false },
  ]);
  assert.equal(items.length, 1);
});
```

18. Run `node --test`. Paste the full output.
19. Change `addTodo`:
    - If `typeof text` is not `"string"`, copy `items` with `items.slice()` and return that copy.
    - If `text.trim()` equals `""`, copy `items` with `items.slice()` and return that copy.
    - Otherwise keep Wednesday's behavior: copy the items, add the new object, return the new array.
20. Run `node --test`. Change `addTodo` until the summary says `pass 15` and `fail 0`. Paste that output.
21. Run these commands again. Paste each output. Each one must still match Thursday.

```powershell
node show-convert.js
node show-quote.js
node show-stopwatch.js
node show-todo.js
```

22. Answer the five journey questions under `## Friday`.
23. Close every AI chat. Do not open a new one for the next step.
24. Add `## Friday memory` to the journey. Without looking at your code, write what you did on Monday, Tuesday, Wednesday, Thursday, and Friday. Write at least five sentences. Write what each of these files holds: `convert.js`, `quote.js`, `stopwatch.js`, `todo.js`.
25. You may look at the code again after those sentences are saved.
26. Run the end-of-day git steps. Open the pull request titled `Day 5: bad input`.
