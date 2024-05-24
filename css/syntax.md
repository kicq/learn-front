# CSS: Ключевые слова, операторы, функции, директивы и синтаксис

## Ключевые слова в CSS

### Свойства отображения и позиционирования
- `display`: `block`, `inline`, `inline-block`, `flex`, `grid`, `none`
- `position`: `static`, `relative`, `absolute`, `fixed`, `sticky`
- `overflow`: `visible`, `hidden`, `scroll`, `auto`

### Свойства цвета
- `color`, `background-color`: `red`, `blue`, `green`, `transparent`

### Свойства текста
- `text-align`: `left`, `right`, `center`, `justify`
- `font-weight`: `normal`, `bold`, `bolder`, `lighter`
- `font-style`: `normal`, `italic`, `oblique`
- `text-decoration`: `none`, `underline`, `overline`, `line-through`

### Свойства фона
- `background-repeat`: `repeat`, `no-repeat`, `repeat-x`, `repeat-y`
- `background-size`: `auto`, `cover`, `contain`

### Свойства границ
- `border-style`: `none`, `solid`, `dotted`, `dashed`, `double`, `groove`, `ridge`, `inset`, `outset`
- `border-width`: `thin`, `medium`, `thick`

### Другие ключевые слова
- `visibility`: `visible`, `hidden`
- `cursor`: `default`, `pointer`, `text`, `move`, `wait`, `help`, `not-allowed`

## Операторы в CSS

### Селекторы
- **Типовой селектор**: `div`, `p`, `span`
- **Классовый селектор**: `.classname`
- **Идентификаторный селектор**: `#idname`
- **Комбинированные селекторы**: `div.classname`, `#idname.classname`
- **Дочерний селектор**: `parent > child`
- **Соседний селектор**: `element + adjacent`
- **Атрибутный селектор**: `input[type="text"]`

### Комбинаторы
- **Пробел** (descendant combinator): `div p` - выбирает все `<p>` внутри `<div>`.
- **`>`** (child combinator): `div > p` - выбирает непосредственных детей `<p>` внутри `<div>`.
- **`+`** (adjacent sibling combinator): `div + p` - выбирает следующий элемент `<p>`, который находится сразу после `<div>`.
- **`~`** (general sibling combinator): `div ~ p` - выбирает все `<p>`, которые являются братьями `<div>`.

### Псевдоклассы
- **Состояния**: `:hover`, `:active`, `:focus`, `:visited`, `:link`
- **Структурные**: `:first-child`, `:last-child`, `:nth-child(n)`, `:nth-of-type(n)`, `:only-child`, `:not(selector)`

### Псевдоэлементы
- `::before`
- `::after`
- `::first-line`
- `::first-letter`

## Цветовые значения
- **Шестнадцатеричные коды**: `color: #ff0000;`

## Функции
- **URL**: `background-image: url('image.png');`
- **Трансформация**: `transform: rotate(45deg);`
- **Вычисление**: `width: calc(100% - 50px);`
- **Цветовые функции**:
    - `background-color: rgb(255, 0, 0);`
    - `border-color: rgba(255, 0, 0, 0.5);`
    - `color: hsl(0, 100%, 50%);`
    - `color: hsla(0, 100%, 50%, 0.5);`

## Директивы CSS

### `@import`
- Используется для импорта одного CSS файла в другой.
    ```css
    @import url('styles.css');
    ```

### `@font-face`
- Используется для определения пользовательских шрифтов.
    ```css
    @font-face {
        font-family: 'MyCustomFont';
        src: url('mycustomfont.woff2') format('woff2'),
             url('mycustomfont.woff') format('woff');
    }
    ```

### `@keyframes`
- Используется для создания анимаций.
    ```css
    @keyframes slidein {
        from {
            transform: translateX(0%);
        }
        to {
            transform: translateX(100%);
        }
    }

    .animated-element {
        animation: slidein 3s ease-in-out;
    }
    ```

### `@supports`
- Используется для проверки поддержки браузером определенных свойств или значений.
    ```css
    @supports (display: grid) {
        .container {
            display: grid;
        }
    }
    ```

### `@page`
- Используется для задания стилей для печати.
    ```css
    @page {
        size: A4;
        margin: 1cm;
    }
    ```

### `@media`
- Используется для применения стилей в зависимости от характеристик устройства.
    ```css
    @media (max-width: 600px) {
        body {
            background-color: lightblue;
        }
    }
    ```

## Переменные в CSS

CSS-переменные (пользовательские свойства) позволяют задавать значения, которые можно переиспользовать в различных стилях. Они определяются с помощью двойного тире (`--`) и могут быть использованы с функцией `var()`.

### Определение переменных

Переменные можно определить в любом селекторе, но обычно их определяют в корневом селекторе `:root` для глобального применения.

#### Пример

```css
:root {
    --main-color: #3498db;
    --secondary-color: #2ecc71;
    --font-size: 16px;
}
```
Использование переменных
Переменные могут быть использованы в любом свойстве с помощью функции var().

Пример
```css
body {
    color: var(--main-color);
    font-size: var(--font-size);
}

h1 {
    color: var(--secondary-color);
}
```
Переопределение переменных
Переменные наследуются потомками, но могут быть переопределены в любом селекторе.

Пример
```css
Copy code
:root {
    --main-color: #3498db;
}

.section {
    --main-color: #e74c3c;
    color: var(--main-color);
}

.article {
    color: var(--main-color); /* Будет использовать цвет из :root, если не является потомком .section */
}
```

## Примеры синтаксиса CSS

```css
/* Числовые значения с единицами измерения */
width: 200px;
font-size: 1.5em;
margin: 1rem;
height: 50vh;

/* Процентные значения */
width: 50%;
padding: 10%;

/* Ключевые слова */
display: flex;
text-align: center;

/* Цветовые значения */
color: #333;

/* Функции */
background-image: url('image.jpg');
transform: translateX(50px);
width: calc(100% - 50px);
background-color: rgb(255, 0, 0);
border-color: rgba(255, 0, 0, 0.5);
color: hsl(0, 100%, 50%);
color: hsla(0, 100%, 50%, 0.5);

/* Краткие значения */
border: 1px solid #000;
margin: 10px 20px 30px 40px;
```