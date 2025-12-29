# Homework №2

## JavaScript. Branching and Logical Operators

---

## Instructions

- Create a repository **goit-js-hw-02** and clone it to your computer.
- In the `goit-js-hw-02` folder, create the project structure according to the scheme in the task.

⚠️ **Attention!**  
File and folder names, as well as the nesting structure, must **exactly match** the requirements. Otherwise, the homework will not be accepted.

![Project preview](assets/homework-js-2.jpg)

- Read each task carefully and complete it in the corresponding file.
- Make sure the code is formatted using **Prettier**.
- When opening the live page, there should be no errors or warnings in the console.
- Submit the homework for review.

---

## Submission Format

The homework must include **two links**:

- a link to the source files (repository with the code);
- a link to the live page on **GitHub Pages**.

---

## Task 1. Droid Order

**File:** `task-1.js`

The repair droid sales station is ready to launch — all that’s left is to write the software for the sales department.

### Task Description

Declare a function `makeTransaction(quantity, pricePerDroid, customerCredits)` that creates and returns a message about purchasing repair droids.

The function takes three parameters:

- `quantity` — the number of ordered droids;
- `pricePerDroid` — the price of one droid;
- `customerCredits` — the amount of credits in the customer’s account.

### Function Logic

1. Declare a variable to store the **total order cost** and calculate its value.
2. Add a check to determine whether the customer can pay for the order:
   - if the total cost exceeds the customer’s credits, return  
     `"Insufficient funds!"`;
   - otherwise, return  
     `"You ordered <quantity> droids worth <totalPrice> credits!"`.

---

### Test Code

```js
console.log(makeTransaction(5, 3000, 23000)); // "You ordered 5 droids worth 15000 credits!"
console.log(makeTransaction(3, 1000, 15000)); // "You ordered 3 droids worth 3000 credits!"
console.log(makeTransaction(10, 5000, 8000)); // "Insufficient funds!"
console.log(makeTransaction(8, 2000, 10000)); // "Insufficient funds!"
console.log(makeTransaction(10, 500, 5000)); // "You ordered 10 droids worth 5000 credits!"
```

## What the mentor will check during the review

- The function `makeTransaction(quantity, pricePerDroid, customerCredits)` is declared
- Calling `makeTransaction(5, 3000, 23000)` returns  
  `"You ordered 5 droids worth 15000 credits!"`
- Calling `makeTransaction(3, 1000, 15000)` returns  
  `"You ordered 3 droids worth 3000 credits!"`
- Calling `makeTransaction(10, 5000, 8000)` returns  
  `"Insufficient funds!"`
- Calling `makeTransaction(8, 2000, 10000)` returns  
  `"Insufficient funds!"`
- Calling `makeTransaction(10, 500, 5000)` returns  
  `"You ordered 10 droids worth 5000 credits!"`

## Task 2. Message Formatting

**File:** `task-2.js`

Work on this task in the file `task-2.js`.

Declare a function `formatMessage(message, maxLength)` that accepts a string (`message`) and checks its length against the specified maximum length (`maxLength`).

### Function Logic

- If the string length is less than or equal to `maxLength`, the function should return the original string unchanged.
- If the string length exceeds `maxLength`, the function should truncate the string to `maxLength` characters, add an ellipsis `"..."` at the end, and return the truncated version.

### Test Code

```js
console.log(formatMessage("Curabitur ligula sapien", 16)); // "Curabitur ligula..."
console.log(formatMessage("Curabitur ligula sapien", 23)); // "Curabitur ligula sapien"
console.log(formatMessage("Vestibulum facilisis purus nec", 20)); // "Vestibulum facilisis..."
console.log(formatMessage("Vestibulum facilisis purus nec", 30)); // "Vestibulum facilisis purus nec"
console.log(formatMessage("Nunc sed turpis a felis in nunc fringilla", 15)); // "Nunc sed turpis..."
console.log(formatMessage("Nunc sed turpis a felis in nunc fringilla", 41)); // "Nunc sed turpis a felis in nunc fringilla"
```

## Mentor Checkpoints

