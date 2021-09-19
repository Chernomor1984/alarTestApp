# alarTestApp

Сделать простое приложение клиент для просмотра онлайн базы данных.

Общие требования:
Swift или Objective-C (да, и вы и мы пишем на Swift в бою, но Objective-C покажет нам, что вы - труразработчик!).

Использовать стандартные средства iOS/Cocoa Touch.
Можно использовать ReactiveCocoa.
Все должно быть кратко и понятно.

Цель теста: увидеть, как претендент пишет код и придумывает архитектуру - никаких копи-пейст "стандартных решений"/

Три экрана:
При запуске.
Показывает текстовые поля логин/пароль и кнопку "Войти".
При нажатии идет к серверу GET http://www.alarstudios.com/test/auth.cgi 
(параметры запроса: username=XXX, password=XXX), он возвращает JSON.
Если "status" == "ok", то пропускаем, нет - показываем красиво, что логин/пароль неправильные.
Сервер выдаст "ok" на "test"/"123" и тогда идем на следующий экран, запоминая "code".

Таблица с данными.
Данные получаем по GET http://www.alarstudios.com/test/data.cgi (параметры запроса: code=XXX из предыдущего шага, p=N - страница с 1), выдает по 10 элементов.
В приложении - отображается как бесконечная пагинация. Доходим до "низа" списка - подгружаем данные.
Каждый элемент таблицы должен содержать картинку (выберите любой внешний URL), подгружаемую асинхронно и имя (name из полученных данных).

При нажатии на элемент, переходим на третий экран.
По нажатию на элемент на втором экране переходим сюда.
Показываем все поля и карту с точкой по координатам в полях "lat"/"lon" из JSON.
Даем возможность вернуться к списку.
Все. Очень просто. На выполнение дается 72 часа. Оцениваем не только сам факт и скорость выполнения, но в гораздо большей степени качество, аккуратность и выбранные решения. Если есть вопросы - пишите!
Перед отправкой, УБЕДИТЕСЬ, что все работает, как нужно, что учитывает "эффект пользователя". Например, быстрая прокрутка.