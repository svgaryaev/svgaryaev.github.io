# Flex

В понятии flex есть контейнер (flex container), а есть элементы (flex items) (или элементы не лучший перевод?).

### display
Сделать флексовый контейнер

```css
.container {
  display: flex; /* or inline-flex */
}
```

### flex-direction

Задать направление для элементов (?)

```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
row (default): left to right in ltr; right to left in rtl
row-reverse: right to left in ltr; left to right in rtl
column: same as row but top to bottom
column-reverse: same as row-reverse but bottom to top
```

### flex-wrap

По умолчанию элементы (?) выстраиваются в одну линию

```css
.container{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
nowrap (default): all flex items will be on one line
wrap: flex items will wrap onto multiple lines, from top to bottom.
wrap-reverse: flex items will wrap onto multiple lines from bottom to top.
```

### flex-flow

Сочетание предыдущих двух свойств. По умолчанию стоит `row nowrap`.

```css
flex-flow: <‘flex-direction’> || <‘flex-wrap’>
```

### flex-grow

Определяет возможности роста при необходимости. Принимает неотрицательное число без единиц измерения, которое означает пропорцию от контейнера.

Так, если у всех элементов (?) `flex-grow` установлен в единицу, то все они займут одинаковое место. Елси у одного `flex-grow: 2`, то оставшее место блоки займут пропорционально.

```css
.item {
  flex-grow: <number>; /* default 0 */
  /* Negative numbers are invalid. */
}
```

### flex-shrink

Аналогично на сжимаемость элементов (?).

```css
.item {
  flex-shrink: <number>; /* default 1 */
  /* Negative numbers are invalid. */
}
```

### flex-basis

Дефолтный размер элемента (?), когда больше нет свободного места. Может принимать значение в процентах, px и т.д. или `keyword`, например `auto` или `content`.

```css
.item {
  flex-basis: <length> | auto; /* default auto */
}
```

### flex

Объединение предыдущих трех свойств. Рекомендуется к использованию.

```css
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

[CSS-TRICKS complete guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)