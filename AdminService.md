## Set/Revoke User Role
### Description 

Добавление и удаление роли администратора.

### Message:
```
{
    "id": "90165e5b-d7a1-4dc6-b710-9484c80ab3d8",
    "role_key": "su"
}
```

### Parameters

|Name | Type | Required fields | Description |
|---|-----|---------------|-----------|
|id|string|Обязательное поле|ID пользователя|
|role_key|string|Обязательное поле|Ключ роли|



### Response:

Code 0

OK

Example Value:

```
 {
    "user": {
        "roles": [
            {
                "key": "staff",
                "name": "Сотрудник"
            }
        ],
        "id": "a46b4bd7-7f1d-4467-8a90-7e39faa70dde",
        "youtrack_id": "9d1d0b95-9916-4ec7-b5ec-8cb83f7dbe26",
        "name": "Питер Квилл",
        "avatar": "https://youtrack-dev.tages.dev/hub/api/rest/avatar/9d1d0b95-9916-4ec7-b5ec-8cb83f7dbe26?etag=MjgtNjA%3D"
    }
}
```

|Name | Type | Required fields | Description |
|---|-----|---------------|-----------|
|key|string|Обязательное поле|Ключ роли|
|name|string|Обязательное поле|Наименование роли|
|id|string|Обязательное поле|ID пользователя|
|youtrack_id|string|Обязательное поле|ID Youtrack аккаунта пользователя|
|name|string|Обязательное поле|Имя и фамилия пользователя|
|avatar|string|Обязательное поле|Аватар пользователя|



## UserList

### Description
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
