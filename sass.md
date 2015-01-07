#SASS Conventions:

###Directory Structure
Спазвайте правилна структура на Вашите папки. Разбийте style кода си на модули и ги разпределете в правилните директории:

```html
sass/ 
| 
|– components/ 
|   |– _fonts.scss       # Fonts
|   |– _buttons.scss     # Buttons
|   |– _carousel.scss    # Carousel
|   |– _dropdown.scss    # Dropdown 
|   |– _navigation.scss  # Navigation 
|   ...                  # Etc… 
| 
|– helpers/ 
|   |– _variables.scss   # Sass Variables 
|   |– _functions.scss   # Sass Functions 
|   |– _mixins.scss      # Sass Mixins 
|   |– _helpers.scss     # Class & placeholders helpers 
|   ...                  # Etc… 
| 
|– layout/ 
|   |– _grid.scss        # Grid system 
|   |– _header.scss      # Header 
|   |– _footer.scss      # Footer 
|   |– _sidebar.scss     # Sidebar 
|   |– _forms.scss       # Forms 
|   ...                  # Etc… 
| 
|– pages/ 
|   |– _home.scss        # Home specific styles 
|   |– _contact.scss     # Contact specific styles 
|   ...                  # Etc… 
| 
|– plugins/ 
|   |– _bootstrap.scss   # Bootstrap 
|   |– _jquery-ui.scss   # jQuery UI
|   |– _datepicker.scss  # Datepicker
|   ...                  # Etc… 
| 
| 
`– main.scss             # основният Sass файл 
```
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
        text-decoration:underline;
    }

    &.active {
        margin:10px;
    }

    & + ul {
        margin-left:10px;
    }
}
```

