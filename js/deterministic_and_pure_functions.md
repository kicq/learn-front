### Побочный эффект (Side Effect)

**Побочный эффект** — это любое изменение состояния программы или взаимодействие с внешним миром, которое происходит вне возвращаемого значения функции. Это может включать в себя:

1. Изменение глобальных переменных или внешних объектов.
2. Взаимодействие с файловой системой (чтение/запись файлов).
3. Взаимодействие с базой данных.
4. Ввод/вывод (например, печать в консоль или модификация DOM).
5. Изменение аргументов функции.

### Примеры побочных эффектов

#### Пример 1: Изменение глобальной переменной

```javascript
let count = 0;

function increment() {
  count += 1; // Изменение глобальной переменной count
  return count;
}

console.log(increment()); // 1
console.log(count); // 1
```

Функция `increment` изменяет глобальную переменную `count`, что является побочным эффектом.

#### Пример 2: Взаимодействие с консолью

```javascript
function logMessage(message) {
  console.log(message); // Печать сообщения в консоль
}

logMessage("Hello, World!"); // Выводит "Hello, World!" в консоль
```

Функция `logMessage` вызывает `console.log`, что является побочным эффектом.

### Пример функции без побочных эффектов

```javascript
function add(a, b) {
  return a + b; // Не изменяет внешнее состояние, просто возвращает результат
}

const result = add(2, 3); // 5
console.log(result); // 5
```

Функция `add` не вызывает побочных эффектов, так как она не изменяет внешние переменные, не взаимодействует с внешним миром и не изменяет аргументы функции.
Побочные эффекты могут усложнить понимание и тестирование программ, так как функции с побочными эффектами зависят от состояния внешнего мира и могут вести себя непредсказуемо в разных контекстах. Чистые функции, напротив, легко тестировать и предсказуемо использовать, так как они не имеют побочных эффектов и зависят только от своих входных данных.

# Детерминированная функция
1. **Один и тот же результат для одних и тех же входных данных**: Для одного и того же набора входных данных детерминированная функция всегда возвращает один и тот же результат.
2. **Отсутствие побочных эффектов**: Детерминированная функция не должна изменять внешнее окружение, то есть не должна менять глобальные переменные, писать в консоль, изменять параметры и т.д.

# Чистая функция
1. **Один и тот же результат для одних и тех же входных данных**: Чистая функция всегда возвращает один и тот же результат для одного и того же набора входных данных.
2. **Отсутствие побочных эффектов**: Чистая функция не должна изменять внешнее окружение. 
3. **Чистая функция всегда детерминированна**: Любая чистая функция по определению является детерминированной.

### Примеры

#### Чистая и детерминированная функция
```javascript
function add(a, b) {
  return a + b;
}
```
- **Результат**: Всегда возвращает одно и то же значение для одних и тех же входных данных.
- **Побочные эффекты**: Нет, функция не изменяет внешнее окружение.

#### Функция с побочными эффектами (не чистая и не детерминированная)
```javascript
let count = 0;

function increment() {
  count += 1;
  return count;
}
```
- **Результат**: Не всегда возвращает одно и то же значение для одних и тех же входных данных.
- **Побочные эффекты**: Да, функция изменяет глобальную переменную `count`.

#### Нечистая, но детерминированная функция (редкий случай, но возможный)
```javascript
let factor = 2;

function multiply(a) {
  return a * factor;
}
```
- **Результат**: Всегда возвращает одно и то же значение для одних и тех же входных данных, если `factor` не изменяется.
- **Побочные эффекты**: Нет, функция не изменяет внешнее окружение, но зависит от внешней переменной.

### Вывод

Чистая функция по определению детерминированная, потому что она всегда возвращает один и тот же результат для одних и тех же входных данных и не имеет побочных эффектов. Однако, не каждая детерминированная функция чистая, если она изменяет внешние переменные или зависит от них.