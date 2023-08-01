## Оглавление:
- [Оглавление:](#оглавление)
- [Оформление markdown;](#оформление-markdown)
- [Как получить занчения поля по его имени? var reader = command.ExecuteReader();](#как-получить-занчения-поля-по-его-имени-var-reader--commandexecutereader)
- [Автоинкремент SQLite](#автоинкремент-sqlite)
- [Разница между reader.GetOrdinal("id") и reader.GetOrdinal("id")](#разница-между-readergetordinalid-и-readergetordinalid)
- [Генерация GUID в Visual Studio. Hot keys](#генерация-guid-в-visual-studio-hot-keys)
- [Режимы Bing](#режимы-bing)
- [Создание новой записи. PK ID.](#создание-новой-записи-pk-id)
- [Вывод SQL запросов в консоль DbContext.cs](#вывод-sql-запросов-в-консоль-dbcontextcs)
- [Публикация в Telegram](#публикация-в-telegram)
- [Если базе данных SQLite поле PK имеет тип INTEGER, то какой тип должно быть у свойства Id?](#если-базе-данных-sqlite-поле-pk-имеет-тип-integer-то-какой-тип-должно-быть-у-свойства-id)


## Оформление markdown;
* [Расширение для Visual Studio: Markdown Editor v2](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor2)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
* Visual Studio Code. Добавить оглавление: *Command Pallete* -> *Markdown All in One: Create Table of Contents*
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
## Режимы Bing

**/mode** - позволяет вам переключаться между режимами Balanced, Creative и Precise. \
**/help** - показывает вам инструкции и правила для общения со мной. \
**/feedback** - позволяет вам оставить отзыв о моем качестве и удовлетворенности. \
**/image** - позволяет вам запросить, чтобы я сгенерировал изображение по вашему запросу. Это работает только в режимах Creative и Precise. \
**/content** - позволяет вам запросить, чтобы я сгенерировал контент, такой как стихи, истории, код, эссе, песни, пародии на знаменитостей и многое другое. \
**/improve** - позволяет вам запросить, чтобы я помог вам улучшить или оптимизировать ваш контент. \

Чтобы переключиться между режимами, введите /mode <название режима>. \
*Например:* \
/mode Creative \
/mode Precise \
/mode Balanced \

**Пример:* \
@content \
Небо, вода

@mode Precise

---
## Создание новой записи. PK ID.
**Вопрос:** Проект: *** \
Файл создания Actors:
1) /Actors/Create.cshtml
2) /Actors/Create.cshtml.cs

Вопрос: В проекте используется база данных SQLite version 3. Если в таблице используется PK Integer, то при создании не обязательно задавать значение полю ID, база сама его заполнит. Сейчас, при создании новой записи Actor выводится поле ввода для ID. Что нужно изменить, чтобы поле не выводилось, а заполнялось самой базой данных. \

**Ответ:** Для того, чтобы скрыть поле ID при создании новой записи Actor, ты можешь использовать атрибут [HiddenInput] в модели Actor или в модели ActorViewModel, если ты используешь ее для передачи данных между представлением и контроллером. Этот атрибут позволяет сгенерировать скрытое поле <input type="hidden"> с помощью метода Html.HiddenFor() в представлении. Например:

В модели:
```cs
public class Actor
{
[HiddenInput]
public int ID { get; set; }
public string Name { get; set; }
// other properties
}
```
В представлении:

```html
@model Actor

<form method="post">
@Html.HiddenFor(model => model.ID)
@Html.LabelFor(model => model.Name)
@Html.EditorFor(model => model.Name)
<!-- other fields -->
<input type="submit" value="Create" />
</form>
```
Таким образом, ты сможешь скрыть поле ID от пользователя, но передать его значение в контроллер при отправке формы. База данных SQLite сама заполнит это поле при создании новой записи, если оно имеет тип Integer и является первичным ключом.

Для более подробной информации по работе со скрытыми полями в ASP.NET Core Razor Pages, ты можешь посмотреть следующие ссылки:

•  https://stackoverflow.com/questions/63208733/asp-net-core-with-razor-pages-bind-hidden-input \
•  https://www.aspsnippets.com/Articles/ASPNet-Core-Razor-Pages-Hidden-Field-example.aspx \
•  https://www.tutorialsteacher.com/mvc/htmlhelper-hidden-hiddenfor \

Надеюсь, это поможет тебе решить проблему с полем ID. blush

---

## Вывод SQL запросов в консоль DbContext.cs

```cs
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
        => optionsBuilder.UseSqlite(Program.connectionString)
           .LogTo(Console.WriteLine);//Вывод SQL запросов в консоль
```

---

## Публикация в Telegram
**ВОПРОСЫ:**
1) Что нужно для того, чтобы приложение самостоятельно публиковало сообщения в своем канале Telegram?
2) Есть ли пример программы на C#, которая автоматически отправляет сообщения в Telegram?

**ОТВЕТ:** \
Для того, чтобы приложение самостоятельно публиковало сообщения в своем канале Telegram, вам нужно сделать следующее:

•  Создать бота в Telegram с помощью специального бота @BotFather и получить его API токен https://stackoverflow.com/questions/31271355/how-to-use-telegram-api-in-c-sharp-to-send-a-message https://stackoverflow.com/questions/29363995/telegram-c-sharp-example-send-message.

•  Добавить бота в свой канал Telegram в качестве администратора https://stackoverflow.com/questions/31271355/how-to-use-telegram-api-in-c-sharp-to-send-a-message.

•  Использовать библиотеку Telegram.Bot для C#, которая позволяет работать с Telegram Bot API https://stackoverflow.com/questions/29363995/telegram-c-sharp-example-send-message https://www.codeproject.com/Tips/5303407/How-to-Easily-Create-Telegram-Bot-using-Csharp https://whatsmate.github.io/2022-06-16-send-telegram-message-csharp/.

•  Использовать метод SendTextMessageAsync или другие методы для отправки сообщений в свой канал по его имени или идентификатору https://stackoverflow.com/questions/29363995/telegram-c-sharp-example-send-message https://www.codeproject.com/Tips/5303407/How-to-Easily-Create-Telegram-Bot-using-Csharp https://whatsmate.github.io/2022-06-16-send-telegram-message-csharp/.

Пример программы на C#, которая автоматически отправляет сообщения в Telegram, может выглядеть так:
```cs
using System;
using System.Threading.Tasks;
using Telegram.Bot;

namespace TelegramBotExample
{
	class Program
	{
		static async Task Main(string[] args)
		{
			// Создаем бота с API токеном
			var bot = new TelegramBotClient("your api token here");

			// Проверяем, что бот работает
			var me = await bot.GetMeAsync();
			Console.WriteLine($"Hello, I am {me.FirstName}.");

			// Отправляем сообщение в канал по его имени
			await bot.SendTextMessageAsync("@channelname", "Hello, this is a test message.");

			// Отправляем сообщение в канал по его идентификатору
			await bot.SendTextMessageAsync(-1001234567890, "Hello, this is another test message.");
		}
	}
}
```

---

## Если базе данных SQLite поле PK имеет тип INTEGER, то какой тип должно быть у свойства Id?
**Ответ:** long \
**Вопрос:** Почему long, а не int? \
**Ответ:** Потому что в SQLite тип INTEGER имеет диапазон значений от -9223372036854775808 до +9223372036854775807 \

---