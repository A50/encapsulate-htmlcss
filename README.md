# gulp-encapsulate-htmlcss
С помощью этого плагина мы можем реализовать инкапсуляцию стилей, путем разделения каждого элемента макета на компоненты.
Каждый компонент должен находится в своем каталоге. Имя каталога является именем компонента и используется в качестве префикса генерируемого атрибута. Все компоненты, должны лежать в каталоге components. 
В каждом компоненте должен лежать файл html и css, если есть какая-то логика, то, там же следует разместить js файл. 
Каждый компонент должен иметь свой тег. Желательно, чтобы в теге был дефис, например:
```html
 <my-component></my-component>  
```
Инкапсуляция стилей достигается за счет добавления уникального атрибута к тегу и к стилю в css файле. 

Пример использования:

```javascript
'use strict';

const gulp = require('gulp');
// Подключаем плагин
const encapsulateHtmlCss = require("gulp-encapsulate-htmlcss");
// Добавляем уникальный атрибут файлам, которые лежат в каталоге компонента
gulp.task('encapsulate', () => {

    return gulp.src(['./src/components/*/*.*'])
        .pipe(encapsulateHtmlCss())
        .pipe(gulp.dest('./build/components'))
});


```
Пример проекта:
['https://github.com/A50/encapsulateHtmlCss'](https://github.com/A50/encapsulateHtmlCss)