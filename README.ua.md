# Домашнє завдання №2

## JavaScript. Розгалуження та логічні оператори

---

## Інструкція

- Створи репозиторій **goit-js-hw-02** та склонюй його собі на комп’ютер.
- У папці `goit-js-hw-02` створи структуру проєкту відповідно до схеми в завданні.

⚠️ **Зверни увагу!**  
Імена файлів і папок, а також структура вкладеності, мають **точно відповідати** вимогам. Інакше робота не буде прийнята.

![Project preview](assets/homework-js-2.jpg)

- Прочитай кожне завдання та виконай його у відповідному файлі.
- Переконайся, що код відформатований за допомогою **Prettier**.
- Під час відкриття живої сторінки в консолі не повинно бути помилок або попереджень.
- Здай домашнє завдання на перевірку.

---

## Формат здачі

Домашня робота має містити **два посилання**:

- на вихідні файли (репозиторій з кодом);
- на робочу сторінку на **GitHub Pages**.

---

## Задача 1. Замовлення дроїдів

**Файл:** `task-1.js`

Станція з продажу ремонтних дроїдів готова до запуску — залишилося написати програмне забезпечення для відділу продажів.

### Завдання

Оголоси функцію `makeTransaction(quantity, pricePerDroid, customerCredits)`, яка складає та повертає повідомлення про купівлю ремонтних дроїдів.

Функція приймає три параметри:

- `quantity` — кількість замовлених дроїдів;
- `pricePerDroid` — ціна одного дроїда;
- `customerCredits` — сума коштів на рахунку клієнта.

### Логіка роботи функції

1. Оголоси змінну для зберігання **загальної суми замовлення** та обчисли її.
2. Додай перевірку можливості оплати:
   - якщо сума замовлення перевищує кількість кредитів клієнта — поверни рядок  
     `"Insufficient funds!"`;
   - інакше — поверни рядок  
     `"You ordered <quantity> droids worth <totalPrice> credits!"`.

### Код для перевірки

```js
console.log(makeTransaction(5, 3000, 23000)); // "You ordered 5 droids worth 15000 credits!"
console.log(makeTransaction(3, 1000, 15000)); // "You ordered 3 droids worth 3000 credits!"
console.log(makeTransaction(10, 5000, 8000)); // "Insufficient funds!"
console.log(makeTransaction(8, 2000, 10000)); // "Insufficient funds!"
console.log(makeTransaction(10, 500, 5000)); // "You ordered 10 droids worth 5000 credits!"
```

## На що буде звертати увагу ментор при перевірці

- Оголошена функція `makeTransaction(quantity, pricePerDroid, customerCredits)`
- Виклик `makeTransaction(5, 3000, 23000)` повертає  
  `"You ordered 5 droids worth 15000 credits!"`
- Виклик `makeTransaction(3, 1000, 15000)` повертає  
  `"You ordered 3 droids worth 3000 credits!"`
- Виклик `makeTransaction(10, 5000, 8000)` повертає  
  `"Insufficient funds!"`
- Виклик `makeTransaction(8, 2000, 10000)` повертає  
  `"Insufficient funds!"`
- Виклик `makeTransaction(10, 500, 5000)` повертає  
  `"You ordered 10 droids worth 5000 credits!"`

---

## Задача 2. Форматування повідомлення

**Файл:** `task-2.js`

Виконуй це завдання у файлі `task-2.js`.

Оголоси функцію `formatMessage(message, maxLength)`, яка приймає рядок (`message`) та перевіряє його довжину відповідно до максимальної довжини (`maxLength`).

### Логіка функції

- Якщо довжина рядка менша або дорівнює `maxLength`, функція повертає початковий рядок без змін.
- Якщо довжина рядка перевищує `maxLength`, функція обрізає рядок до `maxLength` символів, додає трикрапку `"..."` в кінці та повертає обрізану версію.

### Код для перевірки

```js
console.log(formatMessage("Curabitur ligula sapien", 16)); // "Curabitur ligula..."
console.log(formatMessage("Curabitur ligula sapien", 23)); // "Curabitur ligula sapien"
console.log(formatMessage("Vestibulum facilisis purus nec", 20)); // "Vestibulum facilisis..."
console.log(formatMessage("Vestibulum facilisis purus nec", 30)); // "Vestibulum facilisis purus nec"
console.log(formatMessage("Nunc sed turpis a felis in nunc fringilla", 15)); // "Nunc sed turpis..."
console.log(formatMessage("Nunc sed turpis a felis in nunc fringilla", 41)); // "Nunc sed turpis a felis in nunc fringilla"
```

## На що буде звертати увагу ментор при перевірці

