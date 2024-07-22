## Delete /PassP
### Description
Удаляет паспортные данные пользователя из БД

### Parameters
| Name|Type| Required fields           |Description    | 
|-----|----|---------------------------|-------------------------------------|
|fname|string| Обязательное поле         |Имя                                 | 
|lname|string| Обязательное поле         |Фамилия                             | 
|mname|string| Обязательное поле         |Отчество                            | 
|typeDoc|integer| Условно-обязательное поле |Вид документа, удостоверяющего личность:<br>  01 - Паспорт гражданина СССР<br>03 - Свидетельство о рождении<br>10 - Паспорт иностранного гражданина<br>12 - Вид на жительство в Российской Федерации<br>15 - Разрешение на временное проживание в Российской Федерации<br>19 - Свидетельство о предоставлении временного убежища на территории Российской Федерации<br>21 - Паспорт гражданина Российской Федерации<br>23 - Свидетельство о рождении, выданное уполномоченным органом иностранного государства
|dateOfBirth|date| Обязательное поле         |Дата рождения
|sernumDoc|string| Обязательное поле         |Серия и номер документа | 
|dateOfIssue|date| Необязательое поле        |Дата выдачи документа 
### Responses
#### Code 200

successful operation

Media type:_application/json_

**Example Value:**<br>
````
'the user's with nickname {nickname} passport data has been successfully deleted'
````
#### Code 404
Not Found

**Example Value:**<br>
````
'Passport data not found for user with nickname {nickname}'
````
Or

**Example Value:**<br>
````
'User with nickname {nickname} not found'
