## Задача 1. Список студентов
### Описание
Вы разрабатываете систему учета студентов. Для каждого студента нужно хранить следующие данные – ФИО, номер группы, номер студенческого билета. Уникальным идентификатором является номер студенческого билета.
Пользователь вводит данные студентов в бесконечном цикле до ввода команды “end”. По окончанию ввода программа должна вывести список студентов.
Пользователь вводит студентов, аналогично заданию “Список сотрудников”.
Структура данных, куда сохраняются студенты, должна отбрасывать ввод одного и того же студента более одного раза.
Учитывайте, что имена у людей могут быть одинаковыми, а номера документов – нет.
### Реализация
1. Создайте класс `Student` с полями `name`, `group`, `studentID`. Тип каждого поля – `String`.
2. Переопределите методы hashcode и equals для класса `Student` так, чтобы нельзя было сохранить двух студентов с одинаковым номером студенческого билета.
3. Продемонстрируйте добавление объектов класса в HashSet, ошибку при добавлении студентов с одинаковым номером, возможность существования студентов с одинаковыми именами.