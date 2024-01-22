- [Плагины для Visual Studio Code](#плагины-для-visual-studio-code)
- [javascript заметки](#javascript-заметки)
- [ESLint](#eslint)
	- [Проверка кода и его Форматирование](#проверка-кода-и-его-форматирование)
	- [Файл настроек ".eslintrc.js"](#файл-настроек-eslintrcjs)
- [Настройки форматирования](#настройки-форматирования)

<!-- Begin -->
## Плагины для Visual Studio Code
* All Autocomplete
* Auto Complete Tag
* Code Runner
* Import Cost
* JavaScript (ES6) code snippets
* jshint
* Live Server
* Multiple clipboards for VSCode
* Reactjs code snippets
* Sass
* Theme - Oceanic Next
* vscode-icons
<!-- End -->   

<!-- Begin -->
## javascript заметки
1) Атрибуты script
```javascript
/*
1) type="text/javascript" - устаревший, не используется
2) src="js/script.js" - если есть ссылка на файл, то код внутри script выполняться не будет
*/
   <script src="js/script.js" type="text/javascript">alert("User message 01")</script>
   ```
<!-- End -->

<!-- Begin -->
## ESLint
ESLint - это инструмент статического анализа кода для идентификации проблемных шаблонов, найденных в коде JavaScript.

При создании проекта:
1) npm init
2) npm init @eslint/config
<!-- End -->   

<!-- Begin -->
### Проверка кода и его Форматирование

### Файл настроек ".eslintrc.js"
Уроверь обработки ошибок:
* error
* warn
```javascript
module.exports = {	
	'env': {
		'browser': true, //Где будет выполятнся код
		'es2021': true //Стандарт JavaScript
	},
	//'extends': 'eslint:recommended',
	'overrides': [
		{
			'env': {
				'node': true
			},
			'files': [
				'.eslintrc.{js,cjs}'
			],
			'parserOptions': {
				'sourceType': 'script'
			}
		}
	],
	'parserOptions': {
		'ecmaVersion': 'latest'
	},
	'rules': {
		//Отсутпы
		'indent': [
			'error',
			'tab'
		],
		//Операционная система
		'linebreak-style': [
			'error',
			'windows'
		],
		//Кавычки
		'quotes': [
			'error',
			'single'
		],
		//Точка с запятой в конце строки
		'semi': [
			'error',
			'always'
		],
		//Не используемые переменные - предупреждение
		'no-unused-vars': ['warn']
	}
};

```
<!-- End -->   

<!-- Begin -->
## Настройки форматирования
*File -> Preferences -> Settings*

Опция: *Editor: Format On Save* - On/Off
Опция: *Editor: Default formatter* - выбираем ESLint в качестве форматтера по умолчанию

```javascript
//Добавляем сами, если не нет
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "eslint.validate": [
    "javascript"
  ]
  ```
  <!-- End -->