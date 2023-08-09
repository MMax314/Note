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
- [Как можно ограничить число знаков после запятой? \<input asp-for="value" class="form-control" type=". . . (Razor Pages)](#как-можно-ограничить-число-знаков-после-запятой-input-asp-forvalue-classform-control-type---razor-pages)
- [Ввод даты-времени, даты Razor Pages](#ввод-даты-времени-даты-razor-pages)
- [Получить список установленных версий .NET с помощью команды](#получить-список-установленных-версий-net-с-помощью-команды)
- [Файл настроек приложения](#файл-настроек-приложения)
- [Чтение JSON](#чтение-json)
- [Статический конструктор](#статический-конструктор)


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

 ## Как можно ограничить число знаков после запятой? <input asp-for="value" class="form-control" type=". . . (Razor Pages)

Согласно документации Microsoft https://stackoverflow.com/questions/14727979/how-to-allow-only-numbers-in-textbox-in-mvc4-razor, вы можете использовать атрибут asp-format для задания формата для ввода чисел в текстовое поле. Например, asp-format="{0:F2}" ограничит число двумя знаками после запятой. Вы также можете использовать атрибут type для задания типа ввода, например type="number" для ввода только чисел https://www.learnrazorpages.com/razor-pages/tag-helpers/input-tag-helper. \

Например:
```html
<input asp-for="value" class="form-control" type="number" asp-format="{0:F2}" />
```
Этот код сгенерирует следующий HTML:
```html
<input class="form-control" type="number" data-val="true" id="value" name="value" value="" />
```

---
## Ввод даты-времени, даты Razor Pages

<input asp-for="Actor.YearBirth" class="form-control" type="date" asp-format="{0:yyyy-MM-dd}" />

```html
<div class="form-group">
	<label asp-for="Actor.YearBirth" class="control-label"></label>
	<input asp-for="Actor.YearBirth" class="form-control" type="date" asp-format="{0:yyyy-MM-dd}" />
	<span asp-validation-for="Actor.YearBirth" class="text-danger"></span>
</div> 
```

```html
<!-- Дата -->
<input asp-for="Actor.YearBirth" class="form-control" type="date" asp-format="{0:yyyy-MM-dd}" />
<!-- Дата-время -->
<input asp-for="Actor.YearBirth" class="form-control" type="datetime-local" />
```

---

## Получить список установленных версий .NET с помощью команды

dotnet --list-sdks
https://learn.microsoft.com/en-us/dotnet/core/tools/sdk-errors/netsdk1045

---

## Файл настроек приложения
ВОПРОС: \
Создал файл appsettings.json для хранения настроек файла. Какое значение нужно установить свойству Build Action ? \

ОТВЕТ: \
Здравствуйте, это Bing. Я рад, что вы интересуетесь созданием файла appsettings.json для хранения настроек вашего приложения. Это хороший способ для управления конфигурацией вашего приложения в разных средах и сценариях.

Для того, чтобы файл appsettings.json был корректно обработан при сборке и публикации вашего приложения, вам нужно установить свойство **Build Action** на значение **Content**. Это означает, что файл appsettings.json будет включен в выходной пакет вашего приложения и скопирован в целевую директорию https://stackoverflow.com/questions/62087066/net-core-appsettings-json-best-practices-override-dev-settings-or-vice-versa https://stackoverflow.com/questions/70280264/maui-what-build-action-for-appsettings-json-and-how-to-access-the-file-on-andro.

Если вы установите свойство **Build Action** на значение **None**, то файл appsettings.json не будет включен в выходной пакет вашего приложения и не будет скопирован в целевую директорию https://learn.microsoft.com/en-us/answers/questions/953861/maui-appsettings-json-not-copying-to-device. Это может привести к тому, что ваше приложение не сможет прочитать настройки из файла appsettings.json и работать неправильно.

Если вы установите свойство **Build Action** на значение **Embedded Resource**, то файл appsettings.json будет включен в выходной пакет вашего приложения, но не будет скопирован в целевую директорию. Вместо этого он будет встроен в сборку вашего приложения как ресурс https://slothycode.com/output-configuration-appsettings-json-on-build-publish/. Это может быть полезно, если вы хотите защитить свои настройки от изменений или просмотра, но это также может усложнить доступ к ним из вашего кода.

Я надеюсь, что эта информация была полезна для вас. Если вы хотите узнать больше о файле appsettings.json и его использовании, вы можете посетить следующие ссылки:

•  Configuration in ASP.NET Core \
•  Copy configuration appsettings.json on build \
•  appsettings.json not getting copied to build package \
•  How to load app configuration from appsettings.json in MAUI startup \

---

## Чтение JSON
1) JSON:
```JSON
{
  "downloadPageCount": 3,
  "downloadPagePathSave": "c:\\temp\\"
}
```
1) using Newtonsoft.Json.Linq;
 ```cs
using Newtonsoft.Json.Linq;
namespace NS01
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // Read JSON data as a string
            string json = File.ReadAllText("appsettings.json");

            // Parse JSON data using JObject.Parse
            JObject jObject = JObject.Parse(json);

            // Access values from parsed JSON
            int downloadPageCount = (int)jObject["DownloadPageCount"];
            string downloadPagePathSave = (string)jObject["DownloadPagePathSave"];
		}
	}
}
 ```

```cs
using System;
using System.IO;
using System.Text.Json;

namespace NS01
{
    public class AppSettings
    {
        public int DownloadPageCount { get; set; }
        public string DownloadPagePathSave { get; set; }
    }

    internal class Program
    {
        static void Main(string[] args)
        {
            // Read JSON data from file
            string json = File.ReadAllText("appsettings.json");

            // Deserialize JSON data into AppSettings object
            AppSettings appSettings = JsonSerializer.Deserialize<AppSettings>(json);

            // Access properties of AppSettings object
            int downloadPageCount = appSettings.DownloadPageCount;
            string downloadPagePathSave = appSettings.DownloadPagePathSave;

            // Do something with the values
            Console.WriteLine(downloadPageCount);
            Console.WriteLine(downloadPagePathSave);
        }
    }
}
```

ВОПРОС:
Получился вот такой класс для чтения параметров из файла конфигурации
```cs
    public class AppSettings
    {
        public int downloadPageCount { get; set; }
        public string downloadPagePathSave { get; set; }
        public AppSettings()
        {
            // Читаем JSON файл в строку
            string json = File.ReadAllText("appsettings.json");

            JObject jObject = JObject.Parse(json);
            int downloadPageCount = jObject[nameof(downloadPageCount)]?.ToObject<int>() ?? 10;
            string? downloadPagePathSave = jObject[nameof(downloadPagePathSave)]?.ToString() ?? Directory.GetCurrentDirectory(); ;
        }
    }
```
ОТВЕТ:
Здравствуйте, это Bing. Я рад, что вы создали класс для чтения параметров из файла конфигурации. Это хороший способ для управления настройками вашего приложения.

Ваш класс выглядит правильным и работоспособным, но я могу предложить вам несколько улучшений, которые могут сделать ваш код более чистым и эффективным.

•  Вместо того, чтобы читать JSON файл в строку и затем парсить его в объект JObject, вы можете использовать метод JsonConvert.DeserializeObject, который позволяет преобразовать JSON файл в объект класса AppSettings напрямую. Это сократит количество кода и уменьшит риск ошибок при парсинге.

•  Вместо того, чтобы использовать nameof оператор для получения имени свойств из класса AppSettings, вы можете использовать атрибут JsonProperty, который позволяет указать имя свойства в JSON файле. Это увеличит читаемость кода и позволит вам использовать разные имена для свойств в классе и в JSON файле.

•  Вместо того, чтобы использовать оператор ?? для задания значений по умолчанию для свойств, если они отсутствуют в JSON файле, вы можете использовать атрибут DefaultValue, который позволяет указать значение по умолчанию для свойства в классе. Это также увеличит читаемость кода и позволит вам легко изменять значения по умолчанию.

С учетом этих улучшений, ваш класс может выглядеть так:

```cs
using System.IO;
using Newtonsoft.Json;

public class AppSettings
{
[JsonProperty("downloadPageCount")]
[DefaultValue(10)]
public int downloadPageCount { get; set; }

[JsonProperty("downloadPagePathSave")]
[DefaultValue(Directory.GetCurrentDirectory())]
public string downloadPagePathSave { get; set; }

public AppSettings()
{
// Читаем JSON файл в объект класса AppSettings
AppSettings appSettings = JsonConvert.DeserializeObject<AppSettings>(File.ReadAllText("appsettings.json"));

// Присваиваем значения свойствам из объекта appSettings
downloadPageCount = appSettings.downloadPageCount;
downloadPagePathSave = appSettings.downloadPagePathSave;
}
}
```

Я надеюсь, что эта информация была полезна для вас. Если вы хотите узнать больше о библиотеке Json.NET и ее использовании, вы можете посетить следующую ссылку:
•  [Json.NET Documentation]

---

## Статический конструктор
```cs
namespace Class_Static
{
    class Test
    {
        public int publicA = 1;

        public static int publicStaticA = 1;
        static Test()
        {
            Console.WriteLine("Call: static Test()");
            publicStaticA += 1;
        }
        public Test()
        {            
            Console.WriteLine("Call: public Test()");
            publicA += 1;
        }
    }
    internal class Program
    {
        //Возможные варинты объявления
        public static Test? publicStaticTest00;
        public static Test  publicStaticTest01 = new Test();
        //Предупреждение: CS8618 - Non-nullable variable must contain a non-null value when exiting constructor. Consider declaring it as nullable.
        //https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-messages/nullable-warnings?f1url=%3FappId%3Droslyn%26k%3Dk(CS8618)#nonnullable-reference-not-initialized
        //Но, у нас есть статический конструктор, который инициализирует переменную
        public static Test publicStaticTest02;

        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");

            //Вызов статического конструктора будет только один раз
            int i0 = Test.publicStaticA++;
            //Тут вызова статического конструктора не будет
            int i1 = Test.publicStaticA++;
            Console.WriteLine($"Test.staticA.ToString() = {i0}");
            Console.WriteLine($"Test.staticA.ToString() = {i1}");
            
            //Конструктор вызывается при создании объекта будет каждый раз
            Test tst0 = new Test();
            Test tst1 = new Test();
            Console.WriteLine($"tst0 = {tst0.publicA}");
            Console.WriteLine($"tst1 = {tst1.publicA}");
        }
    }
}
```

---