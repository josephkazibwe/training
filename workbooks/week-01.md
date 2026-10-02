# Week 1

You are Kazibwe Joseph. Your mentor is Collin Rollingston. His GitHub login is `collin-rollingston`.

The project folder is `C:\dev\training`. Run git and node commands in Windows PowerShell from that folder. Edit files in VS Code. Save every file with `Ctrl+S` before a command.

Type every line of code yourself. Do not paste code from an AI into a file. You may ask an AI what an error message means.

Merge into `main` only through a pull request. Merge a pull request only after `collin-rollingston` has approved it and the review contains a line that starts with `Rating:`.

## Pull request

Do these steps for each row in the day's table, from top to bottom. Open every pull request in the table before you merge any of them.

1. `git checkout main`
2. `git pull`
3. `git checkout -b BRANCH`
4. Do the work named for that branch.
5. `git status`
6. `git add` only the files in that row.
7. `git commit -m "MESSAGE"`
8. `git push -u origin BRANCH`
9. On GitHub, open `josephkazibwe/training`. Click **Pull requests**. Click **New pull request**. Set base to `main`. Set compare to `BRANCH`. Set the title to `TITLE`. Click **Create pull request**.

When every pull request in the table is open, merge each one whose review is approved and contains `Rating:`. Click **Merge pull request**. Click **Confirm merge**.

Then run:

```powershell
git checkout main
git pull
```

Each journal is its own file. Monday uses `journals/monday.md`. Tuesday uses `journals/tuesday.md`. Wednesday uses `journals/wednesday.md`. Thursday uses `journals/thursday.md`. Friday uses `journals/friday.md`.

Every journal file has these headings:

```markdown
# DAY

## Commands

## Results

## Change

## Error
```

Under **Error**, paste one error, or write `No error.` Under **Change**, write two sentences.

## Monday

### Instructions

1. Open Windows PowerShell.
2. Download the Windows Installer (`.msi`) marked **LTS** from https://nodejs.org/ . Run it. Accept every default. Close PowerShell. Open PowerShell.
3. Run these commands. Use the email on your GitHub account.

```powershell
git config --global user.name "Kazibwe Joseph"
git config --global user.email "YOUR_GITHUB_EMAIL"
git config --global init.defaultBranch main
node --version
```

4. Run these commands.

```powershell
New-Item -ItemType Directory -Force C:\dev
cd C:\dev
git clone https://github.com/josephkazibwe/training.git
cd training
```

5. In VS Code, choose **File**, **Open Folder**, and open `C:\dev\training`.
6. On GitHub, open `josephkazibwe/training`. Click **Settings**. Click **General**. Under **Danger zone**, click **Change repository visibility**. Choose **Public**. Confirm.
7. Click **Settings**. Click **Collaborators**. Click **Add people**. Enter `collin-rollingston`. Choose role **Write**. Send the invite. Stop until `collin-rollingston` is listed as a collaborator.
8. Click **Settings**. In the left sidebar click **Rules**, then **Rulesets**. Click **New ruleset**. Click **New branch ruleset**.
9. Set **Ruleset name** to `main`. Set **Enforcement status** to **Active**. Leave **Bypass list** empty.
10. Under **Target branches**, click **Add target**. Click **Include default branch**.
11. Check **Restrict deletions**. Check **Block force pushes**. Check **Require a pull request before merging**.
12. Set **Required approvals** to `1`. Check **Dismiss stale pull request approvals when new commits are pushed**. Check **Require approval from someone other than the last pusher**. Leave **Require review from Code Owners** unchecked. Click **Create**.
13. Use the pull request steps for this table.

| Branch | Message | Title | Files | Work |
| --- | --- | --- | --- | --- |
| `monday-journal` | `Add the Monday journal` | `Monday journal` | `journals/monday.md` | Paste the full `node --version` output under **Commands**. Under **Results**, write `No tool code.` |
| `monday-codeowners` | `Add code owners` | `Add code owners` | `.github/CODEOWNERS` | One line: `* @collin-rollingston` |

14. After both are merged, open the `main` ruleset. Check **Require review from Code Owners**. Save the ruleset.
15. Run `git checkout main` and `git pull`.

### Deliveries

- `node --version` is in `journals/monday.md`.
- The repository is public.
- `collin-rollingston` has the Write role.
- Ruleset `main` is Active, targets the default branch, has an empty bypass list, requires 1 approval, and requires a code owner review.
- Both Monday pull requests are merged by you after approval and a `Rating:` line.

