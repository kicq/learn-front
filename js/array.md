# Массивы

## Введение в массивы

Массивы в JavaScript - это структура данных, которая позволяет хранить несколько значений в одном месте. Это может быть полезно, когда нужно сохранить список элементов, например, чисел, строк, объектов и других массивов.

### Создание массива

Массивы создаются с использованием квадратных скобок `[]`. Вот несколько примеров:

```javascript
// Пустой массив
let arr = [];

// Массив с числами
let numbers = [1, 2, 3, 4, 5];

// Массив со строками
let fruits = ["apple", "banana", "cherry"];

// Массив с разными типами данных
let mixed = [1, "hello", true, null];
```

### Доступ к элементам массива

Элементы массива доступны по их индексу, начиная с 0.

```javascript
let fruits = ["apple", "banana", "cherry"];

console.log(fruits[0]); // "apple"
console.log(fruits[1]); // "banana"
console.log(fruits[2]); // "cherry"
```

### Изменение элементов массива

Вы можете изменить элемент массива, обратившись к нему по индексу и присвоив новое значение:

```javascript
let fruits = ["apple", "banana", "cherry"];

fruits[1] = "orange";

console.log(fruits); // ["apple", "orange", "cherry"]
```

### Длина массива

Свойство `length` возвращает количество элементов в массиве:

```javascript
let fruits = ["apple", "banana", "cherry"];

console.log(fruits.length); // 3
```

## Основные методы работы с массивами

### Добавление и удаление элементов

- `push()` добавляет элемент в конец массива:

  ```javascript
  let fruits = ["apple", "banana"];

  fruits.push("cherry");

  console.log(fruits); // ["apple", "banana", "cherry"]
  ```

- `pop()` удаляет последний элемент массива:

  ```javascript
  let fruits = ["apple", "banana", "cherry"];

  let last = fruits.pop();

  console.log(fruits); // ["apple", "banana"]
  console.log(last);   // "cherry"
  ```

- `unshift()` добавляет элемент в начало массива:

  ```javascript
  let fruits = ["banana", "cherry"];

  fruits.unshift("apple");

  console.log(fruits); // ["apple", "banana", "cherry"]
  ```

- `shift()` удаляет первый элемент массива:

  ```javascript
  let fruits = ["apple", "banana", "cherry"];

  let first = fruits.shift();

  console.log(fruits); // ["banana", "cherry"]
  console.log(first);  // "apple"
  ```

### Перебор массива

Есть несколько способов перебрать элементы массива.

- `for` цикл:

  ```javascript
  let fruits = ["apple", "banana", "cherry"];

  for (let i = 0; i < fruits.length; i++) {
      console.log(fruits[i]);
  }
  ```

- `forEach()` метод:

  ```javascript
  let fruits = ["apple", "banana", "cherry"];

  fruits.forEach(function(fruit) {
      console.log(fruit);
  });
  ```

- `map()` создает новый массив, применяя функцию к каждому элементу:

  ```javascript
  let numbers = [1, 2, 3];

  let squares = numbers.map(function(num) {
      return num * num;
  });

  console.log(squares); // [1, 4, 9]
  ```

### Поиск и фильтрация

- `indexOf()` возвращает индекс первого вхождения элемента в массиве:

  ```javascript
  let fruits = ["apple", "banana", "cherry"];

  console.log(fruits.indexOf("banana")); // 1
  ```

- `includes()` проверяет, существует ли элемент в массиве:

  ```javascript
  let fruits = ["apple", "banana", "cherry"];

  console.log(fruits.includes("banana")); // true
  ```

- `filter()` создает новый массив с элементами, которые проходят тест:

  ```javascript
  let numbers = [1, 2, 3, 4, 5];

  let evenNumbers = numbers.filter(function(num) {
      return num % 2 === 0;
  });

  console.log(evenNumbers); // [2, 4]
  ```

### Сортировка массива

- `sort()` сортирует массив:

  ```javascript
  let fruits = ["cherry", "banana", "apple"];

  fruits.sort();

  console.log(fruits); // ["apple", "banana", "cherry"]
  ```

- `reverse()` переворачивает массив:

  ```javascript
  let fruits = ["apple", "banana", "cherry"];

  fruits.reverse();

  console.log(fruits); // ["cherry", "banana", "apple"]
  ```
