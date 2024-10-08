# Тестовое задание: Реализация класса `SvbTable`

## Описание задания

Необходимо разработать класс `SvbTable`, который будет рендерить таблицу с возможностью отображения списка документов.

Требования:
1. **Отображение таблицы**:
   - Таблица должна правильно вписываться в окружение на странице и сохранять свою структуру при изменении размеров окна.
   - Шапка и подвал таблицы должны всегда оставаться видимыми пользователю при скроллинге.

2. **Работа с данными**:
   - Должен быть реализован метод `loadRows()`, который очищает текущие строки таблицы и загружает новые данные.
   - Реализовать метод `addRow()`, позволяющий добавить строку в таблицу.
   - Реализовать метод `removeRow()`, который удаляет строку из таблицы.
   - Каждая строка должна иметь уникальный идентификатор, который будет храниться в её `dataset` под ключом `uuid`.
   - Каждый столбец должен иметь атрибут `dataset.name`, содержащий имя атрибута.

3. **Интерактивность**:
   - Строки таблицы должны выделяться при наведении курсора и при клике на строку.
   - Необходимо реализовать метод `getActiveRow()`, который возвращает строку, активную в данный момент (на которую был клик).

4. **Методы управления значениями**:
   - Необходимо реализовать два метода:
     - `setValue(args: any[])`: метод для установки значения в конкретной ячейке строки.
     - `getValue(args: any[])`: метод для получения значения из конкретной ячейки строки.
   - Как искать строки и как будут работать данные методы — на усмотрение исполнителя.

5. **Дизайн**:
   - Таблица должна быть стилизована в соответствии с макетом, доступным по [ссылке в Figma](https://www.figma.com/design/b9ZaU7RHYKa281FTzGGfU2/Untitled?node-id=0-1&t=ZXKQzIe56GE0IsVb-1).

## Структура проекта

Проект реализуется на **чистом JavaScript** и **SCSS**, использование любых библиотек или фреймворков **не допускается**. Ниже приведена структура проекта, чтобы было понятно, где разработчик будет реализовывать свою работу:

1. **`index.html`**:
   - В этом файле находится верстка окружения. Исполнителю этот файл не нужен, кроме элемента `<div id="table-wrapper">`, куда будет вставляться таблица, реализованная разработчиком.

2. **`main.js`**:
   - В этом файле исполнитель инициализирует таблицу, получает моковые данные из файла `getList` и вставляет таблицу в элемент `<div id="table-wrapper">`.

3. **`src/api/get-list.js`**:
   - Содержит функцию `getList()`, которая возвращает моковые данные для работы с таблицей. Эти данные будут использоваться для отображения строк в таблице.

4. **`src/scss`**:
   - В этой папке находятся стили окружения. Они необходимы для общего оформления страницы, но не касаются стилей самой таблицы.

5. **`src/components/svb-table/`**:
   - Папка компонента `SvbTable`. В ней будет реализован весь код, связанный с таблицей.

6. **`src/components/svb-table/SvbTable.js`**:
   - Основной файл компонента, в котором исполнитель будет реализовывать класс `SvbTable`.

7. **`src/components/svb-table/styles/svb-table.scss`**:
   - Файл стилей для таблицы. Здесь будут описаны стили для отображения таблицы согласно требованиям и макету в Figma.

## Ожидаемый результат

1. Класс `SvbTable` должен быть реализован с чистым и понятным API, позволяющим интегрировать таблицу в любое окружение.
2. Должна быть продемонстрирована корректная работа со скроллингом, фиксацией шапки и подвала таблицы, а также интерактивным выделением строк.
3. Методы для загрузки, добавления, удаления строк и работы с их значениями должны быть проверены на корректность.
4. Строки таблицы должны содержать в `dataset` уникальный идентификатор (UUID), а столбцы — в `dataset.name` имя атрибута.

## Уточнения

- Предполагается, что данные для таблицы могут быть переданы в формате массива объектов.
- Дизайн таблицы приведен в макете Figma, и реализация должна соответствовать ему.

## Бонусные задачи. Выполнение этих задач будет большим плюсом в принятии решения.

- Реализуйте возможность измениния ширины стоблца пользователем
- Реализуйте возможность закрепить столбец
- Реализуйте методы для заполнения подвала таблицы по имени столбца 
- Зафиксируйте не только заголовок и подвал таблицы, а так же столбец с номером строки
- Рализуйте форматирование данных типа даты и нумерик (можно выполнить отдельным классом или функцией)
