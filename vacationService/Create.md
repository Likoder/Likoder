## VacationService/Create
### Description 

Метод `VacationService/Create` позволяет добавить отсутствие сотрудникам.

### Message:
```
{
  "type": "VACATION_TYPE_BUSINESS_TRIP",
  "staff_id": "1-16",
  "start_at": {
                "seconds": "1693656000",
                "nanos": 0
            },
    "end_at": {
                "seconds": "1696248000",
                "nanos": 0
            },
    "office": "OFFICE_MSK",
    "office_from": "OFFICE_UFA"
}
```
Name | Type  | Required fields| Description |
|---|-----|-------|-----------|
|type |enum| Обязательное поле |Тип отсутствия|
|staff_id|string| Обязательное поле |Идентификатор сотрудника|
|start_at|TimeStamp{seconds,nanos}| Обязательное поле |Время начала отсутствия|
|end_at|TimeStamp{seconds,nanos}| Обязательное поле |Время конца отсутствия|
|office|string| Условно-обязательное поле |Офис, куда направляется сотрудник|
|office_from|string| Условно-обязательное поле |Офис, откуда направляется сотрудник|

### Response:

Status Code 0

OK

Example Value:

```
{
  "id": "2-47235",
  "type": "VACATION_TYPE_BUSINESS_TRIP",
  "status": "VACATION_STATUS_END",
  "staff_id": "1-16",
  "start_at": {
                "seconds": "1693656000",
                "nanos": 0
            },
  "end_at": {
                "seconds": "1696248000",
                "nanos": 0
            },
  "creator_id": "1-1",
  "office": "OFFICE_MSK",
  "office_from": "OFFICE_UFA"
}
```
### Response:

CODE 13 INTERNAL

Operation couldn’t be completed because of an internal error at the server.    

Error: internal error
