## Оглавление:
- [Оглавление:](#оглавление)
- [Оформление markdown;](#оформление-markdown)
- [Как получить занчения поля по его имени? var reader = command.ExecuteReader();](#как-получить-занчения-поля-по-его-имени-var-reader--commandexecutereader)
- [Автоинкремент SQLite](#автоинкремент-sqlite)
- [Разница между reader.GetOrdinal("id") и reader.GetOrdinal("id")](#разница-между-readergetordinalid-и-readergetordinalid)
- [Генерация GUID в Visual Studio. Hot keys](#генерация-guid-в-visual-studio-hot-keys)


## Оформление markdown;
* [Расширение для Visual Studio: Markdown Editor v2](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor2)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
---

## Как получить занчения поля по его имени? var reader = command.ExecuteReader();
```cs
using (var connection = new SqliteConnection(connectionString))
{
	connection.Open();
	var command = connection.CreateCommand();
	command.CommandText = "SELECT * FROM Films LIMIT 3;";
	var reader = command.ExecuteReader();

	//Вариант 2 (2.1)
	var table = (id: reader.GetOrdinal("id"), 
				Name: reader.GetOrdinal("Name"),
				Budget: reader.GetOrdinal("Budget"),
				Year: reader.GetOrdinal("Year"),
				Genre: reader.GetOrdinal("Genre"));

	while (reader.Read())
	{
		//Вариант 1
		Console.WriteLine($"{reader.GetInt32(0)} {reader.GetString(1)} {reader.GetString(2)} {reader.GetString(3)}");

		//Вариант 2 (2.2)
		 Console.WriteLine($"{table.id} {table.Name} {table.Budget} {table.Year} {table.Genre}");

		//Вариант 3
		// Создаем анонимный тип с полями из reader
		var film = new { id = reader["id"], Name = reader["Name"], Budget = reader["Budget"], Year = reader["Year"], Genre = reader["Genre"] };
		// Используем интерполированную строку для вывода
		Console.WriteLine($"{film.id} {film.Name} {film.Budget} {film.Year} {film.Genre}");		
	}
}
```

ОТВЕТ:
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

## Разница между reader.GetOrdinal("id") и reader.GetOrdinal("id")
Разница между reader["id"] и reader.GetOrdinal("id") в том, что первый вариант использует индексатор, который внутри вызывает метод GetValue с индексом, полученным из метода GetOrdinal https://stackoverflow.com/questions/31742331/how-to-properly-read-data-from-sqldatareader-in-c. \
 То есть, reader["id"] эквивалентен reader.GetValue(reader.GetOrdinal("id")). Второй вариант просто возвращает индекс колонки по ее имени, без получения значения. \
 Если ты хочешь получить значение из reader по имени колонки, то ты можешь использовать любой из этих вариантов, но первый более краткий и читабельный. Однако, если ты хочешь повысить производительность, то ты можешь сохранить индекс колонки в переменную вне цикла и использовать его для получения значения: \ 
https://stackoverflow.com/questions/31742331/how-to-properly-read-data-from-sqldatareader-in-c. \
Например:
```cs
var idIndex = reader.GetOrdinal("id");
while (reader.Read())
{
	var id = reader.GetValue(idIndex);
	...
}
```

Также, если ты знаешь тип данных в колонке, то ты можешь использовать специализированные методы, такие как GetInt32, GetString и т.д., которые делают проверку типа и приведение за тебя: \
https://stackoverflow.com/questions/31742331/how-to-properly-read-data-from-sqldatareader-in-c \
https://stackoverflow.com/questions/45609498/exceldatareader-getordinal-method-in-net-core. \
Например:
```cs
var id = reader.GetInt32(idIndex);
```

---
## Генерация GUID в Visual Studio. Hot keys

Нет одной универсальной комбинации горячих клавиш для генерации GUID, так как это зависит от того, какой инструмент или расширение ты используешь для этой цели. Но вот некоторые примеры, которые я нашел в интернете: \
•  Если ты используешь внешний инструмент PowerShell, как я описал ранее, то ты можешь назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда ->Клавиатура*, выбрав команду *Tools.ExternalCommandX*, где X - номер инструмента в списке https://www.tenforums.com/tutorials/130522-generate-globally-unique-identifier-guid-windows.html. \
•  Если ты используешь расширение Visual Commander, то ты можешь назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда ->Клавиатура*, выбрав команду VCmd.CommandX, где X - номер команды в списке https://stackoverflow.com/questions/58634771/generating-a-plain-guid-in-visual-studio. \
•  Если ты используешь окно C# Interactive, то ты можешь создать сниппет кода для генерации GUID и назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда ->Клавиатура*, выбрав команду *Edit.InvokeSnippetFromShortcut* https://bing.com/search?q=most+common+hotkey+for+generate+guid. \
•  Если ты используешь макрос для Visual Studio 2010 или более ранней версии, то ты можешь назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда -> Клавиатура*, выбрав команду *Macros.MyMacros.Module1.CreateGUID*. Например, один из источников https://abhijitjana.net/2011/01/18/use-shortcut-key-to-generate-guid-very-quickly-in-visual-studio/ предлагает использовать Alt+G для этого макроса.

---
