#CSS Conventions and rules:

###Protocols
По възможност пропускайте протоколната част ( HTTP:, HTTPS: ) при инклудването на мултимедийни файлове

Грешно:
```css
.example {
  background: url(http://www.google.com/images/example);
}
```
Правилно:
```css
.example {
  background: url(//www.google.com/images/example);
}
```

###Пишете коментари
Коментарите са изключително важна част от Вашият код - НЕ ги забравяйте. Грешна практика е да НЕ се пишат коментари за да се спести от големината на файла (за тази цел си има минифициране). Направете Вашият код четлив и разбираем, а не Вашият колега да "гадае" какво се случва.

```css
/* Lorem Ipsum is simply dummy text */
.white-color {
    color: #fff;
}
```

Понякога коменарите може да са прекалено дълги и се налага да се разбият на няколко реда:
```css
/**
 * Lorem Ipsum is simply dummy text
 * of the printing and typesetting industry.
 */
```

Ако е нужно да поставяте някъде TODO коментар, то правилния начин за изписването му е следният:
```css
/**
 * TODO: This is a todo statement that describes an atomic task to be completed
 *   at a later date. It wraps after 80 characters and following lines are
 *   indented by 2 spaces.
 */
```

###Как да използваме кавичките
Използвайте единични (' ') кавички, когато се налага да обградите атрибут селектори

Грешно:
```html
@import url("//www.google.com/css/maia.css");

html {
  font-family: "open sans", arial, sans-serif;
}
```

Правилно:
```html
@import url(//www.google.com/css/maia.css);

html {
  font-family: 'open sans', arial, sans-serif;
}
```

###Използвайте Shorthand свойства
CSS предоставя възможност за изписване на по-кратък начин на някои свойства - използвайте ги при възможност.

Грешно:
```css
border-top-style: none;
background-color: #e5e5e5;
background-image: url(http://www.vzonata.com/wp-content/themes/twentyeleven/images/bg.jpg);
background-repeat: repeat;
background-position: left center;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```

Правилно:
```css
border-top-style: none;
background: url(http://www.vzonata.com/wp-content/themes/twentyeleven/images/bg.jpg) no-repeat left center #e5e5e5;
padding: 0 1em 2em;
```

###Не използвайте единици след стойност "0"
Правилно:
```css
margin: 0;
padding: 0 1em 2em;
```

###Не използвайте "водеща" нула за стойност
Не използвайте "0"-та за стойности, който се намират между интервала -1 и 1.

Грешно:
```css
font-size: 0.8em;
```

Правилно:
```css
font-size: .8em;
```
###Поставяйте интервал между селектора и деклариращият блок
Винаги поставяйте по един празен интервал между селектора и деклариращият блок. Никога не ги разделяйте на редове:

Грешно:
```css
.video{
    margin-top: 1em;
}

.video
{
    margin-top: 1em;
}
```

Правилно:
```css
.video {
    margin-top: 1em;
}
```

###Поставяйте интервал между свойствата и съответната стойност

Грешно:
```css
.example {
    color:blue;
}
```

Правилно:
```css
.example {
    color: blue;
}
```

###Винаги започвайте всеки селектор на нов ред

Грешно:
```css
a:focus, a:active {
    position: relative; top: 1px;
}
```

Правилно:
```css
h1,
h2,
h3 {
    font-weight: normal;
    line-height: 1.2;
}
```

#SASS Conventions and rules:

###Полезно връзки
- Как да си инсталираме SASS: http://sass-lang.com/install
- Документация на SASS: http://sass-lang.com/documentation/file.SASS_REFERENCE.html

###Directory Structure
Спазвайте правилна структура на Вашите папки. Разбийте style кода си на модули и ги разпределете в правилните директории:

