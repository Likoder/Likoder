## LibraryService/SuggestBook
### Description
Метод `SuggestBook` позволяет сотруднику предложить свою книгу в корпоративную библиотеку.
### Message:
```
{
    "author": "Чарльс Покровский",
    "book_type": 1,
    "comment": "",
    "custom_office": "",
    "link": "",
    "name": "Записки на пятках",
    "tages_office": 2
}
```
Name | Type  | Required fields| Description |
|---|-----|-------|-----------|
|author |string| Необязательное поле |Автор книги|
|book_type |enum| Обязательное поле |Тип носителя книги|
|comment |string| Необязательное поле |Комментарий для книги|
|link |string| Условно-обязательное поле |Ссылка на книгу|
|name |string| Обязательное поле |Название книги|
|tages_office |enum| Условно-обязательное поле |Офис, в котором находится книга|


### Response:

Status Code 0

OK

Example Value:

```
{}
```
