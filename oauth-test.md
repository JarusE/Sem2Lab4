Налаштування Keycloak

Запустив Keycloak через Docker![alt text](image-6.png)

Cтворив клієнта згідно завданню:![alt text](image-7.png) ![alt text](image-8.png)

Створив ролі згідно завданню:
Ролі області: ![alt text](image-10.png)

Клієнтські ролі: ![alt text](image-11.png)

Зробив ролі області композитними: ![alt text](image-12.png) ![alt text](image-13.png)

Створив Користуваів з паролем test123: ![alt text](image-14.png)

Призначив ролі кожному користувачу: ![alt text](image-15.png) ![alt text](image-16.png) ![alt text](image-17.png)

Отримання токенів через Postman
Authorization Code Flow

Request:
- Grant Type: Authorization Code
- Callback URL: http://localhost:8080/callback
- Auth URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/auth
- Access Token URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/token
- Client ID: nest-app
- Client Secret: TDwyvIbUQxY0OCs2PdVgmnhJEDyjBh9K
- Scope: openid

![alt text](image.png)

Implicit Flow

URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/auth?client_id=nest-app&response_type=token&redirect_uri=http://localhost:3000

Access Token (витягнутий з адресного рядка): eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICI5RnEwRTJQbTB4SGV6MTZSYzljTjFzaGhuV1NBLWwyZzZGREE4aE1HQlBrIn0.eyJleHAiOjE3NDY2NTk1ODMsImlhdCI6MTc0NjY1ODY4MywiYXV0aF90aW1lIjoxNzQ2NjU4NjgzLCJqdGkiOiI3YjFmMjlkNS00YmFkLTRjYWYtYjUyYy1lMThlMzVkNGFiNGQiLCJpc3MiOiJodHRwOi8vbG9jYWxob3N0OjgwODAvcmVhbG1zL1ZhZHltIiwiYXVkIjoiYWNjb3VudCIsInN1YiI6IjAzNmVkMjI4LWE2MDMtNDQ5Ni05MzNiLWMwNmRhMDI5ODIyNCIsInR5cCI6IkJlYXJlciIsImF6cCI6Im5lc3QtYXBwIiwic2Vzc2lvbl9zdGF0ZSI6ImJiMmY5MmYyLTNiZWYtNGM2Mi1hMmRhLTFlMWRkZGE5YzcyNSIsImFjciI6IjEiLCJhbGxvd2VkLW9yaWdpbnMiOlsiaHR0cDovL2xvY2FsaG9zdDozMDAwIl0sInJlYWxtX2FjY2VzcyI6eyJyb2xlcyI6WyJvZmZsaW5lX2FjY2VzcyIsImFwcC1hZG1pbiIsImRlZmF1bHQtcm9sZXMtdmFkeW0iLCJ1bWFfYXV0aG9yaXphdGlvbiJdfSwicmVzb3VyY2VfYWNjZXNzIjp7Im5lc3QtYXBwIjp7InJvbGVzIjpbImFkbWluIl19LCJhY2NvdW50Ijp7InJvbGVzIjpbIm1hbmFnZS1hY2NvdW50IiwibWFuYWdlLWFjY291bnQtbGlua3MiLCJ2aWV3LXByb2ZpbGUiXX19LCJzY29wZSI6ImVtYWlsIHByb2ZpbGUiLCJzaWQiOiJiYjJmOTJmMi0zYmVmLTRjNjItYTJkYS0xZTFkZGRhOWM3MjUiLCJlbWFpbF92ZXJpZmllZCI6ZmFsc2UsIm5hbWUiOiJUZXN0IFVzZXIyIiwicHJlZmVycmVkX3VzZXJuYW1lIjoidXNlcjIiLCJnaXZlbl9uYW1lIjoiVGVzdCIsImZhbWlseV9uYW1lIjoiVXNlcjIiLCJlbWFpbCI6InRlc3RtYWlsQG1haWwuY29tIn0.VC3qVo2IVZK1h_0TUnRUOSjJUW2jSRhctCxH1YMi7YbHNY23lyrRbRS5I872_Ix7C9k1LMtTsT0mNQFFCOuzUzVarVLEMlLvkuMEgKGsiyOiYkmPylYlaqyyCPUN_8-KLDmSybuS0KeYPhdi8xPoPI9RPysN67fwERl4a8aieaQIkjUII7ryh6-5xQReHVWDVcY6R6FIotWnDWo5P73uz3GIYJFDc5sduNOuYDcFVYYH_QkODldKz1mfx7GAkqAYtn7biGitNJCGr4O7D0JIOjD-bmpPZ4pOmegjtKjjFCxjraF2u9F9dCK19DHPu738GnJNpZCHgfWUT7975K7AbA

