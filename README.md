# SDL_Prac_2
## CWE-598 - Использование GET-метода в запросе, содержащем конфиденциальные параметры
```
$user = $_GET['username'];
$pass = $_GET['password'];
```
>__Исправления:__ Необходимо использовать POST-метод.
```
$user = $_POST['username'];
$pass = $_POST['password'];
```
---
## CWE-307 - Неправильное ограничение чрезмерных попыток аутентификации

>__Варианты исправления__:
>* Отключение пользователя после определённого количества неудачных попыток;
>* Блокировка учетной записи;
>* Реализация тайм-аута;
>* Предоставление пользователю вычислительной задачи.
---
## CWE-327 - Использование нерабочего или неэффективного криптографического алгоритма
```
$pass = md5($pass);
```
>__Исправления__: Использовать современный, проверенный, криптостойкий алгоритм. Например, SHA256.
---
## CWE-759: Использование одностороннего хеширования без соли
>__Исправления__: Использовать соль, которая будет храниться в базе данных.
```
get_salt($username)
```
## CWE-89 - Неправильная нейтрализация специальных символов, используемых в SQL команде
```
$query  = "SELECT * FROM `users` WHERE user = '$user' AND password = '$pass';";
```
>__Исправление:__ добавить использование PDO или его аналогов, чтобы избежать SQL инъекции.
