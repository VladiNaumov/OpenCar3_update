# Папка system
 
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