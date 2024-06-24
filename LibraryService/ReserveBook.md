## LibraryService/ReserveBook
### Description
Присваивает книге сотрудника, который пользуется ей в данный момент
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
