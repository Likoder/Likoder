## AdminService/Set&RevokeUserRole
### Description:

Добавление и удаление роли администратора.

### Message:
```
{
    "id": "90165e5b-d7a1-4dc6-b710-9484c80ab3d8",
    "role_key": "su"
}
```

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
### Response:

CODE 7 PERMISSION DENIED

Access denied

Error: set role to yourself


