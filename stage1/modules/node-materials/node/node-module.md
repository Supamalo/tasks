## Модули
Глобальных переменных вроде `__dirname`, `__filename`, `process.argv` в Node.js совсем немного. [Список глобальных объектов](https://js-node.ru/site/article?id=24).  
Большая часть функционала в Node.js доступна в виде модулей.  
Модули в Node.js были с самого начала, когда в браузерном JavaScript о них ещё даже не думали.  
Особенность модулей Node.js то, что вся информация доступна исключительно внутри модуля.  
Разработчик сам решает какую информацию экспортировать за пределы модуля.

Модули в Node.js бывают трёх типов.  
1. Стандартные модули, которые мы получаем устанавливая node на компьютер.  
Примеры стандартных модулей:
  - [модуль path](module/path.md)
  - [модуль fs](module/fs.md)
  - [модуль os](module/os.md)
2. [Модули, устанавливаемые через npm](module/npm-module.md)
3. [Модули, которые разработчик создаёт самостоятельно](module/create-module.md)

### Стандартные модули
Стандартные модули достаточно подключить и можно с ними работать.    
[Перечень стандартных модулей](https://nodejs.org/dist/latest-v14.x/docs/api/)  
Для подключения модуля используется функция `require()`  
Примеры подключения модулей:  
```js
const path = require('path');
const fs = require('fs');
const os = require('os');
```

### Модули, устанавливаемые через npm
Модули, устанавливаемые через npm, нужно сначала установить, затем подключить, затем использовать.  
Установка модуля осуществляется командой  
```npm install *имя модуля*```  

### Модули, которые разработчик создаёт самостоятельно
Создание модуля начинается с создания отдельного js-файла в котором пишем код. Экспорт осуществляется при помощи функции `module.exports`, импорт в другой файл, как и в случае стандартных модулей, при помощи функции `require()`, только в качестве аргумента вместо имени модуля указываем путь к файлу.

Работу с модулями в Node.js начнём с создания Node.js-приложения

### Создание Node.js-приложения
Создадим новый проект. Для этого создадим папку проекта, откроем её в VS Code и в терминале выполним команду  
```node init -y```  
Параметр `-y` (Yes) означает, что мы соглашаемся со всеми настройками проекта по умолчанию.  
В папке проекта появляется файл `package.json`, в котором описывается созданное приложение.

### Установка модулей через npm.
Установка модуля осуществляется командой  
```npm install *имя модуля*```  
Установим npm модуль nodemon. Для этого в терминале выполним команду  
```npm install nodemon```  
Удаление модуля:
```npm uninstall nodemon```  

Установленные модули добавляются в папку `node_modules`, а информация о них указывается в файле `package.json`.  
Если удалить папку `node_modules` и выполнить команду `npm install`, папка `node_modules` восстановится вместе со всеми добавленными модулями на основе записей в файле `package.json`.

Проекты, написанные на Node.js, добавляются на GitHub без папки `node_modules`, но с файлом `package.json`. После скачивания такого проекта необходимо выполнить в терминале команду `npm install`, чтобы восстановить все установленные через npm модули.