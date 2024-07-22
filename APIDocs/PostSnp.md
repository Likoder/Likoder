## POST /snp
### Description
Передает серию и номер паспорта пользователя
### Parameters
| Name|Type| Required fields           |Description    | 
|-----|----|---------------------------|-------------------------------------|
|sernumDoc|string| Обязательное поле         |Серия и номер документа | 

### Responses
#### Code 200

OK

Media type:_application/json_

**Example Value:**<br>
```
{
"SerNumDoc" "8000728372"
}
```
#### Code 404
Not Found
