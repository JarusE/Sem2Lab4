Налаштування Keycloak

Запустив Keycloak через Docker ![image-6](https://github.com/user-attachments/assets/9aa603a9-ca78-4c4e-8d78-689b8a774303)


Cтворив клієнта згідно завданню:![image-8](https://github.com/user-attachments/assets/084ca8c6-7ff4-431e-8cee-c2bc308c6e73)
![image-7](https://github.com/user-attachments/assets/6c094b57-c200-4f8a-b0fd-d88cc0b9b820)


Створив ролі згідно завданню:
Ролі області: ![image-10](https://github.com/user-attachments/assets/4391fb40-1822-454e-9d22-b3c58e60300c)

Клієнтські ролі: ![image-11](https://github.com/user-attachments/assets/d375abde-32fe-4b8b-a6a2-bd5e6caabbe4)

Зробив ролі області композитними: ![image-13](https://github.com/user-attachments/assets/11dafb9a-7e67-4931-a795-06670963dea7)
![image-12](https://github.com/user-attachments/assets/29908ec2-abf0-419b-b95e-9c4719148ec7)

Створив Користуваів з паролем test123: ![image-14](https://github.com/user-attachments/assets/1a8558b8-3d26-427f-a9de-9b2d10822ac2)

Призначив ролі кожному користувачу:  ![image-17](https://github.com/user-attachments/assets/23bc0e60-3d6f-4542-8fe1-d2de53f6f08f)
![image-16](https://github.com/user-attachments/assets/a735950d-084f-4a03-a718-d8b8f30b3b29)
![image-15](https://github.com/user-attachments/assets/10af7bb3-5bc6-48dc-a01b-42e6dca22782)


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

![image](https://github.com/user-attachments/assets/232efeef-aa1b-4b7f-94ee-e9711a3c9000)

Implicit Flow

URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/auth?client_id=nest-app&response_type=token&redirect_uri=http://localhost:3000

Access Token (витягнутий з адресного рядка): eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICI5RnEwRTJQbTB4SGV6MTZSYzljTjFzaGhuV1NBLWwyZzZGREE4aE1HQlBrIn0.eyJleHAiOjE3NDY2NTk1ODMsImlhdCI6MTc0NjY1ODY4MywiYXV0aF90aW1lIjoxNzQ2NjU4NjgzLCJqdGkiOiI3YjFmMjlkNS00YmFkLTRjYWYtYjUyYy1lMThlMzVkNGFiNGQiLCJpc3MiOiJodHRwOi8vbG9jYWxob3N0OjgwODAvcmVhbG1zL1ZhZHltIiwiYXVkIjoiYWNjb3VudCIsInN1YiI6IjAzNmVkMjI4LWE2MDMtNDQ5Ni05MzNiLWMwNmRhMDI5ODIyNCIsInR5cCI6IkJlYXJlciIsImF6cCI6Im5lc3QtYXBwIiwic2Vzc2lvbl9zdGF0ZSI6ImJiMmY5MmYyLTNiZWYtNGM2Mi1hMmRhLTFlMWRkZGE5YzcyNSIsImFjciI6IjEiLCJhbGxvd2VkLW9yaWdpbnMiOlsiaHR0cDovL2xvY2FsaG9zdDozMDAwIl0sInJlYWxtX2FjY2VzcyI6eyJyb2xlcyI6WyJvZmZsaW5lX2FjY2VzcyIsImFwcC1hZG1pbiIsImRlZmF1bHQtcm9sZXMtdmFkeW0iLCJ1bWFfYXV0aG9yaXphdGlvbiJdfSwicmVzb3VyY2VfYWNjZXNzIjp7Im5lc3QtYXBwIjp7InJvbGVzIjpbImFkbWluIl19LCJhY2NvdW50Ijp7InJvbGVzIjpbIm1hbmFnZS1hY2NvdW50IiwibWFuYWdlLWFjY291bnQtbGlua3MiLCJ2aWV3LXByb2ZpbGUiXX19LCJzY29wZSI6ImVtYWlsIHByb2ZpbGUiLCJzaWQiOiJiYjJmOTJmMi0zYmVmLTRjNjItYTJkYS0xZTFkZGRhOWM3MjUiLCJlbWFpbF92ZXJpZmllZCI6ZmFsc2UsIm5hbWUiOiJUZXN0IFVzZXIyIiwicHJlZmVycmVkX3VzZXJuYW1lIjoidXNlcjIiLCJnaXZlbl9uYW1lIjoiVGVzdCIsImZhbWlseV9uYW1lIjoiVXNlcjIiLCJlbWFpbCI6InRlc3RtYWlsQG1haWwuY29tIn0.VC3qVo2IVZK1h_0TUnRUOSjJUW2jSRhctCxH1YMi7YbHNY23lyrRbRS5I872_Ix7C9k1LMtTsT0mNQFFCOuzUzVarVLEMlLvkuMEgKGsiyOiYkmPylYlaqyyCPUN_8-KLDmSybuS0KeYPhdi8xPoPI9RPysN67fwERl4a8aieaQIkjUII7ryh6-5xQReHVWDVcY6R6FIotWnDWo5P73uz3GIYJFDc5sduNOuYDcFVYYH_QkODldKz1mfx7GAkqAYtn7biGitNJCGr4O7D0JIOjD-bmpPZ4pOmegjtKjjFCxjraF2u9F9dCK19DHPu738GnJNpZCHgfWUT7975K7AbA

![image-1](https://github.com/user-attachments/assets/316eae41-919d-4448-80c3-14463d16a235)

Password Credentials Flow

Request:
- Grant Type: Password Credentials
- Access Token URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/token
- Client ID: nest-app
- Client Secret: TDwyvIbUQxY0OCs2PdVgmnhJEDyjBh9K
- Username: user1
- assword: test123

![image-3](https://github.com/user-attachments/assets/07d22563-3b73-4478-be58-1c621d5e0529)
![image-2](https://github.com/user-attachments/assets/418fd7de-0c7c-43b0-9ee5-aaf9ac981807)

Client Credentials Flow

Request:
- Grant Type: Client Credentials
- Access Token URL: http://localhost:8080/realms/Vadym/protocol/openid-connect/token
- Client ID: nest-app
- Client Secret: TDwyvIbUQxY0OCs2PdVgmnhJEDyjBh9K

![image-5](https://github.com/user-attachments/assets/7fbbf2da-3b22-4681-934d-0aad91764d81)
![image-4](https://github.com/user-attachments/assets/736e7cbf-bd95-4860-8966-059d900f98eb)


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



