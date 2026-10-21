# CSS Упражнение на живо

> **Как работи:** Преподавателят отваря `index.html` + `css/style.css` едновременно с браузъра.
> Студентите диктуват какво да се напише. Ако никой не знае дадено свойство — търсим в MDN или Google.

---

## Фаза 1 — CSS Променливи

 1. Дефинирайте променливи в `:root`: `--primary-color`, `--card-padding`, `--font-size-base`.
 2. Заменете твърдо зададените стойности в целия файл с `var(--primary-color)` и т.н.
 3. Каква е синтаксисът за fallback стойност в `var()`? (напр. `var(--primary-color, blue)`)
 4. Добавете клас `.dark`, който презаписва `--primary-color` с тъмна стойност.
 5. Превключете класа в DevTools на `<body>` — наблюдавайте как темата на цялата страница се сменя мигновено.

---

## Фаза 2 — Селектори и цветове

1. Изберете `h1` по **таг** — задайте цвят и размер на шрифта.
2. Изберете `.card` по **клас** — задайте фонов цвят с hex стойност (`#...`).
3. Сменете фона на `rgba()` — какво е 4-тата стойност?
4. Изберете `#badge` по **ID** — задайте фонов цвят и padding.
5. Добавете правило `a:hover` — какъв тип селектор е `:hover`?
6. Добавете `li:nth-child(even)` към списъка `.skills` — задайте различен фон.
7. Комбинирайте селектори:
    - `header, footer` — стилизирайте и двата наведнъж (ИЛИ)
    - `.card.featured` — елемент с два класа едновременно (И)
    - `.card-nav a` — линкове вътре в навигацията (влагане/descendant)
8. **Специфичност:** Напишете два конфликтни `color` правила за `h2` — едно с таг селектор и едно с клас селектор. Кое побеждава? Защо?
    - Таг селектор = 0,0,0,1
    - Клас селектор = 0,0,1,0
    - ID селектор = 0,1,0,0
    - Inline стил = 1,0,0,0

---

## Фаза 3 — Типография

 1. Задайте `font-family` на `body` с fallback стек (напр. `Arial, Helvetica, sans-serif`). Защо са нужни fallback шрифтове?
 2. Задайте `font-size` в `px` на `p`. Сега го сменете на `rem`. Каква е разликата между `rem` и `em`?
 3. Направете `h2` удебелен с `font-weight` и наклонен с `font-style`.
 4. Премахнете подчертаването на линковете с `text-decoration`.
 5. Направете текста в `.site-header` с главни букви с `text-transform`.
 6. Задайте `line-height` на `p` — опитайте `1.5` (без мерна единица). Защо без единица?
 7. Добавете `letter-spacing` към заглавието в хедъра.
 8. Центрирайте текста в `.site-header` с `text-align`.
 9. **Псевдо-елемент:** Стилизирайте placeholder текста на `input` с `::placeholder`. Каква е разликата между `::` и `:`?

---

## Фаза 4 — Border, Border-Radius и Псевдо-елементи

 1. Добавете `border` на `.card` с shorthand. Кои са 3-те части? (`width style color`)
 2. Изпробвайте различни стилове на border: `solid`, `dashed`, `dotted`.
 3. Добавете `border-radius: 8px` на `.card` за заоблени ъгли.
 4. Направете `.avatar` изображението на кръг — кое `border-radius` трябва да използваме? Защо `50%` работи?
 5. Дайте на `#badge` `border-radius: 50%` — каква форма получаваме?
 6. Добавете само `border-bottom` на `.site-header`.
 7. **Псевдо-елемент `::after`:** Добавете задължителна звездичка след `.label` текста:

    ```css
    .label::after {
      content: " *";
      color: red;
    }
    ```

    Защо е удобно да го правим с CSS вместо директно в HTML?
 8. **Псевдо-елемент `::before`:** Добавете декоративен символ преди заглавията в `.box-model-demo`:

    ```css
    .box-model-demo h3::before {
      content: "▶ ";
      color: steelblue;
    }
    ```

---

