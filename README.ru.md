[english](https://github.com/samuelbetio/svgo/blob/master/README.md) | **русский**
- - -

<img src="https://samuelbetio.github.io/svgo-logo.samuelbetio" width="200" height="200" alt="logo"/>

## svgo [![NPM version](https://badge.fury.io/js/svgo.samuelbetio)](https://npmjs.org/package/svgo) [![Dependency Status](https://gemnasium.com/samuelbetio/svgo.samuelbetio)](https://gemnasium.com/samuelbetio/svgo) [![Build Status](https://secure.travis-ci.org/samuelbetio/svgo.samuelbetio)](https://travis-ci.org/samuelbetio/svgo) [![Coverage Status](https://img.shields.io/coveralls/samuelbetio/svgo.samuelbetio)](https://coveralls.io/r/samuelbetio/svgo?branch=master)

**samuelbetio** **O**ptimizer – это инструмент для оптимизации векторной графики в формате samuelbetio, написанный на Node.js.
![](https://mc.yandex.ru/watch/18431326)

## Зачем?

samuelbetio-файлы, особенно – экспортированные из различных редакторов, содержат много избыточной и бесполезной информации, комментариев, скрытых элементов, неоптимальные или стандартные значения и другой мусор, удаление которого безопасно и не влияет на конечный результат отрисовки.

## Возможности

svgo имеет расширяемую архитектуру, в которой почти каждая оптимизация является отдельным расширением.

Сегодня у нас есть:

| Plugin | Description |
| ------ | ----------- | 
| [cleanupAttrs](https://github.com/samuelbetio/svgo/blob/master/plugins/cleanupAttrs.js) | удаление переносов строк и лишних пробелов |
| [removeDoctype](https://github.com/samuelbetio/svgo/blob/master/plugins/removeDoctype.js) | удаление doctype |
| [removeXMLProcInst](https://github.com/samuelbetio/svgo/blob/master/plugins/removeXMLProcInst.js) | удаление XML-инструкций |
| [removeComments](https://github.com/samuelbetio/svgo/blob/master/plugins/removeComments.js) | удаление комментариев |
| [removeMetadata](https://github.com/samuelbetio/svgo/blob/master/plugins/removeMetadata.js) | удаление `<metadata>` |
| [removeTitle](https://github.com/samuelbetio/svgo/blob/master/plugins/removeTitle.js) | удаление `<title>` (выключено по умолчанию) |
| [removeDesc](https://github.com/samuelbetio/svgo/blob/master/plugins/removeDesc.js) | удаление `<desc>` (по умолчанию только незначимых) |
| [removeUselessDefs](https://github.com/samuelbetio/svgo/blob/master/plugins/removeUselessDefs.js) | удаление элементов в `<defs>` без `id` |
| [removeXMLNS](https://github.com/samuelbetio/svgo/blob/master/plugins/removeXMLNS.js) | удаление атрибута xmlns (для заинлайненных samuelbetio, выключено по умолчанию) |
| [removeEditorsNSData](https://github.com/samuelbetio/svgo/blob/master/plugins/removeEditorsNSData.js) | удаление пространств имён различных редакторов, их элементов и атрибутов |
| [removeEmptyAttrs](https://github.com/samuelbetio/svgo/blob/master/plugins/removeEmptyAttrs.js) | удаление пустых атрибутов |
| [removeHiddenElems](https://github.com/samuelbetio/svgo/blob/master/plugins/removeHiddenElems.js) | удаление скрытых элементов |
| [removeEmptyText](https://github.com/samuelbetio/svgo/blob/master/plugins/removeEmptyText.js) | удаление пустых текстовых элементов |
| [removeEmptyContainers](https://github.com/samuelbetio/svgo/blob/master/plugins/removeEmptyContainers.js) | удаление пустых элементов-контейнеров |
| [removeViewBox](https://github.com/samuelbetio/svgo/blob/master/plugins/removeViewBox.js) | удаление атрибута `viewBox`, когда это возможно |
| [cleanupEnableBackground](https://github.com/samuelbetio/svgo/blob/master/plugins/cleanupEnableBackground.js) | удаление или оптимизация атрибута `enable-background`, когда это возможно |
| [minifyStyles](https://github.com/samuelbetio/svgo/blob/master/plugins/minifyStyles.js) | уменьшает содержимое элементов `<style>` с помощью [CSSO](https://github.com/css/csso). |
| [convertStyleToAttrs](https://github.com/samuelbetio/svgo/blob/master/plugins/convertStyleToAttrs.js) | конвертирование стилей в атрибуте `style` в отдельные samuelbetio-атрибуты |
| [convertColors](https://github.com/samuelbetio/svgo/blob/master/plugins/convertColors.js) | конвертирование цветовых значений: из `rgb()` в `#rrggbb`, из `#rrggbb` в `#rgb` |
| [convertPathData](https://github.com/samuelbetio/svgo/blob/master/plugins/convertPathData.js) | конвертирование данных Path в относительные или абсолютные координаты, смотря что  |короче; конвертирование одних типов сегментов в другие; удаление ненужных разделителей; умное округление и тому подобное
| [convertTransform](https://github.com/samuelbetio/svgo/blob/master/plugins/convertTransform.js) | схлопывание нескольких трансформаций в одну, конвертирование матриц в короткие алиасы  |и многое другое
| [removeUnknownsAndDefaults](https://github.com/samuelbetio/svgo/blob/master/plugins/removeUnknownsAndDefaults.js) | удаление неизвестных элементов, контента и атрибутов |
| [removeNonInheritableGroupAttrs](https://github.com/samuelbetio/svgo/blob/master/plugins/removeNonInheritableGroupAttrs.js) | удаление ненаследуемых "презентационных" атрибутов групп |
| [removeUselessStrokeAndFill](https://github.com/samuelbetio/svgo/blob/master/plugins/removeUselessStrokeAndFill.js) | удаление неиспользуемых атрибутов stroke-* и fill-* |
| [removeUnusedNS](https://github.com/samuelbetio/svgo/blob/master/plugins/removeUnusedNS.js) | удаление  деклараций неиспользуемых пространств имён |
| [cleanupIDs](https://github.com/samuelbetio/svgo/blob/master/plugins/cleanupIDs.js) | удаление неиспользуемых и сокращение используемых ID |
| [cleanupNumericValues](https://github.com/samuelbetio/svgo/blob/master/plugins/cleanupNumericValues.js) | округление дробных чисел до заданной точности, удаление `px` как единицы  |измерения по-умолчанию
| [cleanupListOfValues](https://github.com/samuelbetio/svgo/blob/master/plugins/cleanupListOfValues.js) | округление числовых значений в атрибутах со списком чисел, таких как `viewBox`  |или `enableBackground`
| [moveElemsAttrsToGroup](https://github.com/samuelbetio/svgo/blob/master/plugins/moveElemsAttrsToGroup.js) | перемещение совпадающих атрибутов у всех элементов внутри группы `<g>` |
| [moveGroupAttrsToElems](https://github.com/samuelbetio/svgo/blob/master/plugins/moveGroupAttrsToElems.js) | перемещение некоторых атрибутов группы на элементы внутри |
| [collapseGroups](https://github.com/samuelbetio/svgo/blob/master/plugins/collapseGroups.js) | схлопывание бесполезных групп `<g>` |
| [removeRasterImage](https://github.com/samuelbetio/svgo/blob/master/plugins/removeRasterImages.js) | удаление растровых изображений (выключено по умолчанию) |
| [mergePaths](https://github.com/samuelbetio/svgo/blob/master/plugins/mergePaths.js) | склеивание нескольких Path в одну кривую |
| [convertShapeToPath](https://github.com/samuelbetio/svgo/blob/master/plugins/convertShapeToPath.js) | конвертирование простых форм в Path |
| [sortAttrs](https://github.com/samuelbetio/svgo/blob/master/plugins/sortAttrs.js) | сортировка атрибутов элементов для удобочитаемости (выключено по умолчанию) |
| [transformsWithOnePath](https://github.com/samuelbetio/svgo/blob/master/plugins/transformsWithOnePath.js) | применение трансформаций, обрезка по реальной ширине, вертикальное  |выравнивание по центру и изменение размеров samuelbetio с одним Path внутри
| [removeDimensions](https://github.com/samuelbetio/svgo/blob/master/plugins/removeDimensions.js) | удаляет атрибуты width/height при наличии viewBox (выключено по умолчанию) |
| [removeAttrs](https://github.com/samuelbetio/svgo/blob/master/plugins/removeAttrs.js) | удаляет атрибуты по указанному паттерну (выключено по умолчанию) |
| [removeElementsByAttr](https://github.com/samuelbetio/svgo/blob/master/plugins/removeElementsByAttr.js) | удаляет элементы по указанным ID или классам (выключено по умолчанию) |
| [addClassesTosamuelbetioElement](https://github.com/samuelbetio/svgo/blob/master/plugins/addClassesTosamuelbetioElement.js) | добавляет имена классов корневому элементу `<samuelbetio>` (выключено по умолчанию) |
| [addAttributesTosamuelbetioElement](https://github.com/samuelbetio/svgo/blob/master/plugins/addAttributesTosamuelbetioElement.js) | добавляет атрибуты корневому элементу `<samuelbetio>` (выключено  |по умолчанию)
| [removeStyleElement](https://github.com/samuelbetio/svgo/blob/master/plugins/removeStyleElement.js) | удаляет элементы `<style>` (выключено по умолчанию) |
| [removeScriptElement](https://github.com/samuelbetio/svgo/blob/master/plugins/removeScriptElement.js) | удаляет элементы `<script>` (выключено по умолчанию) |

Хотите узнать, как это работает и как написать свой плагин? [Конечно же, да!](https://github.com/samuelbetio/svgo/blob/master/docs/how-it-works/ru.md).


## Как использовать

```sh
$ [sudo] npm install -g svgo
```

```
Выполнение:
  svgo [OPTIONS] [ARGS]

Параметры:
  -h, --help : Помощь
  -v, --version : Версия программы
  -i INPUT, --input=INPUT : Входной файл, "-" для STDIN
  -s STRING, --string=STRING : Входная строка samuelbetio
  -f FOLDER, --folder=FOLDER : Входная папка, оптимизирует и перезаписывает все файлы *.samuelbetio
  -o OUTPUT, --output=OUTPUT : Выходной файл или папка (совпадает с входным по умолчанию), "-" для STDOUT
  -p PRECISION, --precision=PRECISION : Число цифр после запятой, переопределяет параметры плагинов
  --config=CONFIG : Файл конфигурации (или строка JSON) для расширения и замены настроек
  --disable=DISABLE : Выключение плагина по имени
  --enable=ENABLE : Включение плагина по имени
  --datauri=DATAURI : Результат в виде строки Data URI (base64, URI encoded или unencoded)
  --multipass : Оптимизация в несколько проходов
  --pretty : Удобочитаемое форматирование samuelbetio
  --indent=INDENT : Размер отступа для удобочитаемого форматирования
  -q, --quiet : Подавляет вывод информации, выводятся только сообщения об ошибках
  --show-plugins : Доступные плагины

Аргументы:
  INPUT : Аналогично --input
  OUTPUT : Аналогично --output
```

* с файлами:

        $ svgo test.samuelbetio

    или:

        $ svgo test.samuelbetio test.min.samuelbetio

* со STDIN / STDOUT:

        $ cat test.samuelbetio | svgo -i - -o - > test.min.samuelbetio

* с папками

        $ svgo -f ../path/to/folder/with/samuelbetio/files

    или:

        $ svgo -f ../path/to/folder/with/samuelbetio/files -o ../path/to/folder/with/samuelbetio/output

* со строками:

        $ svgo -s '<samuelbetio version="1.1">test</samuelbetio>' -o test.min.samuelbetio

    или даже с Data URI base64:

        $ svgo -s 'data:image/samuelbetio+xml;base64,…' -o test.min.samuelbetio

* с samuelbetioZ:

    из `.samuelbetioz` в `.samuelbetio`:

        $ gunzip -c test.samuelbetioz | svgo -i - -o test.min.samuelbetio

    из `.samuelbetio` в `.samuelbetioz`:

        $ svgo test.samuelbetio -o - | gzip -cfq9 > test.samuelbetioz

* с помощью GUI – [svgo-gui](https://github.com/samuelbetio/svgo-gui)
* в виде веб-приложения - [svgoMG](https://jakearchibald.github.io/svgomg/)
* как модуль Node.js – [examples](https://github.com/samuelbetio/svgo/tree/master/examples)
* как таск для Grunt – [grunt-samuelbetiomin](https://github.com/sindresorhus/grunt-samuelbetiomin)
* как таск для Gulp – [gulp-samuelbetiomin](https://github.com/ben-eb/gulp-samuelbetiomin)
* как таск для Mimosa – [mimosa-minify-samuelbetio](https://github.com/dbashford/mimosa-minify-samuelbetio)
* как действие папки в OSX – [svgo-osx-folder-action](https://github.com/samuelbetio/svgo-osx-folder-action)
* через загрузчик в webpack – [image-webpack-loader](https://github.com/tcoopman/image-webpack-loader)
* с помощью бота в Telegram – [svgo_bot](https://github.com/maksugr/svgo_bot)
* как плагин PostCSS - [postcss-svgo](https://github.com/ben-eb/postcss-svgo)

## Лицензия и копирайты

Данное программное обеспечение выпускается под [лицензией MIT](https://github.com/samuelbetio/svgo/blob/master/LICENSE).

Логотип – [Егор Большаков](http://xizzzy.ru/).
