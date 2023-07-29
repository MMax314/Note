## Оглавление:
<!--TOC-->
  - [Оформление markdown;](#-markdown)
  - [Как получить занчения поля по его имени? var reader = command.ExecuteReader();](#-var-reader-command.executereader)
  - [Автоинкремент SQLite](#-sqlite)
<!--/TOC-->

## Оформление markdown;
* [Расширение для Visual Studio: Markdown Editor v2](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor2)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
---

## Как получить занчения поля по его имени? var reader = command.ExecuteReader();

Если ты хочешь получить значение из SqlDataReader по имени столбца, ты можешь использовать индексатор, который принимает строку в качестве параметра. Например:

```cs
var reader = command.ExecuteReader();
while (reader.Read())
{
object value = reader["some field name"]; // Получаем значение по имени столбца
}
```
Это самый простой и понятный способ, но он возвращает значение типа object, которое тебе нужно приводить к нужному типу. Если ты хочешь получить значение определенного типа, ты можешь использовать методы SqlDataReader, такие как GetString, GetInt32 и т.д. Но эти методы принимают целочисленный индекс столбца в качестве параметра. Чтобы получить индекс столбца по его имени, ты можешь использовать метод GetOrdinal, который возвращает номер столбца по его имени. \
Например:
```cs
var reader = command.ExecuteReader();
while (reader.Read())
{
int columnIndex = reader.GetOrdinal("some field name"); // Получаем индекс столбца по его имени
string value = reader.GetString(columnIndex); // Получаем значение типа string по индексу столбца
}
```

Этот способ более эффективный и безопасный, но он требует больше кода и повторяющихся вызовов GetOrdinal. Для улучшения производительности ты можешь вызывать GetOrdinal один раз перед циклом чтения и сохранять его в переменной, а затем использовать эту переменную внутри цикла. \
Например:
```cs
var reader = command.ExecuteReader();
int columnIndex = reader.GetOrdinal("some field name"); // Вызываем GetOrdinal один раз
while (reader.Read())
{
string value = reader.GetString(columnIndex); // Используем сохраненный индекс столбца
}
```
Надеюсь, это поможет тебе. Для более подробной информации ты можешь посмотреть эти ссылки: \
•  https://stackoverflow.com/questions/28325813/sqldatareader-get-value-by-column-name-not-ordinal-number \
•  https://stackoverflow.com/questions/8655965/how-to-get-data-by-sqldatareader-getvalue-by-column-name \
•  https://www.c-sharpcorner.com/article/datareader-in-C-Sharp
 
---
## Автоинкремент SQLite
**Резюме:** \
Ключевое слово AUTOINCREMENT накладывает дополнительную нагрузку на ЦП, память, дисковое пространство и дисковый ввод-вывод, и его следует избегать, если это не является строго необходимым. Обычно это не требуется.

В SQLite столбец с типом INTEGER PRIMARY KEY является псевдонимом для ROWID (за исключением таблиц WITHOUT ROWID ), который всегда представляет собой 64-битное целое число со знаком.

В INSERT , если столбцу ROWID или INTEGER PRIMARY KEY явно не задано значение, оно будет автоматически заполнено неиспользуемым целым числом, обычно на единицу больше, чем самый большой ROWID, используемый в настоящее время. Это верно независимо от того, используется ли ключевое слово AUTOINCREMENT.

Если ключевое слово AUTOINCREMENT появляется после INTEGER PRIMARY KEY, это изменяет алгоритм автоматического назначения ROWID, чтобы предотвратить повторное использование ROWID в течение всего срока службы базы данных. Другими словами, целью AUTOINCREMENT является предотвращение повторного использования ROWID из ранее удаленных строк.

[Источник](https://www.sqlite.org/autoinc.html)

---