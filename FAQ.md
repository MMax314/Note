## Оглавление:
- [Разное](#разное)
  - [Выполнение скрипта PowerShall во время сборки проекта;](#выполнение-скрипта-powershall-во-время-сборки-проекта)
  - [Оформление markdown;](#оформление-markdown)
  - [Режимы Bing](#режимы-bing)
  - [Creating a Visual Studio Offline Installer](#creating-a-visual-studio-offline-installer)
  - [Квантовое шифрование](#квантовое-шифрование)
  - [Powershell. Cкрипт. Шифровка, дешифровка текста](#powershell-cкрипт-шифровка-дешифровка-текста)
  - [PowerShell. Объединение всех текстовых файлов из каталога в один файл](#powershell-объединение-всех-текстовых-файлов-из-каталога-в-один-файл)
  - [PowerShell. Разархивирование архивов из каталога](#powershell-разархивирование-архивов-из-каталога)
  - [Контрольная сумма MD5, SHA](#контрольная-сумма-md5-sha)
  - [SSD](#ssd)
  - [GitHub Copilot. Проверка кода](#github-copilot-проверка-кода)
- [C++](#c)
  - [C++. ModBus. modpool.exe Адресация](#c-modbus-modpoolexe-адресация)
  - [C++. ModBus. Контрольная сумма. CRC-16 / ModBus](#c-modbus-контрольная-сумма-crc-16--modbus)
  - [C++. ModBus. Два регистра во float](#c-modbus-два-регистра-во-float)
  - [C++. ModBus. 4 byte to float](#c-modbus-4-byte-to-float)
  - [C++. Список файлов/каталогов](#c-список-файловкаталогов)
  - [C++. TStringList разбиение текста по строкам с использованием разделителя. Игнорирование пробела.](#c-tstringlist-разбиение-текста-по-строкам-с-использованием-разделителя-игнорирование-пробела)
- [C#](#c-1)
  - [C#. SQLite. Как сохранить БД из памяти в файл (на диск)](#c-sqlite-как-сохранить-бд-из-памяти-в-файл-на-диск)
  - [C#. Вывод SQL запросов в консоль DbContext.cs](#c-вывод-sql-запросов-в-консоль-dbcontextcs)
  - [C#. Разница между reader.GetOrdinal("id") и reader.GetOrdinal("id")](#c-разница-между-readergetordinalid-и-readergetordinalid)
  - [C#. Генерация GUID в Visual Studio. Hot keys](#c-генерация-guid-в-visual-studio-hot-keys)
  - [C#. Получить список установленных версий .NET с помощью команды](#c-получить-список-установленных-версий-net-с-помощью-команды)
  - [C#. Как получить занчения поля по его имени? var reader = command.ExecuteReader();](#c-как-получить-занчения-поля-по-его-имени-var-reader--commandexecutereader)
  - [C#. Публикация в Telegram](#c-публикация-в-telegram)
  - [C#. Файл настроек приложения](#c-файл-настроек-приложения)
  - [C#. Чтение JSON](#c-чтение-json)
  - [C#. Статический конструктор](#c-статический-конструктор)
  - [C#. Создание новой записи. PK ID.](#c-создание-новой-записи-pk-id)
  - [C#. Консольное приложение. Меню выбора](#c-консольное-приложение-меню-выбора)
  - [C#. Async - Await](#c-async---await)
  - [C#. SOLID](#c-solid)
  - [C#. Измерение времени работы Stopwatch()](#c-измерение-времени-работы-stopwatch)
  - [C#. SeriLog. Ведение логов](#c-serilog-ведение-логов)
- [C#. Файлы конфигурации приложения](#c-файлы-конфигурации-приложения)
  - [C#. OpenSSL](#c-openssl)
- [SQLite](#sqlite)
  - [SQLite. Автоинкремент SQLite](#sqlite-автоинкремент-sqlite)
  - [SQLite. Если базе данных SQLite поле PK имеет тип INTEGER, то какой тип должно быть у свойства Id?](#sqlite-если-базе-данных-sqlite-поле-pk-имеет-тип-integer-то-какой-тип-должно-быть-у-свойства-id)
- [SQL](#sql)
  - [SQL. Use Cases for Non-Equi JOINs (неравноправные соединения)](#sql-use-cases-for-non-equi-joins-неравноправные-соединения)
  - [SQL. Декартов взрыв. Картезианский взрыв. Выбор названия](#sql-декартов-взрыв-картезианский-взрыв-выбор-названия)
  - [SQL. Декартов взрыв. Картезианский взрыв. Создание таблиц и их заполнение](#sql-декартов-взрыв-картезианский-взрыв-создание-таблиц-и-их-заполнение)
  - [SQL. Декартов взрыв. Картезианский взрыв.](#sql-декартов-взрыв-картезианский-взрыв)
- [EF Core](#ef-core)
  - [EF Core. scaffold-DbContext](#ef-core-scaffold-dbcontext)
  - [EF Core. scaffold-DbContext. Пространство имен -ContextNamespace и  -Namespace](#ef-core-scaffold-dbcontext-пространство-имен--contextnamespace-и---namespace)
  - [EF Core. scaffold-DbContext. Ключ -DataAnnotation](#ef-core-scaffold-dbcontext-ключ--dataannotation)
  - [EF Core. scaffold-DbContext. Будет ли с ключем -Data Annotations по умолчанию работать каскадное удаление?](#ef-core-scaffold-dbcontext-будет-ли-с-ключем--data-annotations-по-умолчанию-работать-каскадное-удаление)
- [Razor pages](#razor-pages)
  - [Razor pages. Библиотеки визуальных компонентов](#razor-pages-библиотеки-визуальных-компонентов)
  - [Razor Pages. Как можно ограничить число знаков после запятой? \<input asp-for="value" class="form-control" type=". . .](#razor-pages-как-можно-ограничить-число-знаков-после-запятой-input-asp-forvalue-classform-control-type--)
  - [Razor Pages. Ввод даты-времени, даты](#razor-pages-ввод-даты-времени-даты)
- [Blazor](#blazor)
  - [Blazor. .Net8 изменения](#blazor-net8-изменения)
  - [Blazor. Linux. Консольное приложение](#blazor-linux-консольное-приложение)
- [React](#react)
  - [React. TypeScript](#react-typescript)
  - [React. Npm](#react-npm)
  - [React. Ошибка при создании проекта React:](#react-ошибка-при-создании-проекта-react)
  - [React. Создание приложения](#react-создание-приложения)
- [PostgreSQL](#postgresql)
  - [PostgreSQL. Создание и конфигури БД](#postgresql-создание-и-конфигури-бд)

<!-- ---------------------------------------- -->
<!-- ---------------------------------------- -->
<!-- ---------------------------------------- --> 
# Разное
<!--BEGIN-->
## Выполнение скрипта PowerShall во время сборки проекта;
Да, вы можете настроить Visual Studio так, чтобы автоматически выполнялся скрипт PowerShell во время компиляции проекта. Это обычно делается с помощью пост-сборочных событий1. Вот пример того, как это можно сделать:

Откройте свойства проекта в Visual Studio.
Перейдите на вкладку **“События сборки”**.
В разделе **“После сборки”** введите команду для запуска вашего скрипта PowerShell. Например, если ваш скрипт называется myscript.ps1 и находится в корневом каталоге проекта, вы можете ввести следующую команду:\
```cmd
powershell.exe -ExecutionPolicy Bypass -File "$(ProjectDir)myscript.ps1"
```

Эта команда запустит скрипт myscript.ps1 каждый раз после успешной сборки проекта.
Обратите внимание, что powershell.exe -ExecutionPolicy Bypass позволяет временно обойти политику выполнения скриптов в PowerShell, чтобы можно было запустить ваш скрипт1.
Также стоит отметить, что если вы используете 64-битную систему, вам нужно разрешить выполнение скриптов в 32-битной версии PowerShell, поскольку исполняемый файл Visual Studio (devenv.exe) является 32-битным1.
- - -
<!--END-->

<!--BEGIN-->
## Оформление markdown;
* [Расширение для Visual Studio: Markdown Editor v2](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor2)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
* Visual Studio Code. Добавить оглавление: *Command Pallete* -> *Markdown All in One: Create Table of Contents*
- - -
<!--END-->

<!--BEGIN-->
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
- - -
<!--END-->

<!--BEGIN-->
## Creating a Visual Studio Offline Installer
Источник: https://trailheadtechnology.com/creating-a-visual-studio-offline-installer/

First, we need to get the installer from the [download page](https://visualstudio.microsoft.com/vs/preview/#download-preview) and store it in a local folder. I will use c:\VSOffline

After that, we need to open a command window in the folder where the installer was downloaded and then run the following instruction, which will start the slow download process.

```bash
VisualStudioSetup.exe --layout C:\VSOffline --lang en-US --add Microsoft.VisualStudio.Workload.NetCrossPlat --add Microsoft.VisualStudio.Workload.Universal --includeRecommended --includeOptional
```

Description of the parameters: \
**–layout** is the destination folder \
**–lang** the language to download, available values are specified in the BCP 47 column in the following link \
**–includeRecommended** & **–includeOptional** will make sure that all the needed files will be included \
**–add** used to include all the workflows that we need. In my case, I’m interested in cross-platform development, but you can see the available flows here \

**Update our installer** \
If we already created the installer, we can update to the latest version using the same call used to create our initial version.

**Install Visual Studio** \
In the same command line window used to do the download, we can use the following command.
```bash
VisualStudioSetup.**exe** --passive --norestart --includeOptional
```
This will start the installation, as shown in the following screenshot. The files are not downloaded again. The installer is only checking that they are available. \
If we open the GUI from the installer, we will see that the selected workflows were installed. \
In a following post, I’m going to add more information about how the process can be further automated and how it can be used with Windows Sandbox (in Spanish) to create temporary clean development environments. \
- - -
<!--END-->

<!--BEGIN-->
## Квантовое шифрование
Квантовое шифрование - это способ защиты информации с помощью квантовых явлений, таких как сверхпозиция и запутанность. Сверхпозиция означает, что квантовый объект, например фотон, может находиться в нескольких состояниях одновременно, пока его не измерят. Запутанность означает, что два квантовых объекта могут быть связаны так, что изменение одного влияет на другой, даже если они находятся на большом расстоянии друг от друга.

Квантовое шифрование позволяет передавать секретный ключ между двумя пользователями по квантовому каналу, например по оптическому волокну. Ключ - это случайная последовательность битов, которая используется для шифрования и расшифрования сообщений. При квантовом шифровании ключ кодируется в состояниях квантовых объектов, например в поляризации фотонов. Поляризация - это направление колебания электрического поля света. Она может быть горизонтальной, вертикальной или под углом.

Преимущество квантового шифрования в том, что любая попытка подслушать или перехватить ключ приводит к тому, что он искажается или разрушается. Это связано с тем, что измерение квантового объекта влияет на его состояние и нарушает сверхпозицию. Таким образом, пользователи могут обнаружить наличие злоумышленника по уровню ошибок или шума в передаваемом ключе. Если ошибок нет или они незначительны, то ключ можно считать безопасным и использовать для дальнейшего обмена зашифрованными сообщениями.

Одним из простейших алгоритмов квантового шифрования является алгоритм Беннета-Брассара (BB84), который был предложен в 1984 году https://ru.wikipedia.org/wiki/%D0%9A%D0%B2%D0%B0%D0%BD%D1%82%D0%BE%D0%B2%D0%B0%D1%8F_%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%BE%D0%B3%D1%80%D0%B0%D1%84%D0%B8%D1%8F. В этом алгоритме отправитель (Алиса) генерирует случайную последовательность битов и кодирует каждый бит в поляризацию фотона с помощью одной из двух баз: прямоугольной или диагональной. Прямоугольная база состоит из горизонтальной и вертикальной поляризации, диагональная - из поляризации под углом 45° и 135°. Например, Алиса может использовать следующее правило: 0 - горизонтальная или 45° поляризация, 1 - вертикальная или 135° поляризация. Затем Алиса посылает фотоны получателю (Бобу) по квантовому каналу.

Боб не знает, какую базу использовала Алиса для каждого фотона. Он выбирает случайную базу для измерения каждого фотона и записывает результаты. После этого Алиса и Боб обмениваются информацией о выбранных базах по открытому каналу и отбрасывают те биты, для которых они использовали разные базы. Оставшиеся биты образуют согласованный ключ, который они могут проверить на ошибки и скорректировать при необходимости.

Если кто-то пытается подслушать или перехватить ключ, например Ева, то она должна измерять фотоны, не зная, какую базу использовала Алиса. Это приводит к тому, что Ева вносит ошибки в ключ, которые могут быть обнаружены Алисой и Бобом. Таким образом, они могут определить, что их канал не безопасен и отказаться от использования ключа.

Квантовое шифрование имеет ряд преимуществ перед классическим шифрованием, таких как:

•  Высокий уровень безопасности, основанный на фундаментальных законах физики, а не на сложности вычислений.

•  Возможность обнаруживать и предотвращать попытки подслушивания или взлома.

•  Совместимость с существующими технологиями связи, такими как оптические волокна.

Однако квантовое шифрование также имеет ряд ограничений и сложностей, таких как:

•  Низкая скорость передачи данных по сравнению с классическим шифрованием.

•  Высокая чувствительность к помехам и потерям в канале связи.

•  Необходимость точной синхронизации и выравнивания приборов для измерения квантовых состояний.

•  Высокая стоимость и сложность оборудования для генерации и детектирования квантовых объектов.

Несмотря на эти трудности, квантовое шифрование является перспективным направлением развития информационной безопасности в условиях роста квантовых вычислений. Уже существуют практические реализации квантового шифрования, например, в Китае https://trends.rbc.ru/trends/industry/63a94bab9a79473b7ff5f721, Швейцарии и России. В будущем ожидается создание глобальной квантовой сети, которая будет объединять разные регионы и континенты с помощью спутников и наземных станций.
- - -
<!--END-->

<!--BEGIN-->
## Powershell. Cкрипт. Шифровка, дешифровка текста
Для шифрования и расшифрования текста с помощью PowerShell можно использовать различные методы и алгоритмы. Например, можно использовать класс System.Security.Cryptography.Aes https://learn.microsoft.com/ru-ru/powershell/scripting/windows-powershell/ise/how-to-write-and-run-scripts-in-the-windows-powershell-ise?view=powershell-7.3 из .NET Framework для создания симметричного ключа шифрования и применять его к тексту с помощью методов Encrypt и Decrypt. Для этого нужно создать файл скрипта с расширением .ps1 и написать в нем код, который будет генерировать ключ, шифровать и расшифровывать текст. Вот пример такого скрипта https://habr.com/ru/companies/ruvds/articles/487876/:
```PowerShell
# Создаем объект AES
$aes = New-Object System.Security.Cryptography.Aes

# Генерируем случайный ключ и вектор инициализации
$aes.GenerateKey()
$aes.GenerateIV()

# Сохраняем ключ и вектор в файлы
$aes.Key | Out-File -FilePath "C:\temp\aes.key"
$aes.IV | Out-File -FilePath "C:\temp\aes.iv"

# Задаем текст для шифрования
$text = "Это секретное сообщение"

# Преобразуем текст в байты
$bytes = [System.Text.Encoding]::UTF8.GetBytes($text)

# Шифруем байты с помощью AES
$encrypted = $aes.CreateEncryptor().TransformFinalBlock($bytes, 0, $bytes.Length)

# Сохраняем зашифрованные байты в файл
$encrypted | Out-File -FilePath "C:\temp\encrypted.txt"

# Читаем зашифрованные байты из файла
$encrypted = Get-Content -Path "C:\temp\encrypted.txt"

# Расшифровываем байты с помощью AES
$decrypted = $aes.CreateDecryptor().TransformFinalBlock($encrypted, 0, $encrypted.Length)

# Преобразуем байты в текст
$text = [System.Text.Encoding]::UTF8.GetString($decrypted)

# Выводим расшифрованный текст на экран
Write-Host $text
```
Для запуска скрипта нужно открыть PowerShell и выполнить команду .\script.ps1, где script.ps1 - имя файла скрипта. Перед этим нужно убедиться, что политика выполнения скриптов разрешает запускать не подписанные скрипты. Для этого можно использовать команду Set-ExecutionPolicy Unrestricted https://tproger.ru/translations/powershell-tutorial/.

Есть и другие способы шифрования и расшифрования текста с помощью PowerShell, например, с использованием алгоритма RSA https://winitpro.ru/index.php/2019/04/03/zapusk-powershell-skripta-kak-sluzhby-windows/ или сертификата Code Signing https://winitpro.ru/index.php/2016/11/17/kak-podpisat-skript-powershell-sertifikatom/
- - -
<!--END-->

<!-- BEGIN -->
## PowerShell. Объединение всех текстовых файлов из каталога в один файл

```bash
#-----------------------------------------------
#Объединение всех текстовых файлов из каталога в один файл
#-----------------------------------------------
$dir = "C:\\Work\\1"
$outputFile = "C:\\Work\\1\\!_All_Data.csv"

# Получите все файлы .csv в каталоге
$files = Get-ChildItem -Path $dir -Filter *.csv

# Объедините все файлы в один
foreach ($file in $files)
{
    Get-Content -LiteralPath $file.FullName | Add-Content $outputFile
}
```
- - -
<!-- END -->

<!-- BEGIN -->
## PowerShell. Разархивирование архивов из каталога

```bash
#------------------------------------
#Разархивирование архивов из каталога
#------------------------------------
$dir = "C:\\Work"
$files = Get-ChildItem -Path $dir -Filter *.7z

foreach ($file in $files) {
    & "C:\Program Files\7-Zip\7z.exe" x $file.FullName "*one*" "*two*"
}
```
- - -
<!-- END -->

<!--BEGIN-->
## Контрольная сумма MD5, SHA
MD2, MD4, MD5, SHA1, SHA256, SHA384, SHA512
```sh
CertUtil.exe -hashfile "c:\work\!_text.txt" MD2 >>crc.txt
```
- - -
<!--END-->

<!--BEGIN-->
## SSD
1) [Download Software, Firmware and Drivers for WD Products](https://support-en.wd.com/app/answers/detailweb/a_id/10346#gs=eyJndWlkZUlEIjozMDgsInF1ZXN0aW9uSUQiOjEsInJlc3BvbnNlSUQiOjEsImd1aWRlU2Vzc2lvbiI6IjZlOE9icGxxIiwic2Vzc2lvbklEIjoiZWVFRWJwbHEifQ)
2) [Download Dashboard](https://wddashboarddownloads.wdc.com/wdDashboard/DashboardSetup.exe)
- - -
<!--END-->

<!--BEGIN-->
## GitHub Copilot. Проверка кода
"Можешь ли ты провести полный анализ и ревью моего кода, учитывая следующие критерии:
1.	Соответствие стандартам кодирования и стилю кода.
2.	Эффективность и производительность кода.
3.	Обработка ошибок и исключений.
4.	Читаемость и поддерживаемость кода.
5.	Безопасность кода.
6.	Корректность и полнота реализации функциональности.
7.	Использование подходящих типов данных и структур.
8.	Корректное использование библиотек и фреймворков.
9.	Наличие и качество комментариев и документации.
10.	Соответствие принципам SOLID и другим принципам объектно-ориентированного программирования."
Это поможет мне понять, что вы хотите получить всесторонний анализ вашего кода, и я смогу предоставить вам обратную связь по каждому из этих критериев.
- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->

<!--END_SECTION: Разное-->

<!--BEGIN_SECTION: C++-->
# C++
<!--BEGIN-->
## C++. ModBus. modpool.exe Адресация

```bash
modpoll.exe -m rtu -a 1 -r 0x0079 -c 2 -b 9600 -d 8 -s 1 -p none COM3
```
Отправленный запрос (SerialPort): *01 03 00 **78** 00 02 44 12*

В протоколе Modbus адреса регистров обычно начинаются с 1, а не с 0¹². 
Поэтому, когда вы указываете адрес регистра как `0x0079`, он соответствует регистру `0x0078` в запросе Modbus¹². Это известно как "**адресация PDU**", и она является стандартной для протокола Modbus¹².

Команда `modpoll` генерирует запрос Modbus RTU для чтения двух регистров, начиная с адреса `0x0078` (или `0x0079` в адресации PDU), от устройства с ID 1 на порту COM3¹². Это объясняет, почему вы видите `01 03 00 78 00 02` в начале вашего запроса¹².

(1) Free Modbus Master Simulator and Test Tool. https://www.modbusdriver.com/modpoll.html.\
(2) Modbus Poll user manual - modbus tools. https://www.modbustools.com/mbpoll-user-manual.html.\
(3) Modbus Software - Mbpoll / Modpoll (Windows) - DomoticX Knowledge Center. https://domoticx.com/modbus-software-mbpoll-modpoll-windows/.\
(4) undefined. https://www.modbustools.com.
- - -
<!--END-->

<!--BEGIN-->
## C++. ModBus. Контрольная сумма. CRC-16 / ModBus
```C++
unsigned int TForm1::calculateModbusCRC16Checksum(const unsigned char* data, unsigned int length)
{
  /*
    //Проверка: https://crccalc.com/
    //Алгоритм: CRC-16/MODBUS
    //Запрос: 0x00 0x03 0x00 0x79 0x00 0x02
    //Результат: CRC=0x0314; CRC Lo=0x14; CRC Hi=0x03
    unsigned char request[8] = {0x00, 0x03, 0x00, 0x79, 0x00, 0x02, 0x00, 0x00};  // Extra two bytes for CRC
    unsigned int crc = calculateCRC16_Modbus(request, sizeof(request) - 2);  // Calculate CRC for the first 6 bytes

    // Add CRC to the request
    request[6] = crc & 0xFF;  // CRC Lo
    request[7] = (crc >> 8) & 0xFF;  // CRC Hi
  */

  unsigned int crc = 0xFFFF;
  for (unsigned int pos = 0; pos < length; pos++)
  {
      crc ^= (unsigned int)data[pos];  // XOR byte into least significant byte of crc
      for (int i = 8; i != 0; i--)
      {  // Loop over each bit
          if ((crc & 0x0001) != 0)
          {  // If the LSB is set
              crc >>= 1;  // Shift right and XOR 0xA001
              crc ^= 0xA001;
          } else {
            // Else LSB is not set
            crc >>= 1;  // Just shift right
          }//if
      }//for
  }//for

  // Note, this number has low and high bytes swapped, so use it accordingly (or swap bytes)
  return crc;
}
```
- - -
<!--END-->

<!--BEGIN-->
## C++. ModBus. Два регистра во float
3. Описание формата с плавающей точкой IEEE 754 32-bit\
Формат с плавающей точкой IEEE 754 передается в двух регистрах Modbus.\
Алгоритм преобразования значения из пары регистров Modbus в значения с
плавающей точкой (для Microsoft Visual Studio):\

```C++
  int wReg1 = 0;
  int wReg2 = 16078;

  DWORD wReg = wReg1 | (wReg2 << 16);
  float fV;
  memcpy( &fV, &wReg, sizeof(float) );

  // fV = 0,4 (приблизительно)
```

[Источник](http://signalrp.ru/catalog/vope-v1/Modbus_RTU_v1.4.pdf)
- - - - -
<!--END-->

<!--BEGIN-->
## C++. ModBus. 4 byte to float
```C++
  union { char c[4]; float f; } conv0;
  //int buf[] = {0x00, 0x00, 0x41, 0xB5};//22,625 Порядок байт, как в ответе прибора
  int buf[] = {0x80, 0x00, 0x43, 0x70};//240,5
  float value0 =          ieee754 ( buf[2],      buf[3],      buf[0],    buf[1]);

  int   valueInt =                 (buf[2]<<24)+(buf[3]<<16)+(buf[0]<<8)+buf[1];
  float value1 = *(float*)&valueInt;

  conv0.c[0] = buf[1];
  conv0.c[1] = buf[0];
  conv0.c[2] = buf[3];
  conv0.c[3] = buf[2];
  float value2 = conv0.f;
```
Статьи:
1) https://www.programmersought.com/article/260510174437/
2) https://stackoverflow.com/questions/7714908/modbus-tcp-answer-convert-to-a-float-c
3) https://cplusplus.com/forum/beginner/94979/
- - - - -
<!--END-->

<!--BEGIN-->
## C++. Список файлов/каталогов
```C++
	AnsiString pathCsvIn = "C:\\Temp";

	//namespace fs = std::filesystem;
	//#include <filesystem> //std::filesystem::directory_iterator
	for (const auto & entry : std::filesystem::directory_iterator(pathCsvIn.c_str()))
	{
		if ( (std::filesystem::is_directory(entry.path())) == true )
		{
			//Каталог
		} else if (entry.path().extension().empty()) {
			//Файл
		} else if ( (std::filesystem::is_regular_file(entry.path())) == true ) {
			//Проверка на нужное расширение
			if ( UpperCase(entry.path().extension().c_str()) == UpperCase(".csv") )
			{
				Memo->Lines->Add(entry.path().c_str());
			}
		}
	}
```
- - -
<!--END-->

<!--BEGIN-->
## C++. TStringList разбиение текста по строкам с использованием разделителя. Игнорирование пробела.
`TStringList` имеет свойство `Delimiter`, установленное в `';'`. Однако, `TStringList` также имеет свойство `DelimitedText`, которое автоматически разбивает строку на подстроки, используя `Delimiter` и пробелы¹².

По умолчанию, `DelimitedText` считает пробелы разделителями, в дополнение к символу, указанному в `Delimiter`¹². Это означает, что если в строке есть пробелы, `DelimitedText` разобьет строку на подстроки по этим пробелам, а также по символу `';'`.

Чтобы `DelimitedText` разбивал строку только по символу `';'`, и игнорировал пробелы, нужно установить свойство `StrictDelimiter` в `true` перед установкой `DelimitedText`¹²:

```cpp
TStringList *row = new TStringList;
row->Delimiter = ';';
row->StrictDelimiter = true;  // Игнорировать пробелы
row->DelimitedText = fileContent->Strings[i];
```

[(1) System.Classes.TStringList - RAD Studio API Documentation.](https://docwiki.embarcadero.com/Libraries/Sydney/en/System.Classes.TStringList) \
[(2) StrUtils.SplitString not working as expected - Stack Overflow.](https://stackoverflow.com/questions/35840707/strutils-splitstring-not-working-as-expected) \
[(3) System.SysUtils.TStringHelper.Split - RAD Studio API Documentation.](https://docwiki.embarcadero.com/Libraries/Alexandria/en/System.SysUtils.TStringHelper.Split) \
[(4) Split a string into an array of strings based on a delimiter.]( https://stackoverflow.com/questions/2625707/split-a-string-into-an-array-of-strings-based-on-a-delimiter) \
[(5) System.Classes.TStrings.LineBreak - RAD Studio API Documentation.](https://docwiki.embarcadero.com/Libraries/Sydney/en/System.Classes.TStrings.LineBreak)
- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->
<!--END_SECTION: C++-->

<!--BEGIN_SECTION: C#-->
# C#
<!--BEGIN-->
- - -
<!--END-->

<!--BEGIN-->
## C#. SQLite. Как сохранить БД из памяти в файл (на диск)
```C#
using (var destination = new SqliteConnection("Data Source=file.sqlite"))
{
    destination.Open();
    this.sqliteConnection.BackupDatabase(destination);
}
```
- - -
<!--END-->

<!--BEGIN-->
## C#. Вывод SQL запросов в консоль DbContext.cs

```csна 
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
        => optionsBuilder.UseSqlite(Program.connectionString)
           .LogTo(Console.WriteLine);//Вывод SQL запросов в консоль
```
- - -
<!--END-->

<!--BEGIN-->
## C#. Разница между reader.GetOrdinal("id") и reader.GetOrdinal("id")
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
- - -
<!--END-->

<!--BEGIN-->
## C#. Генерация GUID в Visual Studio. Hot keys
Нет одной универсальной комбинации горячих клавиш для генерации GUID, так как это зависит от того, какой инструмент или расширение ты используешь для этой цели. Но вот некоторые примеры, которые я нашел в интернете: \
•  Если ты используешь внешний инструмент PowerShell, как я описал ранее, то ты можешь назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда ->Клавиатура*, выбрав команду *Tools.ExternalCommandX*, где X - номер инструмента в списке https://www.tenforums.com/tutorials/130522-generate-globally-unique-identifier-guid-windows.html. \
•  Если ты используешь расширение Visual Commander, то ты можешь назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда ->Клавиатура*, выбрав команду VCmd.CommandX, где X - номер команды в списке https://stackoverflow.com/questions/58634771/generating-a-plain-guid-in-visual-studio. \
•  Если ты используешь окно C# Interactive, то ты можешь создать сниппет кода для генерации GUID и назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда ->Клавиатура*, выбрав команду *Edit.InvokeSnippetFromShortcut* https://bing.com/search?q=most+common+hotkey+for+generate+guid. \
•  Если ты используешь макрос для Visual Studio 2010 или более ранней версии, то ты можешь назначить ему любую свободную комбинацию горячих клавиш в меню *Инструменты -> Параметры -> Среда -> Клавиатура*, выбрав команду *Macros.MyMacros.Module1.CreateGUID*. Например, один из источников https://abhijitjana.net/2011/01/18/use-shortcut-key-to-generate-guid-very-quickly-in-visual-studio/ предлагает использовать Alt+G для этого макроса.
- - -
<!--END-->

<!--BEGIN-->
## C#. Получить список установленных версий .NET с помощью команды

dotnet --list-sdks
https://learn.microsoft.com/en-us/dotnet/core/tools/sdk-errors/netsdk1045
- - -
<!--END-->

<!--BEGIN-->
## C#. Как получить занчения поля по его имени? var reader = command.ExecuteReader();
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
- - -
<!--END-->

<!--BEGIN-->
## C#. Публикация в Telegram
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
- - -
<!--END-->

<!--BEGIN-->
## C#. Файл настроек приложения
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
- - -
<!--END-->

<!--BEGIN-->
## C#. Чтение JSON
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
- - -
<!--END-->

<!--BEGIN-->
## C#. Статический конструктор
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
- - -
<!--END-->

<!--BEGIN-->
## C#. Создание новой записи. PK ID.
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
- - -
<!--END-->

<!--BEGIN-->
## C#. Консольное приложение. Меню выбора
```cs
static void Main(string[] args)
{
    Console.WriteLine("Hello, World!");
    Console.Clear();

    int[] validChoices = { 1, 2, 3 };
    int choice = 0;
    bool validInput = false;

    while (!validInput)
    {
        Console.ForegroundColor = ConsoleColor.White;
        Console.WriteLine("Выберите метод для выполнения и нажмите Enter:");
        Console.WriteLine("1. ***");
        Console.WriteLine("2. ---");
        Console.WriteLine("3. Выход");

        string input = Console.ReadLine();

        if (int.TryParse(input, out choice))
        {
            if (Array.IndexOf(validChoices, choice) != -1)
            {
                validInput = true;
            }
            else
            {
                InvalidChoice();
            }
        }
        else
        {
            InvalidChoice();
        }
    }

    switch (choice)
    {
        case 1:
            func_01();
            break;
        case 2:
            func_02();
            break;
        case 3:
            Environment.Exit(0);
            break;
    }

    //Console.WriteLine("Goodbye, world!");
}

static void InvalidChoice()
{
    Console.ForegroundColor = ConsoleColor.Red;
    Console.WriteLine("Неверный выбор. Пожалуйста, повторите попытку.");
    Console.WriteLine("Для продолжения нажмите любую клавишу");
    Console.ReadKey();
    Console.Clear();
}
```
- - -
<!--END-->

<!--BEGIN-->
## C#. Async - Await
* [Async and Await in C#: Full Guide](https://www.bytehide.com/blog/async-await-csharp)
```C#
**class** Program
{
    static async Task Main(string[] args)
    {
        Console.WriteLine("Main Method Started......");
        Console.WriteLine("Before: Task<string> asdf = SomeMethod();");
        Task<string> someMethodResult = SomeMethod();
        Console.WriteLine("After: Task<string> asdf = SomeMethod();");
        await someMethodResult;
        Console.WriteLine($"result: {someMethodResult}"); ;
        Console.WriteLine("Main Method End");
    }
    public async static Task<string> SomeMethod()
    {
        Console.WriteLine("Some Method Started......");
        //Thread.Sleep(TimeSpan.FromSeconds(10));
        await Task.Delay(TimeSpan.FromSeconds(10));
        Console.WriteLine("\n");
        Console.WriteLine("Some Method End");

        return "text";
    }
}
```
- - -
<!--END-->

<!--BEGIN-->
## C#. SOLID
* [SOLID Principles in C#: A Complete Guide](https://www.bytehide.com/blog/solid-principles-in-csharp)
  
* [Youtube - The SOLID Principles - Klaus Iglberger - CppCon 2020](https://www.youtube.com/watch?v=Ntraj80qN2k)
- - -
<!--END-->

<!--BEGIN-->
## C#. Измерение времени работы Stopwatch()
```C#
        static void deltaTime()
        {
            // Создаем переменную BigInteger, которая содержит число длиной 128 знаков
            BigInteger n = BigInteger.Parse("1234567890");

            // Создаем объект Stopwatch для измерения времени выполнения операций
            Stopwatch sw = new Stopwatch();

            // Измеряем время выполнения операции извлечения корня
            sw.Start();
            bool root = BigInteger.IsPow2(n);
            sw.Stop();
            TimeSpan ts1 = sw.Elapsed; // Сохраняем затраченное время в переменную ts1
            sw.Reset(); // Сбрасываем счетчик времени

            Console.WriteLine($"timeSpan={ts1}");
        }
```
- - -
<!--END-->

<!--BEGIN-->
## C#. SeriLog. Ведение логов
**1. Конфигурирование лога в коде C#**\

* **yyyy-MM - dd HH: mm: ss.fff zzz** дата-время (до миллисекунд) и часовой пояс1.\
* **{Level: u3}** уровень лога(например, *INF* для *Information*, *ERR* для *Error*)\
* **{Message}** сообщение лога\
* **{NewLine}{Exception}** исключение, если оно есть

**.Enrich.FromLogContext()** в Serilog позволяет добавлять дополнительные свойства в логируемые сообщения из *LogContext*.\
```C#
string logFileName = Path.Combine(Environment.CurrentDirectory, logDir, "log.txt");
Log = new Serilog.LoggerConfiguration()
    .Enrich.FromLogContext()
    .WriteTo.File(logFileName,
                  outputTemplate: "{Timestamp:yyyy-MM-dd HH:mm:ss.fff zzz} [{Level:u3}] {Message}{NewLine}{Exception}"
                  )
    .WriteTo.Console()
    .CreateLogger();
```

**LogContext** - это статический класс, который позволяет создавать именованные и временные свойства, которые будут автоматически включены в все сообщения лога. Это может быть полезно, например, когда вы хотите включить некоторые свойства во все сообщения лога в рамках определенного блока кода.

```C#
using (LogContext.PushProperty("A", 1))
{
    Log.Information("Carries property A = 1");

    using (LogContext.PushProperty("A", 2))
    using (LogContext.PushProperty("B", 1))
    {
        Log.Information("Carries A = 2 and B = 1");
    }

    Log.Information("Carries property A = 1, again");
}
```
В этом примере первое и последнее сообщения будут содержать свойство A со значением 1, а второе сообщение будет содержать свойства A со значением 2 и B со значением 1.

**2. Конфигурирование лога в файле конфигурации appSettings.json**

**Вариант 1.** Простой
```JSON
{
  "Serilog": {
    "MinimumLevel": "Information",
    "WriteTo": [
      { "Name": "Console" },
      {
        "Name": "File",
        "Args": {
          "path": "log.txt",
          "outputTemplate": "{Timestamp:yyyy-MM-dd HH:mm:ss.fff zzz} [{Level:u3}] {Message}{NewLine}{Exception}"
        }
      }
    ]
  }
}
```

**Вариант 2:** Разные уровни сообщений для консоли и файлов
```JSON
  "Serilog": {
    "WriteTo": [
      {
        "Name": "Console",
        "Args": {
          "restrictedToMinimumLevel": "Information"
        }
      },
      {
        "Name": "File",
        "Args": {
          "path": "log_info.txt",
          "restrictedToMinimumLevel": "Information",
          "outputTemplate": "{Timestamp:yyyy-MM-dd HH:mm:ss.fff zzz} [{Level:u3}] {Message}{NewLine}{Exception}"
        }
      },
      {
        "Name": "File",
        "Args": {
          "path": "log_error.txt",
          "restrictedToMinimumLevel": "Error",
          "outputTemplate": "{Timestamp:yyyy-MM-dd HH:mm:ss.fff zzz} [{Level:u3}] {Message}{NewLine}{Exception}"
        }
      }
    ]
  }
```

```C#
// Загрузка конфигурации Serilog
// Должен быть установлен пакет: Serilog.Settings.Configuration
var configuration = new ConfigurationBuilder()
    .SetBasePath(Directory.GetCurrentDirectory())
    .AddJsonFile("appsettings.json")
    .Build();

Log.Logger = new LoggerConfiguration()
    .ReadFrom.Configuration(configuration)
    .CreateLogger();
```
- - -
<!--END-->

<!--BEGIN-->
# C#. Файлы конфигурации приложения
В .NET Core вы можете использовать библиотеку, такую как **Microsoft.Extensions.Configuration.CommandLine**, чтобы легко обрабатывать именованные аргументы командной строки.
```C#
//myApp.exe --settings:FileName=appsettings.Production.json
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureAppConfiguration((hostingContext, config) =>
        {
            config.AddCommandLine(args);
        })
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```
- - -
<!--END-->

<!--BEGIN-->
## C#. OpenSSL
https://www.openssl.org/source/

Создание самоподписанного сертификата:

С помощью OpenSSL:
openssl req -newkey rsa:2048 -nodes -keyout localhost.key -x509 -days 365 -out localhost.crt

С помощью .NET CLI:
dotnet dev-certs https --trust

- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->

<!--END_SECTION: C#-->

<!--BEGIN_SECTION: SQLite-->
# SQLite
<!--BEGIN-->
## SQLite. Автоинкремент SQLite

**Резюме:** \
Ключевое слово AUTOINCREMENT накладывает дополнительную нагрузку на ЦП, память, дисковое пространство и дисковый ввод-вывод, и его следует избегать, если это не является строго необходимым. Обычно это не требуется.

В SQLite столбец с типом INTEGER PRIMARY KEY является псевдонимом для ROWID (за исключением таблиц WITHOUT ROWID ), который всегда представляет собой 64-битное целое число со знаком.

В INSERT , если столбцу ROWID или INTEGER PRIMARY KEY явно не задано значение, оно будет автоматически заполнено неиспользуемым целым числом, обычно на единицу больше, чем самый большой ROWID, используемый в настоящее время. Это верно независимо от того, используется ли ключевое слово AUTOINCREMENT.

Если ключевое слово AUTOINCREMENT появляется после INTEGER PRIMARY KEY, это изменяет алгоритм автоматического назначения ROWID, чтобы предотвратить повторное использование ROWID в течение всего срока службы базы данных. Другими словами, целью AUTOINCREMENT является предотвращение повторного использования ROWID из ранее удаленных строк.

[Источник](https://www.sqlite.org/autoinc.html)
- - -
<!--END-->

<!--BEGIN-->
## SQLite. Если базе данных SQLite поле PK имеет тип INTEGER, то какой тип должно быть у свойства Id?
**Ответ:** long \
**Вопрос:** Почему long, а не int? \
**Ответ:** Потому что в SQLite тип INTEGER имеет диапазон значений от -9223372036854775808 до +9223372036854775807 \
- - -
<!--END-->

<!--END_SECTION: SQLite-->

# SQL
<!--BEGIN-->
- - -
<!--END-->

<!--BEGIN-->
## SQL. Use Cases for Non-Equi JOINs (неравноправные соединения)
https://learnsql.com/blog/sql-non-equi-joins-examples/
- - -
<!--END-->

## SQL. Декартов взрыв. Картезианский взрыв. Выбор названия
Декартов взрыв и картезианский взрыв - это два термина, которые используются для описания проблемы производительности, возникающей при выполнении запросов SQL с использованием оператора JOIN. Эта проблема заключается в том, что при объединении двух или более таблиц с большим количеством строк результат может содержать слишком много строк, которые не нужны для решения задачи. Это приводит к избыточности данных, замедлению обработки и потере ресурсов.

Эти термины связаны с понятием декартова произведения, которое названо в честь французского философа и математика Рене Декарта https://en.wikipedia.org/wiki/Cartesian_product. Декартово произведение двух множеств A и B - это множество всех упорядоченных пар (a,b), где a принадлежит A, а b принадлежит B. Например, декартово произведение множеств {1,2} и {a,b} равно {(1,a), (1,b), (2,a), (2,b)}. Декартово произведение используется для определения координат точек на плоскости, а также для представления отношений в теории баз данных.

Декартов взрыв - это ситуация, когда результат JOIN является декартовым произведением двух таблиц, то есть содержит все возможные комбинации строк из этих таблиц. Это происходит, когда в условии JOIN не указано никаких критериев сопоставления строк или когда эти критерии не выполняются ни для одной пары строк. Например, если мы хотим объединить таблицы Customers и Orders по полю CustomerID, но забудем указать это поле в условии JOIN, то мы получим декартово произведение:

```sql
SELECT * FROM Customers CROSS JOIN Orders;
```
CustomerID | CustomerName | OrderID | OrderDate
-----------|--------------|---------|----------
1          | Alice        | 1       | 2023-01-01
1          | Alice        | 2       | 2023-01-02
1          | Alice        | 3       | 2023-01-03
2          | Bob          | 1       | 2023-01-01
2          | Bob          | 2       | 2023-01-02
2          | Bob          | 3       | 2023-01-03
3          | Charlie      | 1       | 2023-01-01
3          | Charlie      | 2       | 2023-01-02
3          | Charlie      | 3       | 2023-01-03

Как видим, каждый заказ повторяется для каждого клиента, хотя на самом деле каждый заказ принадлежит только одному клиенту. Это явно не то, что мы хотели получить. Чтобы избежать декартова взрыва, нам нужно указать условие JOIN по полю CustomerID:

```sql
SELECT * FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
Результат:
CustomerID | CustomerName | OrderID | OrderDate
-----------|--------------|---------|----------
1          | Alice        | 1       | 2023-01-01
2          | Bob          | 2       | 2023-01-02
3          | Charlie      | 3       | 2023-01-03

Теперь мы получаем только те строки, которые соответствуют нашей задаче.

Название декартов взрыв отражает тот факт, что результат JOIN взрывается в размерах, становясь слишком большим и бесполезным. Это напоминает физический взрыв, когда материя распадается на множество мелких частиц.

Картезианский взрыв - это ситуация, когда результат JOIN не является декартовым произведением, но всё равно содержит слишком много строк из-за того, что в условии JOIN используются поля с низкой кардинальностью или неточные критерии сопоставления. Например, если мы хотим объединить таблицы Customers и Orders по полю Country, то мы получим следующий результат:

```sql
SELECT * FROM Customers INNER JOIN Orders ON Customers.Country = Orders.Country;
```
Результат:
CustomerID | CustomerName | Country   | OrderID | OrderDate  | Country
-----------|--------------|-----------|---------|------------|---------
1          | Alice        | USA       | 1       | 2023-01-01 | USA
1          | Alice        | USA       | 4       | 2023-01-04 | USA
2          | Bob          | UK        | 2       | 2023-01-02 | UK
2          | Bob          | UK        | 5       | 2023-01-05 | UK
3          | Charlie      | Australia | 3       | 2023-01-03 | Australia
3          | Charlie      | Australia | 6       | 2023-01-06 | Australia

Как видим, каждый заказ повторяется для каждого клиента из той же страны, хотя на самом деле каждый заказ принадлежит только одному клиенту. Это также не то, что мы хотели получить. Чтобы избежать картезианского взрыва, нам нужно использовать более точные критерии сопоставления, например, по полю CustomerID:

```sql
SELECT * FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
Результат:
CustomerID | CustomerName | Country   | OrderID | OrderDate  | Country
-----------|--------------|-----------|---------|------------|---------
1          | Alice        | USA       | 1       | 2023-01-01 | USA
2          | Bob          | UK        | 2       | 2023-01-02 | UK
3          | Charlie      | Australia | 3       | 2023-01-03 |

Теперь мы получаем только те строки, которые соответствуют нашей задаче.

Название картезианский взрыв отражает тот факт, что результат JOIN увеличивается в размерах, становясь слишком большим и избыточным. Это напоминает геометрический рост, когда количество элементов удваивается или утраивается при каждом шаге.

Cartesian product - Wikipedia: https://en.wikipedia.org/wiki/Cartesian_product
- - -
<!--END-->

<!--BEGIN-->
## SQL. Декартов взрыв. Картезианский взрыв. Создание таблиц и их заполнение

Создание таблиц Customers и Orders:

```sql
-- Создание таблицы Customers
CREATE TABLE Customers (
CustomerID INT PRIMARY KEY,
CustomerName VARCHAR(50) NOT NULL,
Country VARCHAR(50) NOT NULL
);

-- Создание таблицы Orders
CREATE TABLE Orders (
OrderID INT PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INT NOT NULL,
Country VARCHAR(50) NOT NULL,
FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);

--Для заполнения таблиц Customers и Orders я использовал следующий скрипт SQL:
-- Заполнение таблицы Customers
INSERT INTO Customers (CustomerID, CustomerName, Country) VALUES
(1, 'Alice', 'USA'),
(2, 'Bob', 'UK'),
(3, 'Charlie', 'Australia');

-- Заполнение таблицы Orders
INSERT INTO Orders (OrderID, OrderDate, CustomerID, Country) VALUES
(1, '2023-01-01', 1, 'USA'),
(2, '2023-01-02', 2, 'UK'),
(3, '2023-01-03', 3, 'Australia'),
(4, '2023-01-04', 2, 'USA'),
(5, '2023-01-05', 3, 'UK'),
(6, '2023-01-06', 1, 'Australia');

--После выполнения этих скриптов вы можете проверить содержимое таблиц с помощью следующих запросов:

-- Проверка содержимого таблицы Customers
SELECT * FROM Customers;

-- Проверка содержимого таблицы Orders
SELECT * FROM Orders;
Вы также можете повторить мои примеры запросов с использованием оператора JOIN и увидеть результаты:

-- Пример запроса с декартовым взрывом
SELECT * FROM Customers CROSS JOIN Orders;

-- Пример запроса с картезианским взрывом
SELECT * FROM Customers INNER JOIN Orders ON Customers.Country = Orders.Country;

-- Пример правильного запроса с условием JOIN по полю CustomerID
SELECT * FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
- - -
<!--END-->

<!--BEGIN-->
## SQL. Декартов взрыв. Картезианский взрыв.

Декартов взрыв и картезианский взрыв - это два термина, которые используются для описания проблемы производительности, возникающей при выполнении запросов SQL с использованием оператора JOIN. Эта проблема заключается в том, что при объединении двух или более таблиц с большим количеством строк результат может содержать слишком много строк, которые не нужны для решения задачи. Это приводит к избыточности данных, замедлению обработки и потере ресурсов.

Декартов взрыв - это ситуация, когда результат JOIN является декартовым произведением двух таблиц, то есть содержит все возможные комбинации строк из этих таблиц. Это происходит, когда в условии JOIN не указано никаких критериев сопоставления строк или когда эти критерии не выполняются ни для одной пары строк. Например, если мы хотим объединить таблицы Customers и Orders по полю CustomerID, но забудем указать это поле в условии JOIN, то мы получим декартово произведение:

```sql
SELECT * FROM Customers CROSS JOIN Orders;
```
Результат:
CustomerID | CustomerName | OrderID | OrderDate
-----------|--------------|---------|----------
1          | Alice        | 1       | 2023-01-01
1          | Alice        | 2       | 2023-01-02
1          | Alice        | 3       | 2023-01-03
2          | Bob          | 1       | 2023-01-01
2          | Bob          | 2       | 2023-01-02
2          | Bob          | 3       | 2023-01-03
3          | Charlie      | 1       | 2023-01-01
3          | Charlie      | 2       | 2023-01-02
3          | Charlie      | 3       | 2023-01-03

Как видим, каждый заказ повторяется для каждого клиента, хотя на самом деле каждый заказ принадлежит только одному клиенту. Это явно не то, что мы хотели получить. Чтобы избежать декартова взрыва, нам нужно указать условие JOIN по полю CustomerID:

```sql
SELECT * FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
Результат:
CustomerID | CustomerName | OrderID | OrderDate
-----------|--------------|---------|----------
1          | Alice        | 1       | 2023-01-01
2          | Bob          | 2       | 2023-01-02
3          | Charlie      | 3       | 2023-01-03

Теперь мы получаем только те строки, которые соответствуют нашей задаче.

Картезианский взрыв - это ситуация, когда результат JOIN не является декартовым произведением, но всё равно содержит слишком много строк из-за того, что в условии JOIN используются поля с низкой кардинальностью или неточные критерии сопоставления. Например, если мы хотим объединить таблицы Customers и Orders по полю Country, то мы получим следующий результат:

```sql
SELECT * FROM Customers INNER JOIN Orders ON Customers.Country = Orders.Country;
```
Результат:
CustomerID | CustomerName | Country   | OrderID | OrderDate  | Country
-----------|--------------|-----------|---------|------------|---------
1          | Alice        | USA       | 1       | 2023-01-01 | USA
1          | Alice        | USA       | 4       | 2023-01-04 | USA
2          | Bob          | UK        | 2       | 2023-01-02 | UK
2          | Bob          | UK        | 5       | 2023-01-05 | UK
3          | Charlie      | Australia | 3       | 2023-01-03 | Australia
3          | Charlie      | Australia | 6       | 2023-01-06 | Australia

Как видим, каждый заказ повторяется для каждого клиента из той же страны, хотя на самом деле каждый заказ принадлежит только одному клиенту. Это также не то, что мы хотели получить. Чтобы избежать картезианского взрыва, нам нужно использовать более точные критерии сопоставления, например, по полю CustomerID:

```sql
SELECT * FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```
Результат:
CustomerID | CustomerName | Country   | OrderID | OrderDate  | Country
-----------|--------------|-----------|---------|------------|---------
1          | Alice        | USA       | 1       | 2023-01-01 | USA
2          | Bob          | UK        | 2       | 2023-01-02 | UK
3          | Charlie      | Australia | 3       | 2023-01-03 | Australia

Теперь мы получаем только те строки, которые соответствуют нашей задаче.
- - -
<!--END-->

# EF Core
<!--BEGIN-->
## EF Core. scaffold-DbContext
**ВОПРОС**: C#. Дай подробные объяснения этой строке генерации классов на основании базы данных:
*scaffold-DbContext "Строка подключения" Microsoft.EntityFrameworkCore.SqlServer -ContextDir Data -OutputDir Models\Generated -DataAnnotation -ContextNamespace ContosoPissa.Data -Namespace ContosoPizza.Models*

**ОТВЕТ**:  Строка scaffold-DbContext "Строка подключения" Microsoft.EntityFrameworkCore.SqlServer -ContextDir Data -OutputDir Models\Generated -DataAnnotation -ContextNamespace ContosoPissa.Data -Namespace ContosoPizza.Models означает, что вы хотите сгенерировать код для класса DbContext и классов сущностей для базы данных, используя команду scaffold-DbContext из EF Core Package Manager Console (PMC) tools. Давайте разберемся, что означают каждый параметр этой команды:

•  **"Строка подключения"**: это строка, которая содержит информацию о том, как подключиться к базе данных, которую вы хотите использовать. Она может включать в себя имя сервера, имя базы данных, учетные данные пользователя и другие настройки. Например, "Server=(localdb)\mssqllocaldb;Database=ContosoPizza;Trusted_Connection=True;".

•  **Microsoft.EntityFrameworkCore.SqlServer**: это имя провайдера базы данных, который вы хотите использовать. В этом случае вы используете SQL Server, который является одним из самых популярных и мощных реляционных СУБД. EF Core поддерживает множество других провайдеров, таких как SQLite, PostgreSQL, Oracle и другие https://learn.microsoft.com/en-us/ef/core/managing-schemas/scaffolding/.

•  **-ContextDir Data**: это параметр, который указывает папку, в которой будет создан файл с классом DbContext. Класс DbContext представляет собой основной класс EF Core, который отвечает за взаимодействие с базой данных и отслеживание изменений в объектах сущностей. В этом случае файл будет создан в папке Data, которая должна находиться в корневой папке вашего проекта.

•  **-OutputDir Models\Generated**: это параметр, который указывает папку, в которой будут созданы файлы с классами сущностей. Классы сущностей представляют собой классы C#, которые соответствуют таблицам и столбцам в базе данных. Они используются для представления и манипулирования данными в коде. В этом случае файлы будут созданы в папке Models\Generated, которая должна находиться в корневой папке вашего проекта.

•  **-DataAnnotation**: это параметр, который указывает, что вы хотите использовать атрибуты C# для настройки классов сущностей. Атрибуты C# позволяют добавлять метаданные к классам и свойствам, которые могут быть использованы EF Core для определения отношений, ограничений, индексов и других аспектов модели данных. Например, [Key] атрибут указывает, что свойство является первичным ключом таблицы https://stackoverflow.com/questions/40381295/scaffolding-existing-databases-in-asp-net-core-scaffold-dbcontext.

•  **-ContextNamespace ContosoPissa.Data**: это параметр, который указывает пространство имен для класса DbContext. Пространство имен - это способ организации классов по группам или категориям. Оно помогает избежать конфликтов имен и упрощает доступ к классам из других частей кода. В этом случае пространство имен будет ContosoPissa.Data.

•  **-Namespace ContosoPizza.Models**: это параметр, который указывает пространство имен для классов сущностей. В этом случае пространство имен будет ContosoPizza.Models.

Я надеюсь, что это объяснило вам смысл строки генерации классов на основании базы данных. Если у вас есть еще какие-то вопросы о C# или других темах, я буду рад ответить на них. blush
- - -
<!--END-->

<!--BEGIN-->
## EF Core. scaffold-DbContext. Пространство имен -ContextNamespace и  -Namespace
**ВОПРОС:** В чем приемущество разделения этих пространств имен:
-ContextNamespace и  -Namespace ? \

**ОТВЕТ:** Преимущество разделения этих пространств имен заключается в том, что вы можете лучше организовать и структурировать свой код, а также избежать возможных конфликтов имен между классами. Давайте рассмотрим это подробнее.

•  **-ContextNamespace** указывает пространство имен для класса DbContext, который является основным классом EF Core, отвечающим за взаимодействие с базой данных и отслеживание изменений в объектах сущностей. Обычно, класс DbContext находится в отдельной папке, например Data, и имеет свое собственное пространство имен, например ContosoPizza.Data. Это помогает отделить логику доступа к данным от других частей приложения, таких как контроллеры, представления, сервисы и т.д. Также, это позволяет легко настроить и зарегистрировать класс DbContext в контейнере зависимостей приложения, используя метод .AddDbContext<TContext> .

•  **-Namespace** указывает пространство имен для классов сущностей, которые представляют таблицы и столбцы в базе данных. Обычно, классы сущностей находятся в другой папке, например Models, и имеют свое собственное пространство имен, например ContosoPizza.Models. Это помогает отделить модель данных от других частей приложения, таких как бизнес-логика, валидация, маппинг и т.д. Также, это позволяет легко использовать классы сущностей в других слоях приложения, таких как репозитории, сервисы, контроллеры и т.д., используя директиву using .

Разделение пространств имен для класса DbContext и классов сущностей также помогает избежать конфликтов имен между классами, которые могут иметь одинаковые или похожие названия. Например, если вы имеете таблицу Order в базе данных, то вы можете сгенерировать класс сущности Order в пространстве имен ContosoPizza.Models. Однако, если вы также имеете контроллер OrderController в вашем приложении, то вы можете поместить его в другое пространство имен, например ContosoPizza.Controllers. Тогда вы сможете использовать оба класса без конфликтов, указывая полное имя класса или добавляя директиву using для нужного пространства имен .
- - -
<!--END-->

<!--BEGIN-->

<!--BEGIN-->
## EF Core. scaffold-DbContext. Ключ -DataAnnotation
**ВОПРОС:** В чем приемущество  использования ключа  -DataAnnotation? В каких случаях рекомендуется его использовать, а в каких не рекомендуется? Приведи примеры

**ОТВЕТ:** **Data Annotations** - это атрибуты C#, которые позволяют настраивать модель классов, добавляя метаданные к классу и его свойствам. EF Core распознает эти атрибуты и использует их для конфигурации модели. Преимущество использования Data Annotations заключается в том, что вы можете легко и наглядно указать EF Core, как вы хотите отображать свои классы на таблицы и столбцы в базе данных, а также как вы хотите определять отношения, ограничения, индексы и другие аспекты модели данных. Data Annotations также понятны другими фреймворками .NET, такими как ASP.NET Core MVC, которые позволяют использовать эти же атрибуты для клиентской валидации.

Однако, Data Annotations имеют и некоторые недостатки. Они не могут покрыть все сценарии конфигурации, которые поддерживает EF Core, и иногда требуют более сложного синтаксиса, чем Fluent API. Например, Data Annotations не могут настроить каскадное удаление или фильтры запросов. Также, Data Annotations привязывают вашу модель к EF Core, что может нарушить принцип разделения ответственности и усложнить тестирование или переиспользование модели в других контекстах.

Поэтому, рекомендуется использовать Data Annotations в тех случаях, когда вы хотите быстро и просто настроить свою модель, не затрагивая сложные или специфичные для EF Core сценарии. Например, вы можете использовать Data Annotations для указания первичного ключа, обязательности, длины, имени таблицы или столбца, внешнего ключа или обратной связи. Вот несколько примеров использования Data Annotations:

```cs
//•  Для указания первичного ключа, вы можете использовать атрибут [Key] на свойстве класса. Например:
public class Blog
{
[Key]
public int BlogId { get; set; }
// ...
}

//•  Для указания обязательности свойства, вы можете использовать атрибут [Required] на свойстве класса. Например:
public class Post
{
public int PostId { get; set; }

[Required]
public string Title { get; set; }
// ...
}

//•  Для указания длины свойства, вы можете использовать атрибуты [MaxLength] или [MinLength] на свойстве класса. Например:
public class Comment
{
public int CommentId { get; set; }

[MaxLength(200)]
public string Content { get; set; }
// ...
}

//•  Для указания имени таблицы или столбца, вы можете использовать атрибуты [Table] или [Column] на классе или свойстве соответственно. Например:
[Table("Blogs")]
public class Blog
{
public int BlogId { get; set; }

[Column("BlogName")]
public string Name { get; set; }
// ...
}

//•  Для указания внешнего ключа или обратной связи, вы можете использовать атрибуты [ForeignKey] или [InverseProperty] на свойстве класса. Например:
public class Post
{****
public int PostId { get; set; }

[ForeignKey("Blog")]
public int BlogId { get; set; }

[InverseProperty("Posts")]
public Blog Blog { get; set; }
// ...
}
```
- - -
<!--END-->

<!--BEGIN-->
## EF Core. scaffold-DbContext. Будет ли с ключем -Data Annotations по умолчанию работать каскадное удаление?

С ключом -Data Annotations по умолчанию каскадное удаление **работать будет**, но только для **обязательных** связей, то есть тех, где свойство внешнего ключа не может быть null. Для **необязательных** связей, то есть тех, где свойство внешнего ключа может быть null, по умолчанию будет использоваться поведение **ClientSetNull**, которое устанавливает значение внешнего ключа в null, а не удаляет зависимые сущности \
https://learn.microsoft.com/en-us/ef/core/saving/cascade-delete.

Например, если у вас есть такая модель:
```cs
public class Blog
{
public int Id { get; set; }
public string Name { get; set; }
public IList<Post> Posts { get; } = new List<Post> ();
}

public class Post
{
public int Id { get; set; }
public string Title { get; set; }
public string Content { get; set; }
public int BlogId { get; set; }
public Blog Blog { get; set; }
}
```
То по умолчанию EF Core сконфигурирует эту связь как обязательную, так как свойство Post.BlogId не может быть null. Это означает, что при удалении блога все его посты также будут удалены из базы данных. Это поведение называется **Cascade**.

Однако, если вы измените тип свойства Post.BlogId на int?, то EF Core сконфигурирует эту связь как необязательную, так как свойство Post.BlogId теперь может быть null. Это означает, что при удалении блога все его посты не будут удалены из базы данных, а их свойства Post.BlogId будут установлены в null. Это поведение называется **ClientSetNull**.

Вы можете изменить поведение удаления для любой связи, используя Fluent API или Data Annotations. С помощью Fluent API вы можете использовать метод .OnDelete для указания желаемого поведения. \
Например:
```cs
modelBuilder.Entity<Post>()
.HasOne(p => p.Blog)
.WithMany(b => b.Posts)
.OnDelete(DeleteBehavior.Cascade); // or any other behavior
```

С помощью Data Annotations вы можете использовать атрибут [Required] для указания обязательности связи. Если вы добавите этот атрибут к навигационному свойству или к свойству внешнего ключа, то EF Core сконфигурирует связь как обязательную и применит к ней поведение **Cascade**. Например:
```cs
public class Post
{
public int Id { get; set; }
public string Title { get; set; }
public string Content { get; set; }

[Required] // this makes the relationship required and cascade delete enabled
public int? BlogId { get; set; }

[Required] // this also makes the relationship required and cascade delete enabled
public Blog Blog { get; set; }
}
```
Если вы не добавите атрибут [Required] к навигационному свойству или к свойству внешнего ключа, то EF Core сконфигурирует связь как необязательную и применит к ней поведение **ClientSetNull**.
- - -
<!--END-->

# Razor pages
<!--BEGIN-->
 ## Razor pages. Библиотеки визуальных компонентов
•  **Blazorise**: это кроссплатформенная библиотека компонентов для Blazor и Razor Pages, которая поддерживает различные фреймворки CSS, такие как Bootstrap, Bulma и Ant Design https://learn.microsoft.com/ru-ru/aspnet/core/blazor/components/?view=aspnetcore-7.0.

•  **MatBlazor**: это библиотека компонентов для Blazor и Razor Pages, которая реализует принципы дизайна Material Design https://learn.microsoft.com/ru-ru/training/modules/create-razor-pages-aspnet-core/.

•  **Syncfusion Blazor UI Components**: это библиотека профессиональных компонентов для Blazor и Razor Pages, которая предлагает более 70 высокопроизводительных и адаптивных компонентов https://learn.microsoft.com/ru-ru/aspnet/core/mvc/views/razor?view=aspnetcore-7.0.
- - -
<!--END-->

 <!--BEGIN-->
 ## Razor Pages. Как можно ограничить число знаков после запятой? <input asp-for="value" class="form-control" type=". . .

Согласно документации Microsoft https://stackoverflow.com/questions/14727979/how-to-allow-only-numbers-in-textbox-in-mvc4-razor, вы можете использовать атрибут asp-format для задания формата для ввода чисел в текстовое поле. Например, asp-format="{0:F2}" ограничит число двумя знаками после запятой. Вы также можете использовать атрибут type для задания типа ввода, например type="number" для ввода только чисел https://www.learnrazorpages.com/razor-pages/tag-helpers/input-tag-helper. \

Например:
```html
<input asp-for="value" class="form-control" type="number" asp-format="{0:F2}" />
```
Этот код сгенерирует следующий HTML:
```html
<input class="form-control" type="number" data-val="true" id="value" name="value" value="" />
```
- - -
<!--END-->

<!--BEGIN-->
## Razor Pages. Ввод даты-времени, даты

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
- - -
<!--END-->

<!--Begin_SECTION: Blazor-->
# Blazor
<!--BEGIN-->
## Blazor. .Net8 изменения
https://www.telerik.com/blogs/big-changes-coming-blazor-dotnet-8
- - -
<!--END-->

<!--BEGIN-->
## Blazor. Linux. Консольное приложение
**ВОПРОС:** Уточню вопрос. Пусть будет консольное приложение, в котором будет запускаться Web server Kestrel, на котором будет запскаться  ASP.NET Core или Blazor WebAssembly

**ОТВЕТ:**
Я понимаю ваш вопрос. Да, можно сделать консольное приложение, в котором будет запускаться веб-сервер Kestrel, на котором будет работать ASP.NET Core или Blazor WebAssembly. Для этого вам нужно выполнить следующие шаги:

•  Создайте консольное приложение .NET Core с помощью команды dotnet new console.

•  Добавьте пакеты NuGet для ASP.NET Core и Blazor WebAssembly с помощью команд dotnet add package Microsoft.AspNetCore.App и dotnet add package Microsoft.AspNetCore.Components.WebAssembly.Server.

•  В файле Program.cs добавьте код для создания и запуска хоста веб-приложения с помощью класса WebHostBuilder. Например:
```cs
using System;
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.Hosting;

namespace ConsoleApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Создаем хост веб-приложения
            var host = new WebHostBuilder()
            .UseKestrel() // Указываем, что используем Kestrel в качестве веб-сервера
            .UseStartup<Startup>() // Указываем класс Startup для конфигурации приложения
            .Build(); // Строим хост

            // Запускаем хост веб-приложения
            host.Run();
        }
    }
}
```

•  В файле Startup.cs добавьте код для настройки конвейера запросов и служб приложения с помощью классов IServiceCollection и IApplicationBuilder. Например:
```cs
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.DependencyInjection;

namespace ConsoleApp
{
    public class Startup
    {
        public void ConfigureServices(IServiceCollection services)
        {
            // Добавляем службы для Blazor WebAssembly
            services.AddBlazorFrameworkFiles();
            services.AddRazorPages();
        }

        public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
        {
            // Добавляем промежуточное ПО для обработки статических файлов и запросов к Blazor WebAssembly
            app.UseStaticFiles();
            app.UseBlazorFrameworkFiles();
            app.UseRouting();
            app.UseEndpoints(endpoints =>
            {
                endpoints.MapRazorPages(); // Маршрутизируем запросы к Razor Pages
                endpoints.MapFallbackToFile("index.html"); // Перенаправляем все остальные запросы к файлу index.html, где загружается Blazor WebAssembly
            });
        }
    }
}
```
•  В папке wwwroot создайте файл index.html, который будет содержать код для загрузки Blazor WebAssembly. Например:
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>Console App with Blazor WebAssembly</title>
        <base href="/" />
    </head>
    <body>
        <div id="app">Loading...</div>

        <!-- Загружаем Blazor WebAssembly из пакета NuGet -->
        <script src="_framework/blazor.webassembly.js"></script>
    </body>
</html>
```
•  В папке Pages создайте файлы Razor (.cshtml), которые будут содержать код для отображения компонентов Blazor WebAssembly. Например, создайте файл Index.cshtml с таким содержанием:
```html
@page "/"

<h1>Hello, world!</h1>

Welcome to your new app.

<SurveyPrompt Title="How is Blazor working for you?" />
```
•  Скомпилируйте и запустите консольное приложение с помощью команды dotnet run.

•  Откройте браузер и перейдите по адресу http://localhost:5000, где вы увидите ваше приложение с Blazor WebAssembly.

Вы можете узнать больше о том, как создавать и развертывать приложения ASP.NET Core и Blazor WebAssembly на Linux в статьях:
1) Размещение ASP.NET Core в операционной системе Linux с Nginx https://learn.microsoft.com/ru-ru/aspnet/core/host-and-deploy/linux-nginx?view=aspnetcore-7.0 \
2) Размещение ASP.NET Core в операционной системе Linux с Apache https://learn.microsoft.com/ru-ru/aspnet/core/host-and-deploy/linux-apache?view=aspnetcore-7.0. Также вы можете посмотреть примеры кода для консольных приложений с Kestrel на Stack Overflow https://stackoverflow.com/questions/60090732/net-core-linux-kestrel-https-configuration.
- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->
<!--End_SECTION: Blazor-->


<!--Begin_SECTION: React-->

# React
<!--BEGIN-->
## React. TypeScript
**TypeScript шпаргалка:** https://www.dev-notes.ru/articles/typescript/typescript-cheatsheet/ \
(*Источник Eng:* https://cs.fyi/guide/typescript-cheatsheet)
- - -
<!--END-->

<!--BEGIN-->
## React. Npm

*System > About > Advanced system settings > Enviroment Variables > System Variables > Path* \
ИЛИ \
*Start > Edit the system environment variables*

**Добавить путь к каталогу:**
* C:\Program Files\Microsoft Visual Studio\2022\Community\MSBuild\Microsoft\VisualStudio\NodeJs
* C:\Program Files\nodejs
- - -
<!--END-->

<!--BEGIN-->
## React. Ошибка при создании проекта React:
NPX no such file or directory, lstat 'C:\Users\<user>\AppData\Roaming\npm'
Node.js/Windows error: ENOENT, stat 'C:\Users\RT\AppData\Roaming\npm'
* https://www.youtube.com/watch?v=UwY6U7L10lg \
* https://stackoverflow.com/questions/25093276/node-js-windows-error-enoent-stat-c-users-rt-appdata-roaming-npm

 **Решение:** npm install npm -g
- - -
<!--END-->

<!--BEGIN-->
## React. Создание приложения
**Terminal:** node -v\
**Расширение для форматирования кода:** Prettier - Code format \
**Форматирование при сохранении:** Preferences: Open User Settings ===> Format On Save \

**Создание приложения:**
* Create React APP (CRA)
* Vite
    * Terminal: **npm create vite@latest** ( npm create vite@4.1.0 )
    * Project name: react-app
    * Select a framework
    * Terminal: **cd react-app** (Переходим в каталог)
    * Terminal: **npm install** (npm i)
    * Terminal: **code .** (Открытие каталога в VS)
    * Terminal: **npm run dev** (Запуск проекта)
- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->

<!--BEGIN-->
- - -
<!--END-->

<!--End_SECTION: React-->

<!--Begin_SECTION: PostgreSQL-->
# PostgreSQL
## PostgreSQL. Создание и конфигури БД
**Создание БД**
```cmd
echo off

set PATH_BIN=C:\DataBase_00\pgsql\bin
set PATH_DB_=C:\DataBase_00\DB_PostgreSQL_00
set FILE_PASSWORD=!_(0)_Password.txt
set FILE_LOG=!_(5)_Log_Create_DB.txt
del "%FILE_LOG%"

rem initdb.exe [ПАРАМЕТР]... [КАТАЛОГ]

rem https://postgrespro.ru/docs/postgresql/15/app-initdb
rem [-D, --pgdata=]КАТАЛОГ     расположение данных этого кластера БД
rem --pgdata=каталог

rem  -E, --encoding=КОДИРОВКА  кодировка по умолчанию для новых баз

rem -U, --username=ИМЯ имя суперпользователя БД
rem -W, --pwprompt     запросить пароль суперпользователя

rem -A, --auth=МЕТОД метод проверки подлинности по умолчанию для локальных подключений

rem --locale=ЛОКАЛЬ локаль по умолчанию для новых баз
rem https://postgrespro.ru/docs/postgresql/15/locale

rem -E 'UTF-8' --lc-collate='ru_RU.UTF-8' --lc-ctype='ru_RU.UTF-8'
rem --locale='ru_RU.UTF-8' --encoding='UTF-8'

"%PATH_BIN%\initdb.exe" --pgdata="%PATH_DB_%" --username=postgres --pwfile="%FILE_PASSWORD%" --locale=ru_RU.UTF-8 --encoding=UTF-8 --auth=trust >"%FILE_LOG%"
```

**Запуск БД**
```cmd
echo off

set PATH_BIN=C:\DataBase_00\pgsql\bin
set PATH_DB_=C:\DataBase_00\DB_PostgreSQL_00

"%PATH_BIN%\pg_ctl.exe" start  -D "%PATH_DB_%" -l Log_PostgreSQL.txt
```

**Остановка БД**
```cmd
set PATH_BIN=C:\DataBase_00\pgsql\bin
set PATH_DB_=C:\DataBase_00\DB_PostgreSQL_00

"%PATH_BIN%\pg_ctl.exe" stop  -D "%PATH_DB_%" -l Log_PostgreSQL.txt
```

**Статус**
```cmd
set PATH_BIN=C:\DataBase_00\pgsql\bin
set PATH_DB_=C:\DataBase_00\DB_PostgreSQL_00

"%PATH_BIN%\pg_ctl.exe" status -D "%PATH_DB_%"
```

**Конфигурирование доступа к БД**
1) **postgresql.conf**:
```bush
listen_addresses = '*' # what IP address(es) to listen on;
```
2) **pg_hba.conf**:
* *trust* - без пароля
* *password* - досутп по паролю
```bash
# TYPE  DATABASE        USER            ADDRESS                 METHOD
host    all             all             127.0.0.1/32            password
local   all             all                                     trust
host   all              all             111.111.111.111/32        password
```
<!--End_SECTION: PostgreSQL-->