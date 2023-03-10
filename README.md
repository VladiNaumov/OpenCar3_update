# OpenCar3_update

пример регистрации шаблона OpenCar3 (antropy):

- ... admin/controller/extension/theme/antropy.php - регистрация нашего шаблона в контроллере
- ... admin/language/en-db/extension/theme/antropy.php - регистрация нашего языка шаблона
- ... admin/view/template/extension/theme/antropy.twig - регистрация нашего шаблона в представление (view)

P.S. выше указанные операции обязательны для регистрации нашего шаблона в OpenCar3

- ... catalog/view/thema/...  местонахождение наших сайтов 
- ... catalog/view/thema/antropy- это наш только что зарегистрированный шаблон "antropy"
- ... catalog/view/thema/default/ .... это шаблон по умолчанию поставляемый вместе c OpenCart3

  ### ! внимание папку system/ копировать не нужно !

- запуск сайта начинается с файла home.twig - Этот как точка входа в программу.
- он находится catalog/view/thema/-имя вашей темы-/template/common/home.twig

запуск темы в OpenCar3:
- Расширения->темы->включить тему 
- система->настройки->выбрать тему 

дистрибутив OpenCart. Он состоит из двух частей: фронтэнд для пользователей и бэкэнд для администратора. 

В состав дистрибутива (каталога upload) входят 4 папки:
- Admin. Это административная часть магазина или его backend. По сути это сайт для администратора.
- Catalog. Это витрина магазина доступная для посетителей. По сути это сайт для пользователей или frontend магазина.
- Images. В этой папке все картинки магазина, включая каталог, картинки системы, а также картинки шаблонов. 
- System. Здесь системные файлы OpenCar3. 
- папка кеш: syste/storage/cache.


Любой, кто начинает работать с OpenCart задается вопросом: "Что где лежит? Или какая папка и какие файлы за что отвечают в OpenCart, в какую папку нужно копировать файлы нового OpenCart модуля?

## Корневая папка
 
Корневая папка OpenCart, которая находится в папке сайта, содержит 4 папки и 5 файлов:
папки:
- admin - содержит файлы панели администрирования магазинов, то, что видит администратор сайта
- catalog - содержит файлы каталога магазина, то, что видит пользователь, когда заходит на сайта
- image - cодержит изображения для товаров, каталогов, флаги, изображения для товара без изображения, кешированые копии изображений.
- system - содержит системные файлы
 
файлы:
- .htaccess.txt - содержит настройки для ЧПУ (чтобы ссылки на сайте были не yoursite.com/index.php?route=product/product&product_id=40, a yoursite.com/iphone), а также некоторые настройки для сервера, например время выполнения скриптов, максимальный размер для загружаемых файлов итд.
- config.php - конфигурационный файл, содержит определение глобальных переменных для папок сайта, например DIR_APPLICATION для папки каталога, DIR_SYSTEM для папки системных фалов итд., а также настройки базы данных: драйвер БД, хост, пользователь, пароль, БД, префикс таблиц
- crossdomain.xml - файл междоменной политики, нужен например для Adobe флэш плеера.
- index.php - главный файл, который запускается первым 
- php.ini - файл php настроек, здесь можно задать настройки например для стандартной кодировки, лимита оперативной памяти для сайта итд.
 
## Папка admin
 
Содержит 4 папки и 3 файла, папки:
- controller - папка для OpenCart контроллеров, содержит контроллеры для работы с каталогом (товар, категория, атрибуты, опции, фильтры итд.), основные (common)  контроллеры (шапка сайта, футер, меню, страница авторизации, левая колонка итд.), контроллеры расширений (модули, модификации, оплата, доставка..), локализация, установленный модули, настройки, работа с пользователями итд.
- language - папка языковых файлов, содержит папки для каждого языка с языковыми файлами для этого языка
- model - папка для моделей
- view - папка для представлений, шаблонов, содержит как сами шаблоны так и картинки для них, яваскрипт библиотеки и файлы, css файлы
 
файлы: 
- config.php 
- index.php
- php.ini
- практически не отличаются от файлов каталога, описанных выше. 
 
## Папка catalog:
 
Содержит 4 папки, которые по структуре не отличаются от папок папки admin, за исключения разве что папки представалений, которая в каталоге может содержать несколько тем, а в admin только 1:
- controller
- language
- model
- view
 
## Папка system
 
Содержит системные файлы:

- config - папка для конфигурационных файлов
- engine - файлы для основных классов движка: действие action, контроллер controller, события event, фронт контроллер front, загрузчик loader, модель model, реестр registry
- helper - файлы функций помощников: json - для преобразования массивов в json объекты, utf8 - для работы с текстом в кодировке utf8, vat - для vat кодов
- library - классы-библиотеки: драйвера баз данных db, системы кеширования cache, работа с корзиной cart, конфигурационными файлами config, пользователями user,валютой currency, изображениями image, почтой mail, пользователями user, кодировка encryption итд. 


папка storage особо важные системные файлы (находятся совершенно  в отдельном каталоге):
- cache - папка для кешированых данных 
- download - папка для загруженных файлов
- logs - логи ошибок 
- modification - файлы модификаций
- upload - файлы для выгрузки
- modification.xml - файл модификаций OpenCart
- startup.php - файл для проверки установок системы и загрузки основных классов и помощников, необходимых для OpenCart. Этот файл грузится одним из первых при загрузке системы. 