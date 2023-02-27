# OpenCar3_update

пример регистрации шаблона OpenCar3 (antropy):

- ... admin/controller/extension/theme/antropy.php - регистрация нашего шаблона в контроллере
- ... admin/language/en-db/extension/theme/antropy.php - регистрация нашего языка шаблона
- ... admin/view/template/extension/theme/antropy.twig - регистрация нашего шаблона в представление (view)

P.S. выше указанные операции обязательны для регистрации нашего шаблона в OpenCar3

- ... catalog/view/thema/...  местонахождение наших сайтов 
- ... catalog/view/thema/antropy- это наш только что зарегистрированный шаблон "antropy"


... catalog/view/thema/default/ .... это шаблон по умолчанию поставляемый вместе c OpenCart3


- запуск сайта начинается с файла home.twig - Этот как точка входа в программу.
- он находится catalog/view/thema/-имя вашей темы-/template/common/home.twig

запуск темы в OpenCar3:
- Расширения->темы->включить тему 
- система->настройки->выбрать тему 

дистрибутив OpenCart. Он состоит из двух частей: фронтэнд для пользователей и бэкэнд для администратора. 
- Вся административная часть лежит в каталоге admin. (По сути это сайт для администратора)
- Часть для пользователя лежит в каталоге catalog. (По сути это сайт для пользователей или frontend магазина.)
- Обе части движка имеют одинаковую структуру и используют одну базу данных.
- В папке images собираются все картинки сайта магазина.
- В папке system лежат все системные файлы OpenCar3.


В состав дистрибутива (каталога upload) входят 4 папки:
- Admin. Это административная часть магазина или его backend. По сути это сайт для администратора.
- Catalog. Это витрина магазина доступная для посетителей. По сути это сайт для пользователей или frontend магазина.
- Images. В этой папке все картинки магазина, включая каталог, картинки системы, а также картинки шаблонов. 
  Кроме этого здесь есть папка cache для кеша сайта магазина.
- System. Здесь системные файлы OpenCar3. 
- папка кеш: syste/storage/cache.