## UserList

### Description:
Выводит список ролей пользователей  


### Message:
``` {} ```


### Response:

Code 0

OK

Example Value:

   ```
   "list": [
            {
                "roles": [
                    {
                        "key": "staff",
                        "name": "Сотрудник"
                    }
                ],
                "id": "71307ad2-a410-4434-b379-c78752731ba9",
                "youtrack_id": "07777a71-7cde-49e1-83c1-1fee9dad6063",
                "name": "Джеймс Админов Кирк",
                "avatar": "https://youtrack-dev.tages.dev/hub/api/rest/avatar/07777a71-7cde-49e1-83c1-1fee9dad6063?etag=MjgtNzU%3D"
            },
```

### ??

|Name | Type | Required fields | Description |
|---|-----|---------------|-----------|
|key|string|Обязательное поле|Ключ роли|
|name|string|Обязательное поле|Наименование роли|
|id|string|Обязательное поле|ID пользователя|
|youtrack_id|string|Обязательное поле|ID Youtrack аккаунта пользователя|
|name|string|Обязательное поле|Имя и фамилия пользователя|
|avatar|string|Обязательное поле|Аватар пользователя|

### Response:

CODE 7 PERMISSION DENIED

Access denide

Error: set role to yourself
