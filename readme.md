# DevLabs Code Conventions

Да. Всеки добър екип има вътрешни стандарти за писане на код.

Крайно време е да се синхронизираме и да направим тази крачка, заедно.

Такива стандарти вкарват подредба в нещата. Знаете, при работа в екип, липса на стандарти на писане може да направи кода трудно четим, грозен и гнусен. Време е да контролираме кода, който създаваме като екип. Време е да имаме стандарти и най-важното: време е да следим за спазването им.

Старт.

<img src="http://i1.kym-cdn.com/photos/images/original/000/519/011/3f9.png" width="790" />

## Конвенции & Правила
- [Към HTML DevConventions!](html.md)
- [Към STYLE DevConventions!](style.md)
- [Към JavaScript DevConventions!](javascript.md)
- [Към Git DevConventions!](git.md)

## Основни настройки на Code Editor-а
- 4 space-чета за indentation
- "indentation using spaces", а не "using tabs".
- Line endings: Unix
- без trailing whitespace-чета! Sublime 2 / Sublime 3 [плъгин който показва/трие trailing whitespace-чета](http://github.com/SublimeText/TrailingSpaces) в кода

## Sublime плъгини, които enforce-ват конвенциите
Ако ви е трудно да спазвате правилата, може да си сложите плъгин който да ви "пищи" когато не спазвате конвенциите. Сложете си [SublimeLinter](http://sublimelinter.readthedocs.org/en/latest/) и след това:
- за HTML конвенциите (**undefined**)
- за JavaScript конвенциите инсталирайте [SublimeLinter JShint](https://github.com/SublimeLinter/SublimeLinter-jshint) и след това сложете в проекта си в папката със скриптовете [конфигурационен файл .jshintrc](https://github.com/superKalo/front-end-starter-template/blob/master/js/.jshintrc), който съдържа правилата от нашите конвенции
- за STYLE/SASS конвенциите инсталирайте [Sublime​Linter contrib-scss-lint](https://packagecontrol.io/packages/SublimeLinter-contrib-scss-lint) и след това сложете в проекта си в папката със стиловете [конфигурационен файл .scss-lint.yml](https://github.com/superKalo/front-end-starter-template/blob/master/styles/.scss-lint.yml), който съдържа правилата от нашите конвенции