- Function `formatMessage(message, maxLength)` is declared
- Calling `formatMessage("Curabitur ligula sapien", 16)` returns `"Curabitur ligula..."`
- Calling `formatMessage("Curabitur ligula sapien", 23)` returns `"Curabitur ligula sapien"`
- Calling `formatMessage("Vestibulum facilisis purus nec", 20)` returns `"Vestibulum facilisis..."`
- Calling `formatMessage("Vestibulum facilisis purus nec", 30)` returns `"Vestibulum facilisis purus nec"`
- Calling `formatMessage("Nunc sed turpis a felis in nunc fringilla", 15)` returns `"Nunc sed turpis..."`
- Calling `formatMessage("Nunc sed turpis a felis in nunc fringilla", 41)` returns `"Nunc sed turpis a felis in nunc fringilla"`

---

### English version

````markdown
## Task 3. Spam Check

### Execution

The function `checkForSpam(message)` takes a string (`message`), checks it for forbidden words `spam` and `sale`, and returns the check result. Words can be in any case, e.g., `SPAM` or `sAlE`.

### Function logic

- If a forbidden word (`spam` or `sale`) is found, the function returns `true`
- If there are no forbidden words, the function returns `false`

### Test code

```js
console.log(checkForSpam("Latest technology news")); // false
console.log(checkForSpam("JavaScript weekly newsletter")); // false
console.log(checkForSpam("Get best sale offers now!")); // true
console.log(checkForSpam("Amazing SalE, only tonight!")); // true
console.log(checkForSpam("Trust me, this is not a spam message")); // true
console.log(checkForSpam("Get rid of sPaM emails. Our book in on sale!")); // true
console.log(checkForSpam("[SPAM] How to earn fast money?")); // true
```

### Mentor Checkpoints

- Function `checkForSpam(message)` is declared
- Calling `checkForSpam("Latest technology news")` returns `false`
- Calling `checkForSpam("JavaScript weekly newsletter")` returns `false`
- Calling `checkForSpam("Get best sale offers now!")` returns `true`
- Calling `checkForSpam("Amazing SalE, only tonight!")` returns `true`
- Calling `checkForSpam("Trust me, this is not a spam message")` returns `true`
- Calling `checkForSpam("Get rid of sPaM emails. Our book in on sale!")` returns `true`
- Calling `checkForSpam("[SPAM] How to earn fast money?")` returns `true`

## Task 4. Shipping Cost

**File:** `task-4.js`

Declare the function `getShippingCost(country)` which checks whether shipping to the user's country (`country`) is possible and returns a message about the result. Use a `switch` statement.

### Returned string format:

"Shipping to <country> will cost <price> credits"

where `<country>` and `<price>` are replaced with the appropriate values.

### List of countries and shipping costs

- China — 100 credits
- Chile — 250 credits
- Australia — 170 credits
- Jamaica — 120 credits

From the list, it is clear that shipping is not available everywhere. If the specified country is not on the list, the function should return:

Insert the code below after declaring your function to test its correctness. The console will display the results of the function calls.

```js
console.log(getShippingCost("Australia")); // "Shipping to Australia will cost 170 credits"
console.log(getShippingCost("Germany")); // "Sorry, there is no delivery to your country"
console.log(getShippingCost("China")); // "Shipping to China will cost 100 credits"
console.log(getShippingCost("Chile")); // "Shipping to Chile will cost 250 credits"
console.log(getShippingCost("Jamaica")); // "Shipping to Jamaica will cost 120 credits"
console.log(getShippingCost("Sweden")); // "Sorry, there is no delivery to your country"
```

Leave this code for mentor review.

## What the mentor will check:

- The function `getShippingCost(country)` is declared
- The function body uses a `switch` statement
- `getShippingCost("Australia")` returns "Shipping to Australia will cost 170 credits"
- `getShippingCost("Germany")` returns "Sorry, there is no delivery to your country"
- `getShippingCost("China")` returns "Shipping to China will cost 100 credits"
- `getShippingCost("Chile")` returns "Shipping to Chile will cost 250 credits"
- `getShippingCost("Jamaica")` returns "Shipping to Jamaica will cost 120 credits"
- `getShippingCost("Sweden")` returns "Sorry, there is no delivery to your country"

---

**Live page: [GitHub Pages](https://akinaru72.github.io/goit-js-hw-02/)**
````