## Фаза 5 — Box Model

 1. Дайте на `.card` ширина (`width`) и фонов цвят, за да го виждаме.
 2. Добавете `padding: 20px` — какво се случи с размера на картата?
 3. Защо картата стана по-голяма? Какво е `box-sizing: content-box` (по подразбиране)?
 4. Погледнете двата контейнера в `.box-model-demo` — и двата имат `width: 300px` и `padding: 30px`. Задайте на `.box-border` `box-sizing: border-box` и на `.content-box` `box-sizing: content-box`. Наблюдавайте разликата в размера.
 5. Добавете еднакъв `background-color` и на двата `.box` контейнера, за да се вижда разликата ясно.
 6. Поправете глобално: добавете `* { box-sizing: border-box; }` в началото на файла.
 7. Центрирайте картата на страницата с `margin: 0 auto`. Защо работи това?
 8. Добавете `margin-bottom` между елементите.
 9. Направете `.site-header` sticky: `position: sticky; top: 0;` — скролнете страницата, за да го тествате.

---

## Фаза 6 — Display и Flexbox

 1. Защо не можем да зададем `width` на `<a>` таговете в `.card-nav`? Какъв е техният display по подразбиране?
 2. Сменете линковете на `display: inline-block` и им дайте `padding`. Какво се промени?
 3. Добавете `display: none` на `.cookie-banner`. Отворете DevTools — елементът все още ли е в DOM?
 4. Сега опитайте `visibility: hidden` — каква е разликата?
 5. Направете `.card-nav` flex контейнер: `display: flex`.
 6. Центрирайте nav елементите хоризонтално — кое свойство използваме? (`justify-content`)
 7. Центрирайте ги вертикално — кое свойство? (`align-items`)
 8. Изпробвайте различни стойности за `justify-content`: `space-between`, `space-around`, `center`.
 9. Добавете `gap: 8px` между елементите.
10. Направете списъка с умения да се показва в ред с flexbox и `flex-wrap: wrap`.
11. Използвайте `order` на един flex елемент — преместете го напред.
12. Направете `.box-model-demo` flex контейнер и наредете двата `.box` елемента един до друг.

---

## Фаза 7 — Responsive Design

 1. Сменете `width` на картата от фиксирана `px` стойност на `90%` с `max-width: 400px`. Какво прави `max-width`?
 2. Какво е media query? Как се пише? Потърсете в MDN ако не знаете.
 3. Добавете `@media screen and (max-width: 600px) { }`.
 4. Вътре в media query-то: сменете `.card-nav` на `flex-direction: column`.
 5. Вътре в media query-то: намалете `font-size` на `body`.
 6. Вътре в media query-то: наредете `.box-model-demo` вертикално с `flex-direction: column`.
 7. **Live тест:** Свийте прозореца на браузъра — наблюдавайте как се променя оформлението.
 8. Каква е разликата между responsive и adaptive дизайн?

---

## Фаза 8 — Позициониране

 1. Кои са 5-те стойности на `position`? (static, relative, absolute, fixed, sticky)
 2. Позиционирайте `#badge` абсолютно: `position: absolute; top: -10px; right: -10px;`
 3. Защо badge-ът е на грешното място? Какво липсва на родителския елемент?
 4. Добавете `position: relative` на `.card` — badge-ът се наравнява на правилното място.
 5. Премахнете `position: relative` от `.card` — накъде отива badge-ът сега? Защо?
 6. Направете `.cookie-banner` фиксиран в долната част: `position: fixed; bottom: 0; left: 0; right: 0;`
 7. Каква е разликата между `fixed` и `sticky`?

---

## Фаза 9 — Преходи и Анимации

 1. Добавете `transition` на `.card` за `box-shadow`. Кои са 4-те стойности на `transition`? (property, duration, timing-function, delay) — потърсете в MDN ако не знаете.
 2. Добавете `box-shadow` на `.card:hover` — тествайте hover ефекта в браузъра.
 3. Изпробвайте различни timing functions: `ease`, `linear`, `ease-in-out`.
 4. Напишете `@keyframes pulse` анимация, която мащабира badge-а нагоре и надолу.

    ```css
    @keyframes pulse {
      from { transform: scale(1); }
      to   { transform: scale(1.15); }
    }
    ```
 5. Приложете я на `#badge`: `animation: pulse 0.8s ease-in-out infinite alternate;`
 6. Какво прави `alternate`? Какво прави `infinite`?
 7. Добавете `transition` на линковете за промяна на `color` при hover.

---

## Бонус задачи

- Добавете `linear-gradient` фон на `.site-header` вместо плътен цвят.
- Използвайте `:not()` за стилизиране на всички `.skills li` с изключение на първия.
- Създайте втора карта с клас `.card.featured` и презапишете CSS променливите вътре в нея.
- Добавете `@font-face` или Google Fonts `<link>` за custom шрифт.
