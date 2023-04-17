# Functions

##### Different types of declare function

```tsx
function speak () {...}

const speak = function () {...}
const walk = () => {...}

const obj = {
	speak: function () {...},
	walk () {...},
}
```

##### Arguments on function

```tsx
function fn(...args) {
  console.log(arguments);
  console.log(args);

  for (let arg of arguments) {
    console.log(arg);
  }
}

fn("A", "B", "C");
```

```tsx
type Operator = '+' | '

function fn (operator: Operator, acc: number, ...numbers: number[]) {
	for (let number of numbers) {
		if (operator === '+') { acc += number }
		if (operator === '-') { acc -= number }
	}

	console.log(acc)
}

fn ('+', 0, 1, 2, 3, 4, 5)
```

##### Return

```tsx
function createMultiplier(multiplier) {
  return function (n) {
    return n * multiplier;
  };
}

const duplicate = createMultiplier(2);
const triple = createMultiplier(3);

console.log(duplicate(1)); // return 2
console.log(triple(1)); // return 3
```

##### IIFE (Immediately invoked function expression)

```tsx
(function (...params) {...})('Leandro', 'Cruz')
```

##### Factory functions

```tsx
function personFactory(name: string, lastName: string) {
  return {
    name: name,
    lastName: lastName,
    type: "person",
    get fullName() {
      return name + " " + lastName;
    },
    set fullName(fullName: string) {
      const value = fullName.split(" ");
      name = value.shift();
      lastName = value.join(" ");
    },
  };
}

const leh = personFactory("Leandro", "Cruz");
```