### Journal

`journals/monday.md`

## Tuesday

### Instructions

1. Run `git checkout main` and `git pull`.
2. Write a quote of at least 8 words in `journals/tuesday.md` under **Results**. Author: `Kazibwe Joseph`. Keep this file uncommitted until the journal branch.
3. Use the pull request steps. On each code branch, run `node --test` before `git add`, and paste that output into the journal file. Do not `git add` the journal on a code branch.

| Branch | Message | Title | Files | Work |
| --- | --- | --- | --- | --- |
| `tuesday-convert` | `Add the converter tests` | `Converter tests` | `convert.js`, `convert.test.js` | Tests: `cToF(0)` is `32`, `fToC(32)` is `0`. Run `node --test` while `convert.js` is missing. Add empty functions and run `node --test` again. Then `cToF` returns `c * 9 / 5 + 32`. `fToC` returns `(f - 32) * 5 / 9`. |
| `tuesday-quote` | `Add the quote tests` | `Quote tests` | `quote.js`, `quote.test.js` | Test: `nextQuote` at index `0` returns your quote text and author `Kazibwe Joseph`. Run `node --test` before `quote.js` exists. Add empty `nextQuote`. Then return the item at `index`. |
| `tuesday-stopwatch` | `Add the stopwatch tests` | `Stopwatch tests` | `stopwatch.js`, `stopwatch.test.js` | Test: `elapsedSeconds(1000, 4000)` is `3`. Run `node --test` before `stopwatch.js` exists. Add empty `elapsedSeconds`. Then return `(now - start) / 1000`. |
| `tuesday-todo` | `Add the todo tests` | `Todo tests` | `todo.js`, `todo.test.js` | Test: `addTodo([], "buy milk")` deep-equals `[{ text: "buy milk", done: false }]`. Run `node --test` before `todo.js` exists. Add empty `addTodo`. Then return that one object in an array. `done` is `false`. |
| `tuesday-journal` | `Add the Tuesday journal` | `Tuesday journal` | `journals/tuesday.md` | Fill **Commands**, **Change**, and **Error**. **Commands** contains a failing `node --test` output for each tool and the final passing output. |

Use `node:test` and `node:assert/strict` in every test file. Export each function with `module.exports`.

Before you commit each code branch, `node --test` on that branch must pass. After all five pull requests are merged, `node --test` on `main` must print `pass 5` and `fail 0`.

### Deliveries

- Five merged pull requests.
- On `main`, `node --test` prints `pass 5` and `fail 0`.
- `journals/tuesday.md` contains a failing test output for each tool.

### Journal

`journals/tuesday.md`

## Wednesday

### Instructions

1. Run `git checkout main` and `git pull`.
2. Write two new quotes of at least 8 words in `journals/wednesday.md` under **Results**. Author for both: `Kazibwe Joseph`.
3. Use the pull request steps.

| Branch | Message | Title | Files | Work |
| --- | --- | --- | --- | --- |
| `wednesday-convert-stopwatch` | `Test more converter and stopwatch cases` | `Converter and stopwatch cases` | `convert.test.js`, `convert.js`, `stopwatch.test.js`, `stopwatch.js` | Add tests: `cToF(100)` is `212`, `fToC(212)` is `100`, `elapsedSeconds(2500, 2500)` is `0`. The stopwatch test name is `no time passing is 0 seconds`. Run `node --test`. Change the functions until those tests pass. |
| `wednesday-quote-todo` | `Test more quote and todo cases` | `Quote and todo cases` | `quote.test.js`, `quote.js`, `todo.test.js`, `todo.js` | Add a quote test named `last index returns the last quote` for `nextQuote(quotes, 2)` and your third quote. Add the todo test below. Run `node --test`. Copy old items with `items.slice()`, add the new object to the copy, and return the copy. |
| `wednesday-journal` | `Add the Wednesday journal` | `Wednesday journal` | `journals/wednesday.md` | Paste the failing todo output and the final `node --test` output under **Commands**. |

Todo test:

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

Before you commit `wednesday-quote-todo`, the new quote test and the new todo test must pass. After all three pull requests are merged, `node --test` on `main` must print `pass 10` and `fail 0`.

### Deliveries

- Three merged pull requests.
- On `main`, `node --test` prints `pass 10` and `fail 0`.

