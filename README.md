# PWHomeWork7

Вступна
У цьому домашньому завданні ми продовжимо працювати з домашнім завданням із попереднього модуля.

В цій домашній роботі використаємо базу даних postgres. У командному рядку запустіть Docker контейнер:

docker run --name some-postgres -p 5432:5432 -e POSTGRES_PASSWORD=mysecretpassword -d postgres


Замість some-postgres виберіть свою назву контейнера, а замість mysecretpassword придумайте свій пароль для підключення до бази даних

CAUTION
За домовленістю з ментором та технічною неможливістю використовувати postgres, можна замінити її на SQLite

Кроки виконання домашнього завдання
Перший крок
Реалізуйте свої моделі SQLAlchemy, для таблиць:

Таблиця студентів;
Таблиця груп;
Таблиця викладачів;
Таблиця предметів із вказівкою викладача, який читає предмет;
Таблиця де кожен студент має оцінки з предметів із зазначенням коли оцінку отримано;
Другий крок
Використовуйте alembic для створення міграцій у базі даних.

Третій крок
Напишіть скрипт seed.py та заповніть отриману базу даних випадковими даними (~30-50 студентів, 3 групи, 5-8 предметів, 3-5 викладачів, до 20 оцінок у кожного студента з усіх предметів). Використовуйте пакет Faker для наповнення. При заповненні використовуємо механізм сесій SQLAlchemy.

Четвертий крок
Зробити такі вибірки з отриманої бази даних:

Знайти 5 студентів із найбільшим середнім балом з усіх предметів.
Знайти студента із найвищим середнім балом з певного предмета.
Знайти середній бал у групах з певного предмета.
Знайти середній бал на потоці (по всій таблиці оцінок).
Знайти які курси читає певний викладач.
Знайти список студентів у певній групі.
Знайти оцінки студентів у окремій групі з певного предмета.
Знайти середній бал, який ставить певний викладач зі своїх предметів.
Знайти список курсів, які відвідує певний студент.
Список курсів, які певному студенту читає певний викладач.
Для запитів оформити окремий файл my_select.py, де будуть 10 функцій від select_1 до select_10. Виконання функцій повинно повертати результат аналогічний попередньої домашньої роботи. При запитах використовуємо механізм сесій SQLAlchemy.

Додаткове завдання
Перша частина
Для додаткового завдання зробіть такі запити підвищеної складності:

Середній бал, який певний викладач ставить певному студентові.
Оцінки студентів у певній групі з певного предмета на останньому занятті.
Друга частина
Замість скрипту seed.py подумайте та реалізуйте повноцінну CLI програму для CRUD операцій із базою даних. Використовуйте для цього модуль argparse .

Використовуйте команду --action або скорочений варіант -a для CRUD операцій. Та команду --model (-m) для вказівки над якою моделлю проводитися операція.
Реалізуйте ці операції для кожної моделі.
