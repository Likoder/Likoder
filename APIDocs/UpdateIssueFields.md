## POST /api/issues/{issueID}?[fields]

### Description

Обновление полей в задаче

### Params

|key|value|description|
|-|-|-|
|field|id,summary,customFields(id,name,value(avatarUrl,buildLink,color(id),fullName,id,isResolved,localizedName,login,minutes,name,presentation,text))|Поля задачи|


### Request Body
```
{
  "summary": "aleksandr vorobey",
  "customFields": [
    {
      "value": "214",
      "name": "Пароль",
      "id": "154-33",
      "$type": "SimpleIssueCustomField"
    },
    {
      "value": "781273552",
      "name": "Телефон",
      "id": "154-21",
      "$type": "SimpleIssueCustomField"
    }
  ]
}

```

### Responses
#### Code 200

OK

Media type: _application/json_

**Example Value:** <br>
```
{
"summary": "aleksandr vorobey",
    "customFields": [
        {
            "value": {
                "localizedName": null,
                "color": {
                    "id": "0",
                    "$type": "FieldStyle"
                },
                "name": "Испытательный",
                "id": "97-119",
                "$type": "EnumBundleElement"
            }
        }
    ],
    "id": "2-47043",
    "$type": "Issue"
}
```
#### Code 400

Bad Request

Media type: _application/json_

**Example Value:** <br>
```
{
    "error": "Cannot interpret value as jetbrains.charisma.persistence.customfields.IssueCustomField",
    "error_description": "Error in field unknown",
    "error_developer_message": "Error in field unknown",
    "error_field": "unknown"
}

```

#### Code 404

Not Found

Media type: _application/json_

**Example Value:** <br>
```

{
    "error": "Not Found",
    "error_description": "Entity with id Team-2324233 not found"
}
```

#### Code 500

Internal Server error

Media type: _application/json_

**Example Value:** <br>
```
{
    "error": "server_error",
    "error_description": "incompatible-issue-custom-field-id-15213-33"
}
