## LibraryService/ReserveBook
### Description
Метод `ReserveBook` используется для бронирования книги в библиотеке.<br> При выполнении метода, `staff_id`, присваивается книге во время заимствования,  указывая на то, что книга больше находится у конкретного сотрудника и недоступна для других пользователей.

### Message:
```
{
    "book_id": "2-48366"
}
```
Name | Type  | Required fields| Description |
|---|-----|-------|-----------|
|book_id |string| Обязательное поле |Идентификатор книги|

### Response:

Status Code 0

OK

Example Value:

```
{
    "book": {
        "id": "2-48366",
        "name": "Поток: Психология оптимального переживания",
        "author": "Чиксентмихайи Михай",
        "staff_id": "1-16",
        "cover_url": "",
        "e_url": "",
        "audio_url": "",
        "has_paper_copy": true,
        "tages_office": "OFFICE_UFA",
        "book_status": "LIBRARY_ITEM_STATUS_TAKEN"
    }
}
```
### Response:

CODE 13 INTERNAL

Operation couldn’t be completed because of an internal error at the server.    

Error: internal error
