[![en-lang](https://img.shields.io/badge/lang-en-yellowgreen.svg)](README.md)

# Gulppack
Gulppack - сборка для автоматизации задач в повседневной front-end разработке. Компилируйте SCSS/Sass, сжимайте файлы, оптимизируйте картинки. При каждом сохранении файла в редакторе кода браузер автоматически перезагружает страницу. Не волнуйтесь о том, что вам придётся выполнять рутинную работу.

## Что включает в себя сборка?
* [browser-sync](https://browsersync.io/docs/gulp) - живая перезагрузка веб-страницы при внесении изменений в файлы вашего проекта. Одна из опций — tunnel, которая выдаёт вам ссылку, чтобы любой желающий смог посмотреть вашу работу (в обход хостинга);
* [gulp-autoprefixer](https://www.npmjs.com/package/gulp-autoprefixer) — автоматически расставляет вендорные префиксы в CSS в соответствии с сервисом Can I Use;
* [gulp-uglify](https://www.npmjs.com/package/gulp-uglify) — минификация js-файлов;
* [gulp-sass](https://www.npmjs.com/package/gulp-sass) — компиляция Sass/SCSS в CSS;
* [gulp-clean-css](https://www.npmjs.com/package/gulp-clean-css) — минификация CSS-файлов;
* [gulp-concat](https://www.npmjs.com/package/gulp-concat) — объединение файлов;
* [gulp-rename](https://www.npmjs.com/package/gulp-rename) — переименование файлов, добавление суффиксов и префиксов (например, добавление суффикса .min к минифицированным файлам);
* [gulp-svgo](https://www.npmjs.com/package/gulp-svgo) — оптимизация векторной графики SVG;
* [gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin) — сжатие изображений PNG, JPG, GIF и SVG;
* [imagemin-pngquant](https://www.npmjs.com/package/imagemin-pngquant) — дополнение к gulp-imagemin для работы с PNG-изображениями;
* [imagemin-jpeg-recompress](https://www.npmjs.com/package/imagemin-jpeg-recompress) — дополнение к gulp-imagemin для работы с JPG-изображениями;
* [gulp-favicons](https://github.com/evilebottnawi/favicons) — генератор фавиконок для вашего проекта;
* [gulp-svg-symbols](https://github.com/Hiswe/gulp-svg-symbols) - создание SVG-спрайтов;
* [gulp-replace](https://www.npmjs.com/package/gulp-replace) - плагин для замены символов;
* [gulp-plumber](https://www.npmjs.com/package/gulp-plumber) — оповещения в командной строке (например, ошибки в Sass/SCSS);
* [ngrok](https://www.npmjs.com/package/ngrok) — предоставление доступа к локальному серверу (аналог tunnel в browser-sync. Предпочтительно для работы в ОС Windows, если будут проблемы с browser-sync);
* [gulp-newer](https://www.npmjs.com/package/gulp-newer) — кэширование;
* [gulp-debug](https://www.npmjs.com/package/gulp-debug) — отладка в терминале;
* [gulp-rimraf](https://github.com/robrich/gulp-rimraf) — очистка папок, удаление файлов;
* [gulp-watch](https://www.npmjs.com/package/gulp-watch) — отслеживание изменений в ваших файлах проекта.

## Как пользоваться?

* Установите [NodeJS](https://nodejs.org/en/).

> NodeJS — это серверная платформа для работы с JavaScript через движок V8. JavaScript выполняет действие на стороне клиента, а Node — на сервере. С помощью Node можно писать полноценные приложения. Node умеет работать с внешними библиотеками, вызывать команды из кода на JavaScript и выполнять роль веб-сервера.

Далее, используя Powershell в Windows или Терминал Linux/macOS, проделайте следующие шаги: 

* установите gulp глобально: ```npm install --global gulp-cli```;
* перейдите в скачанную папку со сборкой: ```cd gulppack```;
* введите команду, которая скачает необходимые компоненты для корректной работы нашей сборки, указанные в файле ```package.json``` (либо если у вас установлен ```git``` в Windows, просто откройте файл ```npm.sh```. Для Linux/macOS — перетащите ```npm.sh``` в Терминал и нажмите Enter): ```npm install --save-dev --save-exact```;
* введите последнюю команду: ```gulp```.

Если вы всё сделали правильно, у вас должен открыться браузер с локальным сервером и работающим browser-sync. Теперь если вы внесёте изменения в файлы ```.html```, ```.sass```, ```.js```, браузер сам перезагрузит веб-страницу, а Gulp заново соберёт ваш проект в папке ```dest```. 

## Если нужна работа с SCSS
Откройте файл ```gulpfile.js``` в папке со сборкой, найдите следующую строчку 
```javascript 
styles: { src: "src/styles/**/*.sass", dest: "dest/styles/" } 
```

и измените её:
```javascript 
styles: { src: "src/styles/**/*.scss", dest: "dest/styles/" }
```

## Если в Windows возникает ошибка с тем, что команда gulp не найдена
Модули ```npm```, такие как ```gulp```, не установлены в путях. Таким образом они не обнаруживаются при их запуске в командной строке.
* Компьютер — Свойства — Защита системы — Дополнительно — Переменные среды;
* В разделе Переменные среды выберите переменную среды PATH. Нажмите Изменить. Если переменной PATH не существует, нажмите Создать;
* в имени переменной укажите NODE_PATH;
* в значении переменной укажите %AppData%\npm или %AppData%\npm\node_modules;
* закройте командную строку и попробуйте ещё раз.

![Добавление переменных сред](https://pp.userapi.com/c834403/v834403892/c00bd/DgYTcUMrEoA.jpg).
