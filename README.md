# 🔐 HTTP Server with Basic Auth (Go)

Цей проєкт — простий HTTP-сервер на Go з базовою аутентифікацією. Реалізовано middleware через `negroni`, що перевіряє ім'я користувача та пароль з параметрів URL. Для маршрутизації використовується `gorilla/mux`.

## 🧠 Опис

Сервер надає доступ до єдиного маршруту `/hello`, який доступний лише після успішної аутентифікації. Дані користувача передаються через query-параметри `username` та `password`.

## 🚀 Запуск

1. Переконайтесь, що встановлено залежності:

```bash
go get github.com/gorilla/mux
go get github.com/urfave/negroni
```
   
3. Запустіть сервер:

```bash
go run main.go
```

3. Зробіть запит:

```bash
curl "http://localhost:8000/hello?username=admin&password=password"
# Output: Hi admin

curl "http://localhost:8000/hello?username=admin&password=wrong"
# Output: Unauthorized
```

### ⚠️ Попередження

Цей приклад небезпечний для реального використання:

- Аутентифікація через query-параметри — уразлива.
- Паролі не хешуються.
- Відсутній TLS.

 > Використовуйте лише для навчання!

