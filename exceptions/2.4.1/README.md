## Задача 1. Проверка доступа к ресурсу

### Описание
Напишем программу для проверки доступа к ресурсу, во время запуска программы нужно запросить логин или пароль пользователя, если один из введеных
параметров не совпадает, то нужно выбросить checked исключение UserNotFoundException, а если возраст пользователя менее 18 лет, то нужно выбросить исключение AccessDeniedException,
иначе вывести сообщение "Доступ представлен". Массив пользователей для авторизации нужно описать до запуска программы, каждая запись пользователя содержит поля login, password, age (возраст) и email.
 
### Функционал программы
1. Создание Scanner для чтения логина и пароля пользователя из консоли;
2. Создание checked исключения UserNotFoundException;
3. Создание checked исключения AccessDeniedException;
4. Выбрасывать ошибку UserNotFoundException если логин или пароль введены не верно;
5. Выбрасывать ошибку AccessDeniedException если возраст пользователя меньше 18 лет;
5. Если ошибок не возникло вывести сообщение "Доступ представлен".

### Процесс реализации
1. Создадим класс User в котором будем хранить инфомрацию о логине, пароле и возрасте пользователя: 
class User, login, password, email, age;
2. Создадим класс исключение UserNotFoundException на основе базового класса Exception, это исключение будем использовать, если
пользователь ввел не верный логин или пароль:
```java
public class UserNotFoundException extends Exception {
    public UserNotFoundException(String message) {
        super(message);
    }
}
```
3. Аналогичным образом создадим класс исключения AccessDeniedException
4. Создадим класс Main в котором создадим метод getUsers, этот метод должен возвращать список заранее созданных пользователей:
```java
public static User[] getUsers() {
    User user1 = new User("jhon", "jhon@gmail.com", "pass", 24);
    ...
    return new User[]{user1, ...};
}
```
5. Создадим в классе Main метод getUserByLoginAndPassword(String login, String password), в этом методе нужно найти соответствие пары логина и пароля пользователя из массива
возвращаемого методом getUsers, если пользователь не найден выбрасываем исключение UserNotFoundException, иначе возвращаем найденного пользователя:
```java
public static User getUserByLoginAndPassword(String login, String password) throws UserNotFoundException {
    User[] users = getUsersList();
    for (User user : users) {
        ...
    }
    throw new UserNotFoundException("User not found");    
}   
```
6. Создадим к классе Main еще один метод validateUser для проверки возрастра пользователя, если возраст менее 18 лет метод должен выбросить исключение AccessDeniedException:
```java
public static void validateUser(User user) throws AccessDeniedException
``` 
7. Добавим последний метод в классе Main для запуска программы public static void main(String[] args) throws UserNotFoundException, AccessDeniedException
В нем нужно запросить логин и пароль пользователя, проверить есть ли данная пара логин и пароль в массиве пользователей и последним шагом провадировать возраст.
```java
    public static void main(String[] args) throws UserNotFoundException, AccessDeniedException {

        Scanner scanner = new Scanner(System.in);

        System.out.println("Введите логин");
        String login = scanner.nextLine();
        System.out.println("Введите пароль");
        String password = scanner.nextLine();

        //Проверить логин и пароль
        
        //Вызвать методы валидации пользователя
        
        System.out.println("Доступ представлен");
    }

```
8. Программа завершена.