![alt text](image-1.png)

Password Credentials Flow

Request:
- Grant Type: Password Credentials
- Access Token URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/token
- Client ID: nest-app
- Client Secret: TDwyvIbUQxY0OCs2PdVgmnhJEDyjBh9K
- Username: user1
- assword: test123

![alt text](image-2.png)![alt text](image-3.png)

Client Credentials Flow

Request:
- Grant Type: Client Credentials
- Access Token URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/token
- Client ID: nest-app
- Client Secret: TDwyvIbUQxY0OCs2PdVgmnhJEDyjBh9K

![alt text](image-4.png) ![alt text](image-5.png)

Контрольні питання:
- Що таке Keycloak і які основні функції він надає?

    Keycloak — це open-source система управління автентифікацією та авторизацією. Вона дозволяє централізовано керувати обліковими записами, автентифікацією та доступом користувачів до додатків і сервісів.
    Основні функції:
    - Єдиний вхід (SSO)
    - Підтримка OpenID Connect, OAuth 2.0, SAML 2.0
    - Автентифікація через соціальні мережі
    - Управління ролями та користувачами через веб-інтерфейс або REST API
    - Авторизація на основі ролей
    - Можливість розширення через власні провайдери

- Які стандарти відкритого протоколу використовуються Keycloak для забезпечення автентифікації та авторизації?

    Keycloak підтримує такі стандарти:
    - OpenID Connect (OIDC) — розширення OAuth 2.0, що надає ідентифікаційну інформацію
    - OAuth 2.0 — протокол авторизації доступу до ресурсів через токени
    - SAML 2.0 — XML-базований стандарт для єдиного входу (SSO) у корпоративних системах

- Як працює автентифікація з використанням Keycloak? Опишіть процес.

    - Користувач намагається отримати доступ до захищеного ресурсу.
    - Додаток перенаправляє користувача на сторінку входу Keycloak.
    - Користувач вводить логін і пароль.
    - Keycloak перевіряє облікові дані.
    - Успішна автентифікація → Keycloak повертає токен (ID, Access, Refresh).
    - Додаток використовує цей токен для перевірки прав доступу при кожному запиті.

- Які основні кроки потрібно виконати для налаштування сервера Keycloak?

    - Запустити сервер Keycloak (наприклад, через Docker).
    - Увійти в Admin Console як адміністратор.
    - Створити realm - ізольоване середовище для додатків.
    - Додати клієнтів - додатки, які будуть використовувати авторизацію.
    - Створити ролі для контролю доступу.
    - Створити користувачів і призначити їм відповідні ролі.

- Що таке Realm в Keycloak і яка його роль?

    Realm — це ізольоване середовище автентифікації, яке містить користувачів, клієнтів, ролі, політики доступу тощо.
    Кожна Realm незалежна й не ділиться даними з іншими. Це дозволяє створювати кілька середовищ (наприклад, тестове і продакшн).

- Як створити клієнта в Keycloak і яку роль він відіграє у системі?

    - Admin Console - Clients - Create client
    - Вказати Client ID, тип доступу (confidential, public, bearer-only)
    - Вказати допустимі redirect URL
    - Налаштувати потоки (Authorization code, Implicit тощо)

    Клієнт ініціює автентифікацію та отримує токени.

- Що таке Composite Roles в Keycloak і як вони працюють?

    Composite Role — це складена роль, яка об'єднує кілька інших ролей (області або клієнта).
    Коли користувачу призначається composite role, він автоматично отримує всі ролі, які до неї входять. Це зручно для групування дозволів.

- Як створити користувача в Keycloak і як призначити йому ролі?

    - Admin Console - Users - Add User
    - Вказати ім'я користувача, email, username
    - У вкладці Credentials задати пароль
    - У вкладці Role Mapping Вибрати Realm Roles або Client Roles



