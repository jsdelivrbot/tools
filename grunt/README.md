<img src="https://gruntjs.com/img/grunt-logo.svg" width="200" alt="Grunt">

## Установка

Для использования Гранта вам понадобится установить [Node.js](http://nodejs.org/). Вместе с Нодой установится менеджер пакетов `npm`, который понадобится для установки самого Гранта и его плагинов.

*Если вы уже пользуетесь предыдущей версией Гранта, то перед установкой новой версии старую нужно удалить: npm uninstall -g grunt.*

Установим [консольную утилиту grunt](https://github.com/gruntjs/grunt-cli/), которая будет запускать Грант, установленный в папке вашего проекта (ключ `-g` означает, что пакет будет установлен глобально). Таким образом у каждого проекта будут свои версии Гранта и плагинов — можно не бояться, что при обновлении сборка поломается.

```bash
$ npm install grunt-cli -g
```

## Настройка

Теперь нужно создать в корневой папке проекта два файла:

- package.json — описание проекта для npm. Содержит список зависимостей (в нашем случае это Грант и его плагины) и позволяет потом устанавливать их все одной командой.

- Gruntfile.js — файл конфигурации Гранта (грантфайл). (До версии 0.4 этот файл назывался grunt.js.)

### package.json

Этот файл можно создать вручную или с помощью команды `npm init`. В нём есть два обязательных поля — имя проекта и версия. Если вы делаете сайт, а не библиотеку, то их содержимое не имеет значения. Остальные поля можно не задавать.

```json
{
    "name": "MyProject",
    "version": "0.1.0"
}
```

Теперь нужно установить (и добавить в package.json) зависимости нашего проекта. Устанавливаем [Грант](https://github.com/gruntjs/grunt/):

```bash
$ npm install grunt --save-dev
```

И все необходимые плагины:

```bash
$ npm install grunt-contrib-concat grunt-contrib-uglify --save-dev
```

Ключ `--save-dev` в дополнение к установке добавляет ссылку на пакет в package.json. После установки плагинов файл package.json будет выглядеть [примерно так](http://gruntjs.com/getting-started#package.json).

Установить все зависимости, уже перечисленные в файле, можно командой `npm install`.

### Gruntfile.js

Грантфайл имеет следующий синтаксис:

```javascript
// Обязательная обёртка
module.exports = function(grunt) {

    // Конфигурация
    grunt.initConfig({
        concat: {
            // Настройка плагина concat
        },
        uglify: {
            // Настройка плагина uglify
        }
    });

    // Загрузка плагинов, установленных с помощью npm install
    grunt.loadNpmTasks('grunt-contrib-concat');
    grunt.loadNpmTasks('grunt-contrib-uglify');

    // Задача по умолчанию
    grunt.registerTask('default', ['concat', 'uglify']);
};
```

Обратите внимание на задачу по умолчанию default — это просто «ссылка» на задачи concat и uglify. Она обязательно должна быть в грантфайле.

[Пример](http://gruntjs.com/getting-started#an-example-gruntfile) Gruntfile.js с плагином uglify.

## Запуск

```bash
$ grunt  # Задача default
$ grunt concat  # Задача concat
$ grunt concat:main  # Подзадача concat:main

$ grunt --debug
```

Во время разработки удобно запускать Грант с ключом `--debug`. Задачи могут использовать его по-разному. Например, [grunt-contrib-stylus](https://github.com/gruntjs/grunt-contrib-stylus) в отладочном режиме не сжимает CSS-код.

## Плагины

Плагины из коллекции contrib (поддерживаются разработчиками Гранта):
- [concat](https://github.com/gruntjs/grunt-contrib-concat) — склеивание файлов;
- [uglify](https://github.com/gruntjs/grunt-contrib-uglify) — минификация JS (UglifyJS);
- [jshint](https://github.com/gruntjs/grunt-contrib-jshint) — проверка JS (JSHint);
- [watch](https://github.com/gruntjs/grunt-contrib-watch) — отслеживание изменений в файлах;
- [connect](https://github.com/gruntjs/grunt-contrib-connect) — простой веб-сервер для статики;
- [imagemin](https://github.com/gruntjs/grunt-contrib-imagemin) — оптимизация картинок;
- CSS-препроцессоры: [sass](https://github.com/gruntjs/grunt-contrib-sass), [less](https://github.com/gruntjs/grunt-contrib-less), [stylus](https://github.com/gruntjs/grunt-contrib-stylus);
- тестовые фреймворки: [qunit](https://github.com/gruntjs/grunt-contrib-qunit), [jasmine](https://github.com/gruntjs/grunt-contrib-jasmine).

Полный список плагинов можно найти на [gruntjs.com](http://gruntjs.com/).