```html
sass/
|
|– modules/              # all uncompiled css code
|   |– _fonts.scss       # Fonts
|   |– _mixins.scss      # Mixins
|   |– _templates.scss   # Templates
|   |– _colors.scss      # Colors
|   |– _variables.scss   # Variables
|   ...                  # Etc…
|
|– components/
|   |– _base.scss        # Base style
|   |– _forms.scss       # Forms and form elements
|   |– _buttons.scss     # Buttons
|   |– _slider.scss      # Slider
|   |– _nagivation.scss  # Navigation
|   ...                  # Etc…
|
|– layouts/
|   |– _grid.scss        # Grid system
|   |– _header.scss      # Header
|   |– _footer.scss      # Footer
|   |– _sidebar.scss     # Sidebar
|   ...                  # Etc…
|
|– pages/
|   |– _home.scss        # Home specific styles
|   |– _contact.scss     # Contact specific styles
|   ...                  # Etc…
|
|– vendors/              # All plugins
|   |– _bootstrap.scss   # Bootstrap
|   |– _jquery-ui.scss   # jQuery UI
|   |– _datepicker.scss  # Datepicker
|   ...                  # Etc…
|
|
`– style.scss             # Main SASS file
```

###Правила
- Основният style.scss трябва да съдържа само импорти в примерна последователност на директориите:
  - modules
  - componenets
  - layouts
  - pages
  - vendors
- по възможност в template.scss файла съръжайте само silent ( "тихи" ) класове. Под template се разбира основната структура на class-a, включваща стил както за родителя, така и за всички нейни child елементи.
- промениливите за проекта трябва да се сърържат само във _variables.scss
- base.scss файла трябва да съдържа код без никаква конктретика

###Подходящи имена на променливи
Избирайте подходящи имена за Вашите промениливи

Избягвайте да кръщавате променливите с директните им свойства:
```css
$red-button: #ff000;
```
Желателно е да ги кръщавате спрямо към какво се отнасят
```css
$primary-color: #ff000;
$base-font-family: Helvetica, Arial, sans-serif !default;
```
###Последователност
Последователността на свойствата е изключително важен фактор, особено когато нов член към екипа чете кода ни:
- @extends;
- @includes;
- свойства на елемента;
- действие към елемента;
- комбинация с други класове;
- комбинация с други елементи;

```css
.element {
    @extend .rounded-border;
    @include data-module;
    cursor: pointer;
    height: 300px;
    margin: 0 auto;
    padding: 0;
    width: 400px;
    &:hover {
        text-decoration: underline;
    }
    &.active {
        color: #fff;
    }
    & > li {
        margin: 10px;
    }
    & + ul {
        margin-left: 10px;
    }
}
```
###Как да кръщаваме имената на елементите спрямо съществително или прилагателно
Когато четем един SASS код е хубаво да имаме ясна представа за структурата на HTML елементите и в какво състояние са те:

От тип object - традиционно използваните елементи:
```css
.noun {}            // examples: .button, .menu, .textbox, .header
```

От тип parent-child - когато има връзка между елементите и също е съществително:
```css
.noun {}            // parent: .post
.noun-noun {}       // child:  .post-title
```

От тип subclasses - когато елемента е превъзхождан от прилагателно:
```css
.adjective-noun {}  // example: .dropdown-button
```

От тип modifiers - когато винаги са прилагателни:
```css
.is-state {}        // state: .is-selected, .is-hidden
.adjective {}       // examples: .left, .right, .block, .inline
```

###Стъпаловидна структура

Бъдете внимателни със вашите нива на стъпаловидност. Препоръчителното максимално ниво е до 3 нива навътре:
```css
.weather {
    .cities {
        li {
            // no more!
        }
    }
}
```
Препоръчителни максималните редове на Вашата стъпаловидна структура са до 50 реда. Ако Вашият SASS block код превиши 50 реда има голяма вероятност да не събере на Вашият editor screen и да се превърне в труден за четене. Прегледайте си кода, може да използвате @import или @mixins, а проверихте ли Naming конвенциите.

###Използвайте SourceMapping
Не забравяйте да добавите опцията за SourceMapping когато конвентирате кода от sass към css. Той ви помага да намерите всяко едно property от inspect elementa, в кой от всичките инклуднати SASS файловете се намира и на кой ред.