### Journal

`journals/wednesday.md`

## Thursday

### Instructions

1. Run `git checkout main` and `git pull`.
2. Use the pull request steps.

| Branch | Message | Title | Files | Work |
| --- | --- | --- | --- | --- |
| `thursday-show-convert-stopwatch` | `Show converter and stopwatch results` | `Show converter and stopwatch` | `show-convert.js`, `show-stopwatch.js` | `node show-convert.js` prints `32` then `0`. `node show-stopwatch.js` prints `3`. |
| `thursday-show-quote-todo` | `Show quote and todo results` | `Show quote and todo` | `show-quote.js`, `show-todo.js` | `node show-quote.js` prints your first quote, then `Kazibwe Joseph`. `node show-todo.js` prints `buy milk`. |
| `thursday-journal` | `Add the Thursday journal` | `Thursday journal` | `journals/thursday.md` | Paste all four show outputs under **Commands**. |

`show-convert.js`:

```js
const { cToF, fToC } = require("./convert");

console.log(cToF(0));
console.log(fToC(32));
```

`show-stopwatch.js`:

```js
const { elapsedSeconds } = require("./stopwatch");

console.log(elapsedSeconds(1000, 4000));
```

`show-quote.js` calls `nextQuote` with your three quotes at index `0`, prints `text`, then prints `author`.

`show-todo.js`:

```js
const { addTodo } = require("./todo");

const items = addTodo([], "buy milk");
console.log(items[0].text);
```

On `thursday-journal`, before you commit, `node --test` must still print `pass 10` and `fail 0`. Do not add test files to that pull request.

### Deliveries

- Three merged pull requests.
- The four show commands print the required lines.
- `node --test` prints `pass 10` and `fail 0`.

### Journal

`journals/thursday.md`

## Friday

### Instructions

1. Run `git checkout main` and `git pull`.
2. Use the pull request steps.

| Branch | Message | Title | Files | Work |
| --- | --- | --- | --- | --- |
| `friday-convert-stopwatch` | `Reject bad converter and stopwatch input` | `Bad converter and stopwatch input` | `convert.js`, `convert.test.js`, `stopwatch.js`, `stopwatch.test.js` | Add the convert tests and the stopwatch test below. `cToF` and `fToC` return `"invalid"` when the type is not `"number"`. `elapsedSeconds` returns `"invalid"` when `now < start`. |
| `friday-quote-todo` | `Reject bad quote and todo input` | `Bad quote and todo input` | `quote.js`, `quote.test.js`, `todo.js`, `todo.test.js` | Add the quote test and the todo test below. Use your first quote in place of `QUOTE`. `nextQuote` returns `null` when `index < 0` or `index >= quotes.length`. `addTodo` returns `items.slice()` when `text` is not a string or `text.trim()` equals `""`. |
| `friday-journal` | `Add the Friday journal` | `Friday journal` | `journals/friday.md` | Close every AI chat. Under **Change**, write at least five sentences from memory about Monday through Friday and what the four tool files hold. Do not open those files while you write **Change**. Paste the final `node --test` output under **Commands**. |

Convert tests:

```js
test("words are invalid for C", () => {
  assert.equal(cToF("hot"), "invalid");
});

test("words are invalid for F", () => {
  assert.equal(fToC("cold"), "invalid");
});
```

`cToF` shape:

```js
function cToF(c) {
  if (typeof c !== "number") {
    return "invalid";
  }
  return c * 9 / 5 + 32;
}
```

Stopwatch test:

```js
test("time going backwards is invalid", () => {
  assert.equal(elapsedSeconds(5000, 1000), "invalid");
});
```

Quote test:

```js
test("a missing index returns null", () => {
  const quotes = [
    { text: "QUOTE", author: "Kazibwe Joseph" },
  ];
  assert.equal(nextQuote(quotes, 99), null);
  assert.equal(nextQuote(quotes, -1), null);
});
```

Todo test:

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

Before you commit `friday-quote-todo`, the new quote test and the new todo test must pass. After all three pull requests are merged, on `main`, `node --test` must print `pass 15` and `fail 0`. Run the four show commands on `main`. Each output must match Thursday.

### Deliveries

- Three merged pull requests.
- On `main`, `node --test` prints `pass 15` and `fail 0`.
- The four show commands still match Thursday.
- `journals/friday.md` has the five memory sentences.

### Journal

`journals/friday.md`
