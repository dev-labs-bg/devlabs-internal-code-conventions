#SASS Conventions and rules:

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
- Основният style.scss трябва да съдържа са импорти, които да са в следната последователност:
  - modules
  - componenets
  - layouts
  - pages
  - vendors
- папката modules трябва да съдържа само uncompiled код. Uncompiled code е код, който не може да съществува самостоятелно т.н. трябва да бъде наследен от някой селектор за да бъде компилиран, в противен случай се игнорира от SASS
- template.scss файла трябва да съдържа само silent ( "тихи" ) класове, като всеки от тях трябва да представлява template. Под template се разбира основната структура на class-a, включваща стил както за родителя, така и за всички нейни child елементи.
- промениливите за проекта трябва да се съръждат само във _variables.scss
- base.scss файла трябва да съдържа код без никаква конктретика

###Подходящи имена на променливи
Избирайте подходящи имена за Вашите промениливи

Избягвайте да кръщавате променливите с директните им свойства:
```css
$red-button: #ff000;
```
Желателно е да ги кръщавате спрямо към какво се отнасят
```css
$primary-color: #333;
$base-font-family: Helvetica, Arial, sans-serif !default;
```
###Последователност
Последователността на свойствата е изключително важен фактор, особено когато нов член към екипа чете кода ни:
- $variables;
- @extends;
- @includes;
- свойства на елемента;
- действие към елемента;
- комбинация с други класове;
- комбинация с други елементи;
Оставяйте по един свободен ред между отделните типове.

```css
.element {
    $bg-color: #D90000;

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
adjective-noun {}  // example: .dropdown-button
```

От тип modifiers - когато винаги са прилагателни:
```css
.is-state {}        // state: is-selected, is-hidden
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