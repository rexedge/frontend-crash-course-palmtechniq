# Class 6: JavaScript Basics
### A self-guided read-through — read each section, then do the practice before moving on. You don't need any of your earlier pages this time: just VS Code, a browser, and a new empty folder.

---

## 1. Recap: Where We Are

You can now build a real page: semantic HTML for the structure, CSS for the look, Flexbox and Grid for the layout, and media queries so it works on a phone.

But your pages don't *do* anything yet. Submit your contact form and it just reloads. There's no button that switches to dark mode, no counter, no "thank you" message. A page made of HTML and CSS is like a printed poster: nice to look at, but it can't react.

**JavaScript** is the third layer — the one that makes a page *behave*. Remember the house from Class 1: HTML is the frame, CSS is the paint and furniture, and JavaScript is the electricity and plumbing.

This class is different from the last five in one big way: **you won't change the page at all.** You'll learn the language itself — values, decisions, loops, functions — and see the results as text in the browser's **Console**. In Class 7 you'll connect that logic to your pages. Learning it in this order means that when you get there, only one thing is new at a time.

A word of encouragement before you start. For a lot of people this is the class where it starts to feel like "real programming" — and it's also where people get stuck the most. That's normal. Go slowly, type everything, and expect red error messages. In this class they're your friends.

---

## 2. What JavaScript Does

A JavaScript file is a **list of instructions**. The browser reads it from top to bottom and carries out each instruction in order, one at a time. That's all a program is.

On a real page, those instructions do four kinds of job:

- **React** to the user — a click, typing in a field, submitting a form.
- **Decide** — "is the password long enough?", "is the cart empty?"
- **Calculate** — a total, a score, the days left until a date.
- **Change the page** — show a message, hide a menu, add an item to a list.

The first and the last are Class 7. This class is the middle two: deciding and calculating. They're the "thinking" part, and every interactive page needs them.

Three quick facts, so nothing confuses you later:

- JavaScript (often written **JS**) has nothing to do with the language called Java. The similar name is a historical accident.
- JS is **case-sensitive** and fussy about spelling. `console.log` works. `Console.log` and `console.Log` don't.
- HTML and CSS forgive mistakes: the browser skips what it doesn't understand and carries on. JS doesn't. One mistake can stop the whole script — but JS also tells you exactly where the mistake is.

---

## 3. Your First JavaScript: the Console

Every browser has a place where you can type JavaScript and run it straight away: the **Console**.

1. Open any page in Chrome or Edge. A blank tab is fine.
2. Open dev tools: press **`F12`**, or right-click the page → **Inspect**.
3. Click the **Console** tab. (A shortcut that goes straight there: `Ctrl+Shift+J`, Mac `Cmd+Option+J`.)

You'll see a `>` prompt. Type this and press Enter:

```js
2 + 2
```

The Console answers `4`. Try a few more: `10 * 5`, `100 / 8`, `"hello"`.

Now the most-used instruction in this whole class:

```js
console.log("Hello from JavaScript!");
```

`console.log(...)` means "print this in the Console". You'll use it constantly — to show results, and to check what your code is doing.

> After a `console.log(...)`, the Console also prints a grey `undefined` on the next line. Ignore it. It's the Console saying "that instruction didn't hand anything back". You only see it when you type straight into the Console.

The Console is great for quick experiments. But it forgets everything when you reload the page, so real code goes in a file. That's next.

### Practice Now
Open the Console and try each of these: `7 * 6`, `"Ada" + " " + "Lovelace"`, `console.log("my first log")`, and `console.log(7 * 6)`. Then press the **up arrow** key — the Console brings back your last line so you can change it and run it again.

---

## 4. Connecting a Script to a Page

CSS lives in a `.css` file, connected with `<link>`. JavaScript lives in a `.js` file, connected with a `<script>` tag.

Make a new folder called `js-practice/` and create two files in it.

**`index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>JS Practice</title>
</head>
<body>
    <h1>JS Practice</h1>
    <p>Nothing to see on the page. Open the Console.</p>

    <script src="app.js"></script>
</body>
</html>
```

**`app.js`**

```js
console.log("app.js is connected!");
console.log(2 + 2);
```

Open `index.html` with Live Server, then open the Console. You should see two lines. On the right of each one is `app.js:1` or `app.js:2` — the file and the line number it came from.

Things to notice:

- `<script>` always needs its closing `</script>`, even though there's nothing between the two tags.
- It goes at the **end of `<body>`**, just before `</body>`. That doesn't matter yet, but it will in Class 7. Build the habit now.
- `src` is a path to a file, just like `src` on an `<img>`.
- The page itself doesn't change. All the action is in the Console — keep it open for this whole class.
- Every time you save, Live Server reloads the page, and the whole script runs again from the top.
- Start each new section with an empty `app.js`. Lines left over from an earlier experiment can clash with the new ones.

### The small rules of the language

```js
// This is a comment. The browser ignores it. Leave notes for yourself.

/* This is a comment
   that covers several lines. */

console.log("Statements end with a semicolon");
```

