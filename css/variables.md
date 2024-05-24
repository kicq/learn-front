Конечно, давайте добавим информацию о CSS-переменных, которые позволяют упрощать управление стилями и создавать более гибкие и поддерживаемые CSS-правила.

### CSS-переменные

CSS-переменные (также известные как пользовательские свойства) позволяют задавать значения, которые можно переиспользовать в различных стилях. Они определяются с помощью двойного тире (`--`) и могут быть использованы с функцией `var()`.

### Определение переменных

Переменные можно определить в любом селекторе, но обычно их определяют в корневом селекторе `:root` для глобального применения.

#### Синтаксис

```css
:root {
    --main-color: #3498db;
    --secondary-color: #2ecc71;
    --font-size: 16px;
}
```

### Использование переменных

Переменные могут быть использованы в любом свойстве с помощью функции `var()`.

#### Синтаксис

```css
body {
    color: var(--main-color);
    font-size: var(--font-size);
}

h1 {
    color: var(--secondary-color);
}
```

### Пример использования

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Variables Example</title>
    <style>
        :root {
            --main-bg-color: #f0f0f0;
            --primary-color: #3498db;
            --secondary-color: #2ecc71;
            --font-size: 18px;
            --padding: 10px;
        }

        body {
            background-color: var(--main-bg-color);
            font-size: var(--font-size);
            padding: var(--padding);
        }

        .header {
            color: var(--primary-color);
        }

        .content {
            color: var(--secondary-color);
        }

        .box {
            border: 1px solid var(--primary-color);
            padding: var(--padding);
            background-color: var(--main-bg-color);
        }
    </style>
</head>
<body>
    <h1 class="header">Welcome to My Website</h1>
    <p class="content">This is a simple example of using CSS variables.</p>
    <div class="box">This box uses CSS variables for its styles.</div>
</body>
</html>
```

### Наследование и переопределение переменных

Переменные наследуются потомками, но могут быть переопределены в любом селекторе.

#### Пример переопределения

```css
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

### Использование переменных по умолчанию

Функция `var()` позволяет задавать значение по умолчанию, если переменная не определена.

#### Синтаксис

```css
.element {
    color: var(--undefined-variable, black); /* Использует черный цвет, если переменная не определена */
}
```

### Преимущества использования CSS-переменных

1. **Удобство управления стилями**: Легко менять значения переменных, что автоматически обновляет все связанные стили.
2. **Гибкость и модульность**: Переменные можно использовать в различных контекстах и переопределять по мере необходимости.
3. **Повышение читаемости кода**: Использование переменных делает CSS-код более понятным и поддерживаемым.

CSS-переменные являются мощным инструментом для создания гибких и поддерживаемых стилей, особенно в больших проектах.