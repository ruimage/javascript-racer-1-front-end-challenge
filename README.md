# Javascript Racer 1 Front End

## Компетенции

* Работа с EventListener
* Изменение DOM на основе событий
* Написание чистого объектно-ориентированного кода на JS

## Введение

Давайте напишем веб-версию гонок с использованием всех знаний которые у нас есть на текущем этапе. В этой части задания мы будем писать только клиентскую часть, без бекэнда. В этой версии будет побеждать не тот гонщик, которому просто повезло, а тот, кто быстрее нажимает на кнопку.
Например, можем закрепить за 1-ым гонщиком кнопку "q", а за вторым "p". По нажатию на одну из этих кнопок соответствующий игрок должен передвигатья на одну клетку вперёд. И таким образом 2 игрока могут соревноваться в гонках.
Цель задания - попрактиковаться в работе с асинхронной обработкой событий.


## Releases

### Release 0: Подготовка

В этом задании нет готового скелета. Поэтому вам придется самостоятельно писать HTML, CSS, JS и соединять все вместе. Первое что надо сделать - создать поле для гонок. Есть много вариантов как подойти к решению данного вопроса. Например, вы можете создать таблицу:


```html
<table class="racer_table">
  <tr id="player1_strip">
    <td></td>
    <td class="active"></td>
    <td></td>
    <td></td>
    ... etc ...
  </tr>
  <tr id="player2_strip">
    <td></td>
    <td></td>
    <td></td>
    <td class="active"></td>
    ... etc ...
  </tr>
</table>
```

И дополнить ее стилями:

```css
.racer_table td {
  background-color: white;
  height: 20px;
  width: 20px;
}

.racer_table td.active {
  background-color: black;
}
```

Обновление позиции игрока можно сделать добавлением класса `active` к нужной ячейке таблицы `td`. Но это лишь один из вариантов реализации - вы можете использовать свой, это было бы даже лучше.

Ознакомьтесь с [normalize.css][] - полезная библиотека, которая поможет вам обеспечить кроссбраузерность в изначальных стилях. Также вы можете поискать аналоги.


### Release 1: Добавим JavaScript

Теперь настало время написать код на JS. Наш код должен обновлять состояние нашего игрового поля. Необходима функция, которая будет обновлять позицию каждого игрока. На вход этой функции можем подавать текущую позицию игрока.

```javascript
updatePlayerPosition('player1', 10);
```

Если у вас возникают ошибки - пытайтесь решить их самостоятельно при помощи вывода в консоль "console.log", работы с дебаггером.


### Release 2: Привязка к нажатию на кнопку.

Теперь делаем игру интерактивной. Привяжите свою функцию на событие `keyup`. Ознакомьтесь и с другими событиями `keydown`, `keypress`. Почему лучше использовать keyup? [Документация по keyboard events][keyboard events]

Привязывать событие в данном случае лучше всего к `document`:

```javascript
document.addEventListener("DOMContentLoaded", function() {
  document.addEventListener("keyup", function(event) {
    // Detect which key was pressed and call the appropriate function
  });
});
```

### Release 3: Состояния игры

Нам нужно понимать когда игра началась, когда гонка закончена, чтобы можно было перезапустить игру и сыграть в нее еще раз. Добавьте состояния starting, playing, winning, restarting.



## Resources

* [normalize.css][]
* [Keyboard events][keyboard events]



[normalize.css]: https://github.com/necolas/normalize.css/
[keyboard events]: https://developer.mozilla.org/ru/docs/Web/API/KeyboardEvent