- A **statement** is one instruction. End each one with a **semicolon** `;`. (JS can often guess where a statement ends without one. "Often" isn't "always" — just write them.)
- Text goes inside quotes: `"like this"`. Without quotes, JS thinks the word is the *name* of something.
- Brackets and quotes come in pairs. Every `(`, `{`, `[` and `"` needs its partner.

### Your first error — on purpose
Add this as line 3 of `app.js`, and save:

```js
console.log(helo);
```

The Console shows a red message:

```
Uncaught ReferenceError: helo is not defined
    at app.js:3:13
```

Read it properly. It tells you three things:

- **What kind of problem:** `ReferenceError` — you used a name JS doesn't know.
- **The detail:** `helo is not defined` — there were no quotes, so JS went looking for something *called* `helo`.
- **Where:** `app.js:3:13` — the file, line 3, character 13. Click it, and dev tools jumps to that exact spot.

Fix it by adding the quotes: `console.log("helo");`.

One more thing to notice: when JS hits an error, it **stops**. Any lines after the broken one don't run. So always fix the **first** red message first — the others often disappear with it.

A red message isn't a telling-off. It's the browser pointing at the exact line. The people who get good at JavaScript are the people who read the red text.

### Practice Now
Set up the two files and get both lines logging. Then make these three mistakes on purpose, **one at a time**. Read each message before you fix it:

1. Delete the closing `)` from a `console.log` line. (Look at how much of the file still runs.)
2. Write `console.Log("hi");` with a capital **L**.
3. In `index.html`, change `src="app.js"` to `src="apps.js"`.

✅ **Checkpoint:** Your `.js` file is connected, you can see its output in the Console, and you've read three red messages without panicking.

---

## 5. Variables: `let` and `const`

A **variable** is a named box that holds a value, so you can use it again later.

```js
const firstName = "Ada";
let score = 0;

console.log(firstName);   // Ada
console.log(score);       // 0
```

Read `const firstName = "Ada";` as "make a box called `firstName` and put `"Ada"` in it". The `=` sign doesn't mean "equals", as it does in maths. It means "**put the value on the right into the box on the left**".

There are two keywords for making a box:

- **`let`** — the value **can** be changed later.
- **`const`** — short for *constant*. The value **can't** be replaced.

```js
let score = 0;
score = 10;           // fine — no `let` this time, the box already exists
score = score + 5;    // take what's in the box, add 5, put the answer back → 15

const firstName = "Ada";
firstName = "Grace";  // ❌ TypeError: Assignment to constant variable.
```

Which one should you use? **Start with `const`. Switch to `let` only when the value has to change** — a counter, a running total. Then whenever you see `let` in your code, it's a signal: "watch this one, it changes".

You write `let` or `const` **once**, when you make the box. After that, use the name on its own:

```js
let total = 100;
let total = 200;   // ❌ SyntaxError: Identifier 'total' has already been declared
total = 200;       // ✅ no `let` — you're reusing the box
```

> You'll see `var` in older tutorials. It's the old way to make a variable, and it behaves in some confusing ways. Don't use it.

### Naming rules
- Letters, digits, `_` and `$` only. No spaces, no hyphens. A name can't start with a digit.
- Names are case-sensitive: `score` and `Score` are two different boxes.
- For names made of several words, use **camelCase**: `firstName`, `totalPrice`, `isLoggedIn`. (CSS classes use hyphens, like `first-name`. JS names can't — a `-` means minus.)
- Choose names that say what's inside. `price` beats `p`. `daysLeft` beats `x`.

### Practice Now
Empty your `app.js`. Make a `const` for your first name, a `const` for the year you were born, and a `let` for the cups of water you've drunk today, starting at `0`. Log all three. Then add 1 to the cups, twice, and log it again. Finally, try to change your birth year, and read the error.

---

## 6. Data Types

Every value has a **type**. You need five to begin with:

| Type | What it is | Examples |
|---|---|---|
| **string** | text, always inside quotes | `"Lagos"`, `"hello there"`, `"42"`, `""` |
| **number** | any number: whole or decimal, positive or negative | `42`, `3.14`, `-7`, `0` |
| **boolean** | a yes/no answer — there are only two | `true`, `false` |
| **undefined** | "nothing has been put here yet" | a `let` you made but never filled |
| **null** | "empty, on purpose" | you write it yourself: `let winner = null;` |

A few things to notice:

- **Quotes make a string.** `42` is a number. `"42"` is text that happens to look like a number. That difference will catch you out in Section 7.
- Double quotes and single quotes both work: `"hi"` and `'hi'` are the same string. This course uses double quotes.
- `true` and `false` have no quotes. `"true"` is just a string.
- `undefined` is what JS gives you by itself when something is missing. `null` is what *you* write to say "nothing here, and I mean it".

### `typeof` — ask what type a value is

```js
console.log(typeof "Lagos");     // string
console.log(typeof 42);          // number
console.log(typeof true);        // boolean

let nothingYet;
console.log(nothingYet);         // undefined
console.log(typeof nothingYet);  // undefined
```

One famous oddity: `typeof null` gives `object`, not `null`. It's a mistake from the very first version of JavaScript, and it can never be fixed because old websites depend on it. Just remember it.

### Template literals — strings with gaps to fill
To build a sentence out of variables, you can glue pieces together with `+`:

```js
const city = "Lagos";
const temperature = 31;

console.log("It is " + temperature + " degrees in " + city + ".");
```

It works, but all those quotes and plus signs are easy to get wrong. A **template literal** is cleaner. It uses **backticks** `` ` `` instead of quotes, and `${ }` wherever a value should be dropped in:

```js
console.log(`It is ${temperature} degrees in ${city}.`);
// It is 31 degrees in Lagos.
```

On most keyboards the backtick is the key at the top left, under `Esc`. It is **not** the same as a single quote `'`.

Whatever is inside `${ }` is worked out first, so you can put a sum in there: `` `Next year I'll be ${age + 1}.` ``

### Practice Now
Declare `const firstName`, `let age`, and `const isStudent` (a boolean). Log the `typeof` each one. Then log one template-literal sentence that uses all three, such as `Ada is 28. Student: true`. Finally, swap the backticks for ordinary double quotes and see what gets printed.

---

## 7. Operators: Doing Maths

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `+` | add | `17 + 5` | `22` |
| `-` | subtract | `17 - 5` | `12` |
| `*` | multiply | `17 * 5` | `85` |
| `/` | divide | `17 / 5` | `3.4` |
| `%` | the **remainder** after dividing | `17 % 5` | `2` |
| `**` | to the power of | `17 ** 2` | `289` |

`%` is the new one. `17 % 5` is `2` because 5 goes into 17 three times (that's 15), with 2 left over. It looks obscure, but it answers some very common questions:

- Is `n` even? → `n % 2` is `0`.
- Is `n` a multiple of 3? → `n % 3` is `0`.
- How many seconds are left over after taking out the whole minutes? → `seconds % 60`.

The order is the same as in school maths — the rule you may know as **BODMAS** or **PEMDAS**. Brackets first, then `**`, then `*` `/` `%`, then `+` `-`. So `2 + 3 * 4` is `14`, not `20`: the multiplying happens first.

Use brackets to change the order, or whenever you're not sure: `(2 + 3) * 4` is `20`. Extra brackets never hurt.

### Shortcuts for changing a variable

```js
let count = 10;

count = count + 5;   // the long way          → 15
count += 5;          // the same thing, shorter → 20
count -= 2;          // subtract 2            → 18
count *= 2;          // double it             → 36
count++;             // add 1                 → 37
count--;             // subtract 1            → 36
```

You'll see `count++` in almost every loop.

### The `+` trap: adding or joining?
`+` does two jobs. With two numbers, it **adds**. If **either side is a string**, it **joins**:

```js
console.log(2 + 2);       // 4
console.log("2" + 2);     // "22" — joined, not added
console.log("5" - 2);     // 3 — minus only does maths, so JS turns "5" into a number
console.log("5" * "2");   // 10
```

JS quietly changes types to make an operation work. Sometimes that's handy. Sometimes it gives you `"22"` when you wanted `4`. This matters a lot in Class 7, because **everything a user types into a form arrives as a string**.

To convert on purpose, use `Number()`:

```js
const typed = "25";

console.log(typed + 5);           // "255"
console.log(Number(typed) + 5);   // 30
```

If the text isn't a number at all, you get **`NaN`** — "Not a Number":

```js
console.log(Number("hello"));   // NaN
console.log(10 / "a");          // NaN
```

`NaN` is JS saying "that sum made no sense". When you see `NaN` in your output, look for a string or an `undefined` that has sneaked into your maths.

> `console.log` prints strings **without** their quotes, so `"22"` and `22` look almost the same in the Console (Chrome and Edge show numbers in a different colour). When you're not sure which one you have, log `typeof` it.

### Practice Now
With `const a = 17;` and `const b = 5;`, log all six operations from the table. Then predict each of these **before** you run it: `1 + "1"`, `"3" * 4`, `"10" / 2`, `"3" + 4 + 5`, `3 + 4 + "5"`. The last two are sneaky — JS works from left to right.

---

## 8. Comparisons and Logic

A **comparison** asks a question. The answer is always a boolean.

| Operator | The question | Example | Result |
|---|---|---|---|
| `===` | exactly equal? | `5 === 5` | `true` |
| `!==` | different? | `5 !== 3` | `true` |
| `>` | greater than? | `10 > 3` | `true` |
| `<` | less than? | `10 < 3` | `false` |
| `>=` | greater than or equal to? | `18 >= 18` | `true` |
| `<=` | less than or equal to? | `17 <= 16` | `false` |

### One, two, or three equals signs
- `=` **puts** a value into a variable.
- `===` **compares** two values.
- `==` (two signs) also compares, but it changes the types first, so `5 == "5"` is `true`. That hides bugs.

**Always compare with `===` and `!==`.** They say `5 === "5"` is `false` — because a number is not a string.

Comparing strings works too, and capitals matter: `"apple" === "apple"` is `true`, but `"Apple" === "apple"` is `false`.

### Combining questions: `&&`, `||`, `!`

| Operator | Name | `true` when… |
|---|---|---|
| `&&` | AND | **both** sides are true |
| `\|\|` | OR | **at least one** side is true |
| `!` | NOT | it flips the answer: `!true` is `false` |

```js
const age = 20;
const hasTicket = true;

console.log(age >= 18 && hasTicket);   // true — both are true
console.log(age < 13 || age >= 65);    // false — neither is true
console.log(!hasTicket);               // false
```

To check a **range**, you need two comparisons joined with `&&`:

```js
age >= 13 && age <= 19   // ✅ "from 13 to 19"
13 <= age <= 19          // ❌ no error — but it's true for 20 as well
```

The second line is how you'd write it in maths. JS runs it without complaining and gives the wrong answer. Always write both halves.

### Practice Now
Predict, then check in the Console: `5 == "5"`, `5 === "5"`, `0 === false`, `10 > 3 && 3 > 5`, `10 > 3 || 3 > 5`, `!(5 > 2)`. Then make a `const age` and write one expression that is `true` only for a teenager (13 to 19). Test it with 12, 13, 19, and 20.

✅ **Checkpoint:** You can say what `=`, `==`, and `===` each do, and why you'll only ever write the first and the last.

---

## 9. Functions

So far, every line runs once, from top to bottom. A **function** is a named set of instructions that you can run whenever you like, as often as you like — with different values each time.

```js
function add(a, b) {
    return a + b;
}

console.log(add(2, 3));     // 5
console.log(add(10, 20));   // 30
```

The anatomy:

- `function` — "I'm defining a function".
- `add` — its name. Same rules as variable names. A good function name is usually a verb.
- `(a, b)` — its **parameters**: boxes that get filled each time the function runs. No `let` needed.
- `{ ... }` — the **body**: the instructions to carry out.
- `return a + b;` — hand this value **back** to whoever asked.

Defining a function doesn't run it. It's a recipe sitting on the shelf. To run it, you **call** it: write its name followed by brackets, `add(2, 3)`. The values you pass in — `2` and `3` — are the **arguments**. They go into the parameters in order: `a` gets `2`, and `b` gets `3`.

A call **turns into** its return value. So `add(2, 3)` can go anywhere a number can go:

```js
const total = add(2, 3);          // total is 5
console.log(add(2, 3) * 10);      // 50
console.log(add(add(1, 2), 3));   // 6 — the inner call runs first
```

### `return` vs `console.log` — the big one
They look the same when you're testing in the Console. They're completely different:

- `console.log(x)` **shows** `x` to *you*, the person writing the code. The program can't use it.
- `return x` **gives** `x` back to the *program*, so it can be stored, added to, or passed on.

```js
function addAndLog(a, b) {
    console.log(a + b);
}

function addAndReturn(a, b) {
    return a + b;
}

const first = addAndLog(2, 3);       // logs 5 …
console.log(first);                  // … but first is undefined

const second = addAndReturn(2, 3);   // logs nothing …
console.log(second);                 // … and second is 5
```

A function with no `return` gives back `undefined`. So here's the rule for this course: **a function `return`s its answer, and you `console.log` the call to see it.**

Two more facts about `return`:

- `return` **ends** the function straight away. Lines after it, inside the function, never run.
- A function can have no parameters at all: `function sayHello() { ... }`. You still call it with brackets: `sayHello()`. The brackets are what make it run.

> Give every function in a file its own name. If two functions share a name, JS quietly keeps the **last** one and uses it for every call — with no error to warn you.

### Variables inside a function stay inside

```js
function priceWithTax(price) {
    const tax = price * 0.1;
    return price + tax;
}

console.log(priceWithTax(2000));   // 2200
console.log(tax);                  // ❌ ReferenceError: tax is not defined
```

`price` and `tax` only exist while the function is running. Outside it, they don't exist. That's a good thing: each function gets its own private workspace, so two functions can both have a `total` without getting in each other's way.

### Practice Now
Write each of these, and test each with three logged calls: `subtract(a, b)`, `multiply(a, b)`, `square(n)`, and `celsiusToFahrenheit(c)` (multiply by 9, divide by 5, add 32 — so `celsiusToFahrenheit(100)` is `212`). Then write `greet(firstName)` that **returns** a template-literal string such as `Hello, Ada!`. Remember: `return` inside, `console.log` outside.

✅ **Checkpoint:** You can explain the difference between `return` and `console.log`, and you know why a function with no `return` gives `undefined`.

---

## 10. Making Decisions: `if`, `else if`, `else`

```js
const temperature = 31;

if (temperature >= 30) {
    console.log("It's hot.");
}
```

The condition goes in the brackets, and it must work out to `true` or `false`. If it's `true`, the block inside the braces runs. If it's `false`, the block is skipped.

Add `else` for "otherwise", and `else if` for more options:

```js
function describeTemperature(degrees) {
    if (degrees >= 30) {
        return "hot";
    } else if (degrees >= 20) {
        return "warm";
    } else if (degrees >= 10) {
        return "cool";
    } else {
        return "cold";
    }
}

console.log(describeTemperature(31));   // hot
console.log(describeTemperature(22));   // warm
console.log(describeTemperature(4));    // cold
```

JS reads the ladder from the top, takes the **first** condition that's true, and skips all the rest. That's why 31 gives `hot` and not `warm`, even though `31 >= 20` is also true.

So **the order matters**. Put `degrees >= 10` first, and 31 would come out as `cool` — it passes the first test, and JS never looks any further. Put the strictest test first.

`else` has no condition. It catches everything that's left.

### Test the edges
The bugs in an `if` ladder live at the boundaries. Is 30 `hot` or `warm`? That depends on whether you wrote `>=` or `>`. Whenever you write a ladder, test each boundary and the value on either side of it: 29, 30, 31.

### Check for bad input first
Because `return` ends the function, you can deal with awkward values at the top and get them out of the way:

```js
function divide(a, b) {
    if (b === 0) {
        return "Cannot divide by zero";
    }

    return a / b;
}
```

No `else` is needed. If the function gets past the `if`, then `b` isn't zero.

### The ternary: a one-line `if` / `else`
When you're choosing between **two values**, there's a short form:

```js
condition ? valueIfTrue : valueIfFalse
```

```js
const age = 20;
const ticket = age >= 18 ? "adult" : "child";

console.log(ticket);   // adult
```

Read it as a question: "Is `age` at least 18? Then `"adult"`. Otherwise `"child"`." Use it for simple either/or choices. For three or more options, or anything that needs several lines, a normal `if` is easier to read.

### The one-equals bug
An `if` wants `true` or `false`. If you give it something else, JS converts it: `0`, `""` (an empty string), `null`, `undefined`, and `NaN` count as false. Everything else counts as true.

You don't need to use that yet. You need to know it because of this classic bug:

```js
let n = 5;

if (n = 10) {              // ❌ one = sign: this PUTS 10 into n …
    console.log("ten");    // … and 10 counts as true, so this always runs
}
```

No error, no warning. It just always runs. If an `if` seems to be "always true", count the equals signs.

> You'll see short `if`s written without braces: `if (b === 0) return 0;`. That works when there's exactly one statement. While you're learning, always write the braces.

### Practice Now
Write `describeNumber(n)` that returns `"negative"`, `"zero"`, or `"positive"`, and test it with `-5`, `0`, and `7`. Then write `canVote(age)` using a ternary, so it returns `"yes"` or `"not yet"`. Test 17, 18, and 19.

---

## 11. Loops: `for` and `while`

A **loop** runs the same block of code again and again. Computers are very good at this: they never get bored, and they never lose count.

### The `for` loop — when you know how many times

```js
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
// 1
// 2
// 3
// 4
// 5
```

The header has three parts, separated by **semicolons**:

| Part | Here | When it runs |
|---|---|---|
| **start** | `let i = 1` | once, before anything else |
| **condition** | `i <= 5` | before **every** round — when it's `false`, the loop ends |
| **step** | `i++` | after **every** round |

So: `i` starts at 1 → is `1 <= 5`? Yes → run the body → `i++` makes it 2 → is `2 <= 5`? Yes → … → `i` becomes 6 → is `6 <= 5`? No → stop.

`i` is just a variable (it's short for "index"). It's a counter, and you can use it inside the body.

Change the three parts to count in other ways:

```js
for (let i = 0; i < 5; i++) { ... }        // 0 1 2 3 4    — five rounds, starting at 0
for (let i = 2; i <= 20; i += 2) { ... }   // 2 4 6 … 20   — the even numbers
for (let i = 10; i >= 1; i--) { ... }      // 10 9 8 … 1   — a countdown
```

### The running-total pattern
Most useful loops build something up, one round at a time. Make a variable **before** the loop, change it **inside** the loop, and use it **after** the loop:

```js
function sumTo(n) {
    let total = 0;

    for (let i = 1; i <= n; i++) {
        total += i;
    }

    return total;
}

console.log(sumTo(4));     // 10 (1 + 2 + 3 + 4)
console.log(sumTo(100));   // 5050
```

Two places where this goes wrong:

- `let total = 0;` must be **above** the loop. Inside it, `total` would be reset to 0 on every round.
- `return total;` must be **below** the loop's closing brace. Inside it, the function would end on the very first round.

### Trace it by hand
When a loop confuses you, draw a table and step through it the way the browser does. For `sumTo(4)`:

| Round | `i` | `total` after the body |
|---|---|---|
| 1 | 1 | 1 |
| 2 | 2 | 3 |
| 3 | 3 | 6 |
| 4 | 4 | 10 |

It feels slow. It's also the most reliable debugging tool you'll ever have.

### The `while` loop — when you don't know how many times

```js
let savings = 1000;
let months = 0;

while (savings < 5000) {
    savings += 750;
    months++;
}

console.log(`It took ${months} months.`);   // It took 6 months.
```

`while (condition) { ... }` keeps going **as long as** the condition is true. It's a `for` loop with only the middle part: you make the starting variables yourself, above the loop, and you change them yourself, inside it.

Which one should you use?

- **`for`** — you're counting, or going through a list. You know how many rounds there will be.
- **`while`** — you're waiting for something to become true, and you can't say in advance how long that will take.

### The infinite loop
If the condition never becomes false, the loop never ends:

```js
let i = 0;

while (i < 5) {
    console.log(i);
    // no i++ here, so i is 0 forever
}
```

The tab freezes, and your computer's fan may start to spin. Don't panic. **Close the tab** (or the whole browser, if the tab won't close), fix the code, and open the page again. Before you save any `while` loop, find the line inside it that moves towards the exit.

### Practice Now
With `for`: log the numbers 1 to 20, then only the even ones, then 20 down to 1. Next, type `sumTo` from memory and trace `sumTo(5)` in a table on paper before you run it. Finally, with `while`: start a variable at 1 and keep doubling it until it passes 1000. How many doublings did it take?

---

## 12. Arrays

A variable holds one value. An **array** holds a **list** of values, in order.

```js
const cities = ["Lagos", "Abuja", "Ibadan", "Kano"];
```

Square brackets, with commas between the values. Each value has a position number, called its **index** — and **indexes start at 0**, not 1.

```
index:      0         1          2         3
         "Lagos"   "Abuja"   "Ibadan"    "Kano"
```

```js
console.log(cities[0]);                   // Lagos — the first item
console.log(cities[2]);                   // Ibadan
console.log(cities.length);               // 4 — how many items there are
console.log(cities[cities.length - 1]);   // Kano — the last item
console.log(cities[4]);                   // undefined — there is no index 4
```

Because counting starts at 0, the last index is always `length - 1`. Four items have the indexes 0, 1, 2, and 3. Asking for an index that doesn't exist isn't an error. You just get `undefined`.

### Changing an array

```js
cities.push("Enugu");          // add one to the end
cities[1] = "Benin City";      // replace the item at index 1

console.log(cities.length);    // 5
```

Wait — `cities` is a `const`, and you just changed it? Yes. `const` stops you putting a **different** array in the box (`cities = [...]` would be an error). It doesn't freeze what's inside the array. The box always holds the same list; the list itself can grow and change.

### Looping over an array
This is what `for` loops are used for most of the time. Start at index 0, and keep going while `i` is **less than** the length:

```js
for (let i = 0; i < cities.length; i++) {
    console.log(`City ${i + 1}: ${cities[i]}`);
}
// City 1: Lagos
// City 2: Benin City
// City 3: Ibadan
// City 4: Kano
// City 5: Enugu
```

Learn that header by heart: `for (let i = 0; i < cities.length; i++)`. Start at `0`. Use `<`, not `<=`.

> **The off-by-one trap, again:** `i <= cities.length` goes one round too far and logs `undefined` at the end. `i < cities.length - 1` stops one round early and misses the last item. In Class 5, grid lines started at 1. Array indexes start at 0. Sorry about that.

Put the array loop together with the running-total pattern, and you can add up a list of any length:

```js
function sumAll(numbers) {
    let total = 0;

    for (let i = 0; i < numbers.length; i++) {
        total += numbers[i];
    }

    return total;
}

console.log(sumAll([10, 20, 30]));   // 60
```

An array can hold any type of value. Keep each array to **one kind** of thing, though — all prices, or all names.

### Practice Now
Make an array of five foods you like. Log its length, the first item, and the last item (using `length - 1`). Push a sixth. Loop over it and log lines such as `1. Jollof rice`. Then type `sumAll` by hand and write `average(numbers)`, which **calls** `sumAll` and divides by the length. `average([10, 20, 30])` should be `20`.

✅ **Checkpoint:** You can write the array loop header from memory, and you know why it's `<` and not `<=`.

---

## 13. More With Strings

A string is a row of characters. It works a lot like an array of letters: it has a `.length`, and you can read one character with an index that starts at 0.

```js
const word = "JavaScript";

console.log(word.length);             // 10
console.log(word[0]);                 // J
console.log(word[word.length - 1]);   // t
```

Strings also come with built-in tools, called **methods**. You use a method by writing a dot after the string — just like `console.log`, which is a method too.

| Method | What it gives back | Example | Result |
|---|---|---|---|
| `.toUpperCase()` | the string in capitals | `"Hello".toUpperCase()` | `"HELLO"` |
| `.toLowerCase()` | the string in small letters | `"Hello".toLowerCase()` | `"hello"` |
| `.includes(text)` | `true` if that text is somewhere inside | `"JavaScript".includes("Script")` | `true` |
| `.slice(start, end)` | the part from index `start` up to — but **not including** — `end` | `"JavaScript".slice(0, 4)` | `"Java"` |

A few things to notice:

- `.length` has **no brackets**. It's a fact about the string. The methods **need** their brackets, because they do some work. `word.toUpperCase` without brackets doesn't run it.
- A method gives back a **new** string. It never changes the original:
  ```js
  const shout = word.toUpperCase();

  console.log(shout);   // JAVASCRIPT
  console.log(word);    // JavaScript — unchanged
  ```
- `.slice(4)` with one number means "from index 4 to the end": `"JavaScript".slice(4)` is `"Script"`.
- Everything is case-sensitive: `"JavaScript".includes("script")` is `false`. To compare without caring about capitals, turn both sides into lower case first.

### Looping over a string
It's the same loop as for an array:

```js
function countLetter(text, letter) {
    let count = 0;

    for (let i = 0; i < text.length; i++) {
        if (text[i] === letter) {
            count++;
        }
    }

    return count;
}

console.log(countLetter("banana", "a"));   // 3
```

A loop, an `if`, and a counter. That shape solves a huge number of problems: count the vowels, count the spaces, count the capitals.

To **build** a new string, start with an empty one and add to it on each round:

```js
function repeatWord(word, times) {
    let result = "";

    for (let i = 0; i < times; i++) {
        result += word;
    }

    return result;
}

console.log(repeatWord("ha", 3));   // hahaha
```

One last trick: `<` and `>` work on strings as well. They compare in dictionary order, so `"a" < "b"` is `true`. That gives you a way to check whether a character is a digit: `char >= "0" && char <= "9"`.

### Practice Now
With `const title = "The Quick Brown Fox";`: log its length, its upper-case and lower-case versions, whether it includes `"Quick"`, whether it includes `"quick"`, and the word `Quick` on its own using `.slice`. Then write `countSpaces(text)` with a loop. `countSpaces(title)` should be `3`.

---

## 14. The `Math` Toolbox

`Math` is a built-in box of maths tools. It's spelled with a capital **M**.

| Tool | What it does | Example | Result |
|---|---|---|---|
| `Math.round(n)` | rounds to the **nearest** whole number | `Math.round(4.6)` | `5` |
| `Math.floor(n)` | rounds **down** | `Math.floor(4.9)` | `4` |
| `Math.max(a, b, ...)` | the largest of the numbers you give it | `Math.max(3, 9, 4)` | `9` |
| `Math.random()` | a random decimal from 0 up to (but never reaching) 1 | `Math.random()` | e.g. `0.7314…` |
| `Math.PI` | π — no brackets, it's a value | `Math.PI` | `3.14159…` |

### Recipe: round to 2 decimal places
`Math.round` only makes whole numbers. The trick is to multiply by 100, round, and divide by 100 again:

```js
const price = 28.756;

console.log(Math.round(price * 100) / 100);   // 28.76
```

You'll need this sooner than you think, because computers can't store every decimal exactly:

```js
console.log(0.1 + 0.2);   // 0.30000000000000004
```

That isn't a bug in your code, and it isn't only JavaScript — nearly every programming language does it. Whenever you show money or measurements, round them.

### Recipe: a random whole number

```js
const dice = Math.floor(Math.random() * 6) + 1;   // 1, 2, 3, 4, 5, or 6
```

Read it from the inside out:

1. `Math.random()` → a decimal from 0 up to 0.999…
2. `* 6` → from 0 up to 5.999…
3. `Math.floor(...)` → 0, 1, 2, 3, 4, or 5
4. `+ 1` → 1 to 6

The same idea picks a random item from an array: the index is `Math.floor(Math.random() * items.length)`.

### Practice Now
Log `Math.round(7.5)`, `Math.round(7.49)`, `Math.floor(7.99)`, and `Math.max(12, 45, 7)`. Then write `circleArea(radius)` — π × radius² — rounded to 2 decimal places. `circleArea(1)` should be `3.14`, and `circleArea(2.5)` should be `19.63`. Finally, put the dice line inside a loop that runs 10 times, and check that every result is between 1 and 6.

---

## 15. Debugging Habits

Your code will be wrong far more often than it's right. That's true of everybody who writes JavaScript, including people who've done it for twenty years. The skill isn't avoiding bugs. It's finding them quickly. Five habits:

**1. Keep the Console open. Always.**
In HTML and CSS, a mistake shows up on the page. In JS, a mistake often shows *nothing at all* — unless the Console is open.

**2. Read the red message. All of it.**
The kind of error, the detail, and the file and line. These are the four you'll meet most often:

| Error | What it usually means |
|---|---|
| `ReferenceError: x is not defined` | A name JS doesn't know: a typo, text with no quotes round it, or a variable used outside the function it lives in. |
| `TypeError: Assignment to constant variable.` | You tried to change a `const`. Make it a `let`. |
| `TypeError: x is not a function` | You called something that isn't a function — usually a typo or a wrong capital letter, like `console.Log`. |
| `SyntaxError: ...` | JS couldn't read the file at all: a missing or extra bracket, brace, or quote. **Nothing** in the file runs. Look at the line it names, and the line above it. |

**3. No error, but the wrong answer? Log your way in.**
Put a `console.log` inside the function to see the values at each step. Label each one, or you'll end up staring at a column of mystery numbers:

```js
function averageOfThree(a, b, c) {
    const sum = a + b + c;
    console.log("sum:", sum);

    return sum / 3;
}
```

`console.log` can take several values, separated by commas. It prints them side by side. Delete these extra logs once the bug is fixed.

**4. Change one thing at a time.**
Write three lines, save, check the Console. If you write thirty lines and then something breaks, the bug could be anywhere. If you wrote one line, you know exactly where it is.

**5. Test more than the easy case.**
For every function: a normal value, the boundary values, and something awkward — `0`, a negative number, an empty string, an empty array.

And when you're really stuck, **explain the code out loud, line by line** — to a friend, or to a rubber duck on your desk. It sounds silly. It works, because it makes you say what each line *actually* does, instead of what you meant it to do.

### Practice Now
This function has a bug in it, **on purpose**. It should return the average of three numbers. There's no error, but `averageOfThree(10, 20, 30)` gives `40` instead of `20`:

```js
function averageOfThree(a, b, c) {
    return a + b + c / 3;   // ❌ wrong answer, no error
}
```

Type it in exactly as it is. Add labelled logs until you can see where the `40` comes from — try logging `c / 3` on its own. Then fix it, and check that you now get `20`. (The rule you need is in Section 7: which part of that line does JS work out first?)

✅ **Checkpoint:** You can name the three parts of an error message, and you have a plan for a function that gives the wrong answer with no error at all.

---

## 16. Guided Practice: Build a Calculator Toolkit

This is the main build for Class 6. There's no page to style this time. What you're making is a file of small, correct, tested functions — and a Console full of right answers.

### Requirements
- [ ] `index.html` loads `app.js` with a `<script>` tag at the end of `<body>`
- [ ] Four basic functions — `add`, `subtract`, `multiply`, `divide` — that each **return** their answer
- [ ] `divide` checks for dividing by zero
- [ ] `calculate(a, operator, b)` picks the right function from an operator string (`"+"`, `"-"`, `"*"`, `"/"`), and copes with an operator it doesn't know
- [ ] `roundTo2(n)` rounds to 2 decimal places
- [ ] `sumAll(numbers)` and `average(numbers)` work on an array of any length — including an empty one
- [ ] A `for` loop prints a times table, using `multiply`
- [ ] Every function is tested with logged calls
- [ ] No red in the Console

**`index.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Calculator Toolkit</title>
</head>
<body>
    <h1>Calculator Toolkit</h1>
    <p>Nothing to see on the page. Open the Console.</p>

    <script src="app.js"></script>
</body>
</html>
```

**`app.js`**

```js
// Calculator toolkit — Class 6

// ---------- The four basics ----------

function add(a, b) {
    return a + b;
}

function subtract(a, b) {
    return a - b;
}

function multiply(a, b) {
    return a * b;
}

function divide(a, b) {
    if (b === 0) {
        return "Cannot divide by zero";
    }

    return a / b;
}

// ---------- One function that picks the right one ----------

function calculate(a, operator, b) {
    if (operator === "+") {
        return add(a, b);
    } else if (operator === "-") {
        return subtract(a, b);
    } else if (operator === "*") {
        return multiply(a, b);
    } else if (operator === "/") {
        return divide(a, b);
    } else {
        return "Unknown operator";
    }
}

// ---------- Helpers ----------

function roundTo2(n) {
    return Math.round(n * 100) / 100;
}

function sumAll(numbers) {
    let total = 0;

    for (let i = 0; i < numbers.length; i++) {
        total = add(total, numbers[i]);
    }

    return total;
}

function average(numbers) {
    if (numbers.length === 0) {
        return 0;
    }

    return roundTo2(divide(sumAll(numbers), numbers.length));
}

// ---------- Tests ----------

console.log(`7 + 5 = ${calculate(7, "+", 5)}`);
console.log(`7 - 5 = ${calculate(7, "-", 5)}`);
console.log(`7 * 5 = ${calculate(7, "*", 5)}`);
console.log(`7 / 5 = ${calculate(7, "/", 5)}`);
console.log(`7 / 0 = ${calculate(7, "/", 0)}`);
console.log(`7 ? 5 = ${calculate(7, "?", 5)}`);

console.log(roundTo2(10 / 3));
console.log(roundTo2(0.1 + 0.2));
console.log(roundTo2(5));

const scores = [72, 85, 90, 64, 88];

console.log(`Total: ${sumAll(scores)}`);
console.log(`Average: ${average(scores)}`);
console.log(`Average of nothing: ${average([])}`);

// ---------- A times table ----------

const table = 7;

for (let i = 1; i <= 12; i++) {
    console.log(`${i} x ${table} = ${multiply(i, table)}`);
}
```

Type it by hand — don't paste. Save after each function and check the Console for red before you write the next one. Then open `index.html` with Live Server.

Notice how the functions **call each other**. `calculate` doesn't do any maths itself; it hands the work to the four basics. `average` uses `sumAll`, `divide`, and `roundTo2`. Small functions that each do one job, joined together: that's how every real program is built.

### What you should see

| Lines in the Console | What they show |
|---|---|
| `7 + 5 = 12`, `7 - 5 = 2`, `7 * 5 = 35`, `7 / 5 = 1.4` | the four basics, called through `calculate` |
| `7 / 0 = Cannot divide by zero` | the zero check in `divide` |
| `7 ? 5 = Unknown operator` | the final `else` in `calculate` |
| `3.33`, `0.3`, `5` | `roundTo2` — including the `0.1 + 0.2` problem, fixed |
| `Total: 399`, `Average: 79.8` | `sumAll` and `average` on five scores |
| `Average of nothing: 0` | the empty-array check in `average` |
| `1 x 7 = 7` … `12 x 7 = 84` | twelve lines from the loop |

### Now break it, then fix it
Do these one at a time. Predict what will change **before** you save, and undo each one afterwards.

1. Delete the word `return` in `add` (leave `a + b;`). There's no error — count how many lines of output are now wrong.
2. In `sumAll`, change `i < numbers.length` to `i <= numbers.length`.
3. Delete the zero check in `divide`. What does JS give for `7 / 0`?

### Acceptance criteria
- The Console shows every line from the table, in order, with no red.
- None of the functions contains a `console.log`. Each one returns its value, and the logging happens outside.
- `calculate` calls the four basic functions; it doesn't repeat their maths.
- `sumAll` and `average` give the right answer for an array of 1 item, 5 items, and 0 items.
- Changing `const table = 7;` to another number changes the whole times table.
- You can explain what happened in each of the three "break it" experiments.

✅ **Checkpoint:** A file of small functions that call each other, each one tested. You wrote no CSS at all, and it's the most "programming" you've done so far.

---

## 17. Troubleshooting

| Problem | Likely cause |
|---|---|
| Nothing appears in the Console at all | The script isn't loading: the `src` path or file name is wrong (the Console shows a red line ending in `404 (Not Found)`), the closing `</script>` is missing, or you're looking at a different tab from the one Live Server opened. Or the functions are defined but never **called**. |
| `ReferenceError: something is not defined` | A typo in a name, the wrong capitals (`userName` vs `username`), text with no quotes round it, or a variable used outside the function where it was made. |
| `TypeError: Assignment to constant variable.` | You're changing a `const`. Declare it with `let` instead. |
| `SyntaxError`, and nothing in the file runs | A missing or extra `)`, `}`, `"`, or backtick. Look at the line the message names, then the line above it. |
| A function call logs `undefined` | The function has no `return` — or its `return` is in a branch that didn't run. |
| `"22"` instead of `4`, or `"1005"` instead of `105` | One of the values is a string, so `+` joined instead of adding. Check with `typeof`, and convert with `Number()`. |
| `NaN` | Maths on something that isn't a number: often `undefined` (an index past the end of an array, or a missing argument), or a string that isn't numeric. |
| An `if` block always runs | `=` instead of `===` in the condition. |
| An `else if` branch never runs | A condition higher up the ladder catches the value first. Put the strictest test first. |
| The loop logs `undefined` at the end | `i <= array.length`. Use `<`. |
| The loop misses the last item | `i < array.length - 1`. Use `i < array.length`. |
| The total comes out wrong, or the function stops after one round | `let total = 0;` is inside the loop (it resets every round), or `return` is inside the loop (it ends the function on round one). |
| The tab freezes | An infinite loop: the `while` condition never becomes false. Close the tab, fix the code, and open it again. |
| `${firstName}` appears in the output, exactly as typed | Ordinary quotes instead of backticks. Only backticks fill in `${ }`. |
| `.toUpperCase()` "didn't work" | String methods give back a **new** string. They don't change the original. Store the result, or log it. |

---

## 18. Self-Check: Can You Answer These?

Try without scrolling back.

1. Where does the `<script>` tag go, and what does `console.log` do?
2. `let` or `const` — which do you reach for first, and when do you switch?
3. Name the five data types from this class. What does `typeof "42"` give?
4. What is `17 % 5`? Give one common use for `%`.
5. What do `"3" + 4` and `"3" * 4` give? Why are they different?
6. What's the difference between `=`, `==`, and `===`?
7. What's the difference between `return` and `console.log`? What does a function with no `return` give back?
8. In an `if` / `else if` ladder, why does the order of the conditions matter?
9. Write the loop header that goes through every item in an array called `items`. What is the index of the last item?
10. The Console shows a red error. What three things does the message tell you?

---

## 19. Homework

1. **Write five small functions that solve logic problems** (the course homework). In a fresh folder, with an `index.html` and an `app.js`:
   - [ ] Pick any five from this list: `isEven(n)`, `maxOfTwo(a, b)`, `absoluteValue(n)`, `isVowel(char)`, `sumTo(n)`, `factorial(n)`, `countVowels(text)`, `reverseString(text)`, `largestInArray(numbers)`, `isPrime(n)`
   - [ ] Every function **returns** its answer — no `console.log` inside
   - [ ] At least one makes a decision with `if`, at least one uses a loop, and at least one works on an array or a string
   - [ ] Three logged test calls for each function, including one awkward value (zero, a negative number, an empty string, an empty array)
   - [ ] A comment above each function saying, in plain words, what it does
   - [ ] No red in the Console

2. *(Optional)* Add `power(base, exponent)` to your calculator toolkit **without** using `**` — use a loop that multiplies. Then teach `calculate` a new operator, `"^"`, that uses it.

For a lot more practice on this class — drills, Console mini-games, "predict the output" puzzles, and debugging exercises with answers — see the **Class 6** section of [`assignments.md`](assignments.md).

---

## What's Next

Class 7 is **JavaScript & the DOM** — where the logic from this class finally meets your pages. You'll learn how JavaScript finds an element on the page, changes its text and its classes, and listens for clicks and typing. Your contact form will say "thank you" without reloading, and your pages will get a light/dark mode button. Keep today's functions safe — you'll be plugging them in.
