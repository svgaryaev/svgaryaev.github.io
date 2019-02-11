# Angular

```js
export enum Foo {
  'first': 'FIRST',
  'second': 'SECOND'
}
Object.keys(Foo) // вернет список ключей
function Bar(xyz: keyof typeof Foo) { } // проверка этапа компиляции, т.е. переменная должна быть среди ключей Foo
function Bar(xyz: 'first' | 'second') { } // эквивалентно
```

```html
<div *ngFor="let name of names; let i = index">{{ i }} {{ name }}</div> <!-- индекс цикла -->
```