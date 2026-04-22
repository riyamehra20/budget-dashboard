## 1. Parsing Input Values
Inputs always return Strings. Convert to number before using:
```js
let amount = parseFloat(input.value);
let salary = Number(input.value);
```

## 2. Validation
Check before doing any calculation:
```js
if (isNaN(amount) || amount <= 0) {
  // show error, stop here
  return;
}
```

## 3. Array Methods
Add an expense:
```js
expenses.push({ name: "Rent", amount: 5000 });
```
Remove an expense by index:
```js
expenses.splice(index, 1);
```
Calculate total using reduce:
```js
let total = expenses.reduce(function(sum, exp) {
  return sum + exp.amount;
}, 0);
```

## 4. DOM Manipulation
Read input value:
```js
let value = document.getElementById('salary-input').value;
```
Update text on screen:
```js
document.getElementById('disp-salary').textContent = 'Rs ' + salary;
```
Dynamically create a list item:
```js
let li = document.createElement('li');
li.textContent = 'Rent - Rs 5000';
document.getElementById('expense-list').appendChild(li);
```

## 5. localStorage
Only stores Strings — use JSON for arrays/objects.

Save:
```js
localStorage.setItem('expenses', JSON.stringify(expenses));
```
Load:
```js
let expenses = JSON.parse(localStorage.getItem('expenses'));
```

## 6. Event Listeners
Button click:
```js
document.getElementById('add-btn').addEventListener('click', addExpense);
```
Enter key on input:
```js
input.addEventListener('keydown', function(e) {
  if (e.key === 'Enter') addExpense();
});
```
