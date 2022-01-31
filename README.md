# test

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

Задача

- сделать 3 вертикальные колонки (как бы экран поделить на 3 ровные части)

- слева нарисовать группу радио кнопок "все", "меньше 0", "больше или равно 0" (друг под другом), затем чекбокс (без сортировки/сортировка по сумме), т.е должно получиться всего 3 радио и 1 чекбокс

- в средней колонке список в котором отображаются записи из массива в строку, сам массив нужно сгенерировать со 100 объектами, каждый объект это  { id: 1, amount:  -950  }, свойство amount заполнить числом рандомно от -1000 до +1000, в саму строку так же нужно добавить чекбокс, что бы можно было выбрать запись

- справа показывать то что сейчас выбранно, целиком строчка как в средней части, так же не зависимо от переключения все, меньше 0, больше или равно 0 справа результат сохраняется и так же выбранные чекбоксы в средней колонке

стилей особо не нужно, разбить на кокмпоненты, без использования стор
