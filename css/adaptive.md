# Адаптивная верстка

Адаптивная и резиновая верстка — это важные концепции в веб-разработке, позволяющие создавать сайты, которые корректно отображаются на разных устройствах и экранах. Вот подробный гайд по созданию адаптивной и резиновой верстки с использованием CSS.

### 1. Основные концепции

**Адаптивная верстка (responsive design)** — подход, при котором веб-страница меняет свой внешний вид в зависимости от размера экрана. Это достигается с помощью медиазапросов, которые применяют определенные стили при достижении заданных условий (ширина экрана, ориентация устройства и т.д.).

**Резиновая верстка (fluid design)** — подход, при котором элементы на странице изменяют свои размеры пропорционально размеру окна браузера. Это достигается использованием относительных единиц измерения, таких как проценты (%), em и rem.

### 2. Основные принципы адаптивной верстки

1. **Использование медиазапросов (media queries)**
2. **Относительные единицы измерения**
3. **Гибкие сетки (flexbox, grid)**
4. **Гибкие изображения и медиа-контент**

### 3. Пример адаптивной верстки

#### HTML
```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Адаптивная и резиновая верстка</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Адаптивная и резиновая верстка</h1>
        <nav>
            <ul>
                <li><a href="#home">Главная</a></li>
                <li><a href="#about">О нас</a></li>
                <li><a href="#services">Услуги</a></li>
                <li><a href="#contact">Контакты</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section id="home">
            <h2>Добро пожаловать!</h2>
            <p>Это пример адаптивной и резиновой верстки.</p>
        </section>
        <section id="about">
            <h2>О нас</h2>
            <p>Мы предоставляем лучшие услуги в своей сфере.</p>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 Все права защищены.</p>
    </footer>
</body>
</html>
```

#### CSS (styles.css)
```css
/* Основные стили */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    background-color: #333;
    color: #fff;
    padding: 10px 0;
}

header h1 {
    text-align: center;
    margin: 0;
}

nav ul {
    list-style: none;
    display: flex;
    justify-content: center;
    margin: 0;
    padding: 0;
}

nav ul li {
    margin: 0 15px;
}

nav ul li a {
    color: #fff;
    text-decoration: none;
}

main {
    padding: 20px;
}

footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 10px 0;
}

/* Адаптивные стили */
@media (max-width: 768px) {
    nav ul {
        flex-direction: column;
        align-items: center;
    }

    nav ul li {
        margin: 10px 0;
    }

    main {
        padding: 10px;
    }
}

@media (max-width: 480px) {
    header h1 {
        font-size: 1.5rem;
    }

    nav ul li {
        margin: 5px 0;
    }
}
```

### 4. Основные моменты

1. **Мета-тег viewport**: Обязателен для правильного масштабирования на мобильных устройствах.
    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```

2. **Использование относительных единиц измерения**: Проценты, em и rem обеспечивают гибкость элементов.
    ```css
    body {
        font-size: 16px;
    }

    h1 {
        font-size: 2rem; /* 2 * 16px = 32px */
    }
    ```

3. **Медиазапросы**: Позволяют изменять стили в зависимости от ширины экрана.
    ```css
    @media (max-width: 768px) {
        /* Стили для планшетов и мобильных устройств */
    }
    ```

4. **Flexbox и CSS Grid**: Используйте для создания гибких и адаптивных макетов.
    ```css
    nav ul {
        display: flex;
        justify-content: center;
    }

    @media (max-width: 768px) {
        nav ul {
            flex-direction: column;
        }
    }
    ```

### 5. Советы и рекомендации

- **Тестируйте на реальных устройствах**: Эмуляторы полезны, но реальные устройства дают более точное представление.
- **Начинайте с мобильной версии (mobile-first approach)**: Проще сначала сделать макет для мобильных устройств, а потом адаптировать его для больших экранов.
- **Используйте современные инструменты**: Flexbox и CSS Grid значительно упрощают создание адаптивных макетов.

Вот некоторые примеры медиа запросов в CSS:

1. **width** и **height**:
```css
@media (min-width: 600px) {
  body {
    font-size: 20px;
  }
}

@media (max-height: 800px) {
  nav {
    display: none;
  }
}
```
В первом примере, когда ширина окна браузера будет 600 пикселей или более, размер шрифта текста внутри тега `<body>` будет увеличен до 20 пикселей. Во втором примере, когда высота окна браузера будет 800 пикселей или менее, элемент навигации `<nav>` будет скрыт.

2. **device-width** и **device-height**:
```css
@media (device-width: 375px) {
  img {
    width: 100%;
  }
}

@media (max-device-height: 768px) {
  aside {
    display: none;
  }
}
```
В первом примере, когда ширина устройства будет равна 375 пикселям, изображения внутри тега `<img>` будут растянуты на всю ширину. Во втором примере, когда высота устройства будет 768 пикселей или менее, элемент `<aside>` будет скрыт.

3. **orientation**:
```css
@media (orientation: landscape) {
  section {
    display: flex;
  }
}

@media (orientation: portrait) {
  section {
    display: block;
  }
}
```
В первом примере, когда устройство будет в горизонтальной ориентации, элементы внутри тега `<section>` будут расположены в одну линию с помощью свойства `display: flex`. Во втором примере, когда устройство будет в вертикальной ориентации, элементы внутри тега `<section>` будут расположены в столбец с помощью свойства `display: block`.

4. **aspect-ratio**:
```css
@media (aspect-ratio: 16/9) {
  video {
    width: 100%;
  }
}
```
В этом примере, когда соотношение сторон окна браузера будет равно 16:9, видео внутри тега `<video>` будет растянуто на всю ширину.

5. **color**:
```css
@media (color: 8) {
  body {
    background-color: gray;
  }
}
```
В этом примере, когда устройство использует 8 битов на пиксель для отображения цвета, цвет фона тега `<body>` будет изменен на серый.

6. **color-index**:
```css
@media (color-index: 256) {
  img {
    display: none;
  }
}
```
В этом примере, когда цветовая палитра устройства содержит 256 цветов, изображения внутри тега `<img>` будут скрыты.