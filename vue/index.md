# Vue.js

[Website](https://vuejs.org/)

* Vue можно подключать как библиотеку

```html
<!-- development version, includes helpful console warnings -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

<!-- production version, optimized for size and speed -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

```javascript
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!',
    seen: true,
    items = ['item1', 'item2', 'item3']
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
});
```

```html
<div id="app">
  {{ message }}
  <span v-if="seen">Now you see me</span>
  <div v-for="item in items">
    {{ item }}
  </div>
  <button v-on:click="reverseMessage">Reverse Message</button>
</div>
```