- Оголошена функція `formatMessage(message, maxLength)`
- Виклик `formatMessage("Curabitur ligula sapien", 16)` повертає `"Curabitur ligula..."`
- Виклик `formatMessage("Curabitur ligula sapien", 23)` повертає `"Curabitur ligula sapien"`
- Виклик `formatMessage("Vestibulum facilisis purus nec", 20)` повертає `"Vestibulum facilisis..."`
- Виклик `formatMessage("Vestibulum facilisis purus nec", 30)` повертає `"Vestibulum facilisis purus nec"`
- Виклик `formatMessage("Nunc sed turpis a felis in nunc fringilla", 15)` повертає `"Nunc sed turpis..."`
- Виклик `formatMessage("Nunc sed turpis a felis in nunc fringilla", 41)` повертає `"Nunc sed turpis a felis in nunc fringilla"`

---

## Задача 3. Перевірка спаму

### Виконання

Функція `checkForSpam(message)` приймає рядок (`message`), перевіряє його на наявність заборонених слів `spam` та `sale`, і повертає результат перевірки. Слова можуть бути у будь-якому регістрі, наприклад `SPAM` або `sAlE`.

### Логіка роботи функції

- Якщо знайдено заборонене слово (`spam` або `sale`), функція повертає `true`
- Якщо заборонених слів немає — функція повертає `false`

### Код для перевірки

```js
console.log(checkForSpam("Latest technology news")); // false
console.log(checkForSpam("JavaScript weekly newsletter")); // false
console.log(checkForSpam("Get best sale offers now!")); // true
console.log(checkForSpam("Amazing SalE, only tonight!")); // true
console.log(checkForSpam("Trust me, this is not a spam message")); // true
console.log(checkForSpam("Get rid of sPaM emails. Our book in on sale!")); // true
console.log(checkForSpam("[SPAM] How to earn fast money?")); // true
```

### На що буде звертати увагу ментор при перевірці

- Оголошена функція `checkForSpam(message)`
- Виклик функції `checkForSpam("Latest technology news")` повертає `false`
- Виклик функції `checkForSpam("JavaScript weekly newsletter")` повертає `false`
- Виклик функції `checkForSpam("Get best sale offers now!")` повертає `true`
- Виклик функції `checkForSpam("Amazing SalE, only tonight!")` повертає `true`
- Виклик функції `checkForSpam("Trust me, this is not a spam message")` повертає `true`
- Виклик функції `checkForSpam("Get rid of sPaM emails. Our book in on sale!")` повертає `true`
- Виклик функції `checkForSpam("[SPAM] How to earn fast money?")` повертає `true`

---

## Задача 4. Доставка товару

**Файл:** `task-4.js`

Оголоси функцію `getShippingCost(country)`, яка перевіряє можливість доставки товару в країну користувача (`country`) і повертає повідомлення про результат. Обов’язково використай інструкцію `switch`.

### Формат рядка, що повертається:

"Shipping to <country> will cost <price> credits"

де замість `<country>` і `<price>` підставляються відповідні значення.

### Список країн і вартість доставки

- China — 100 кредитів
- Chile — 250 кредитів
- Australia — 170 кредитів
- Jamaica — 120 кредитів

Зі списку видно, що доставка можлива не скрізь. Якщо зазначена країна відсутня у списку, функція повинна повернути рядок:

Візьми код нижче і встав після оголошення своєї функції для перевірки коректності її роботи. У консоль будуть виведені результати її роботи.

```js
console.log(getShippingCost("Australia")); // "Shipping to Australia will cost 170 credits"
console.log(getShippingCost("Germany")); // "Sorry, there is no delivery to your country"
console.log(getShippingCost("China")); // "Shipping to China will cost 100 credits"
console.log(getShippingCost("Chile")); // "Shipping to Chile will cost 250 credits"
console.log(getShippingCost("Jamaica")); // "Shipping to Jamaica will cost 120 credits"
console.log(getShippingCost("Sweden")); // "Sorry, there is no delivery to your country"
```

Залиш цей код для перевірки ментором.

## На що буде звертати увагу ментор при перевірці:

- Оголошена функція getShippingCost(country)
- У тілі функції використана інструкція switch
- Виклик getShippingCost("Australia") повертає "Shipping to Australia will cost 170 credits"
- Виклик getShippingCost("Germany") повертає "Sorry, there is no delivery to your country"
- Виклик getShippingCost("China") повертає "Shipping to China will cost 100 credits"
- Виклик getShippingCost("Chile") повертає "Shipping to Chile will cost 250 credits"
- Виклик getShippingCost("Jamaica") повертає "Shipping to Jamaica will cost 120 credits"
- Виклик getShippingCost("Sweden") повертає "Sorry, there is no delivery to your country"

---

**Жива сторінка: [GitHub Pages](https://akinaru72.github.io/goit-js-hw-02/)**
