# Задача:
**В мобильное приложение требуется добавить 
возможность, чтобы каждый пользователь мог указать 
свои паспортные данные, которые должны проверяться по ИНН, корректные данные должны отправляться в базу данных о пользователе. Также у пользователя должна быть возмоижность удалять паспортные данные через службу поддержки.**
##
1. (UI) Создание кнопки "Добавления паспортных данных" для пользователя.
##
2. (UI) Создание страницы с использованием `API ФНС(innfl)`  для ввода паспортных данных:
- Фамилия;
- Имя;
- Отчество(при наличии);
- Дата рождения;
- Тип документа; 
- Серия и номер документа.<br>
И получения ИНН `(массив items[])`.
![](![image](https://github.com/Likoder/Likoder/assets/90778057/556d48d3-75b7-4088-b15c-89470070a712)


##



3. (Backend) Используя хендлер [GET /user](https://github.com/Likoder/Likoder/blob/main/GETuser.md) проверять
наличия значения в массиве, в случае
наличия - изменить статус пользователя 
на подтвержденный
##
4. (Backend) Cохранить его данные в БД используя
хендлер [POST /user](https://github.com/Likoder/Likoder/blob/main/PostUser.md), при отстуствии -
произвести переадресацию в личный кабинет.
##
5. (UI) Добавить параметр пользователя "подтверждённый" и "не подтверждённый", изначальный статус пользователя является "не подтверждённый".
##
6. (UI) При статусе пользователя "подтверждённый" кнопка добавления документа исчезает из ЛК.
##
7. (Backend) Создать раздел в службе поддержке 
"Удаление паспортных данных", в случае если 
аккаунт имеет статус "не подтверждённый" 
вывести ошибку "Аккаунт не имеет 
подтверждённых паспортных данных! Для 
верификации перейдите в личный кабинет!", в 
случае если аккаунт имеет статус 
"подтверждённый" использовать хендлер 
[DELETE /passP](https://github.com/Likoder/Likoder/blob/main/DeletePasp.md) и вновь 
отображать кнопку "Добавление паспортных данных"
в ЛК.
##
#### Визуализация БД

##### БД ФНС

![](https://sun9-74.userapi.com/impg/pJ-iOQ3ZhHCnNJKw_RcJ0rAF8Qjvq4vTlAuUsw/PsGyl38uiMU.jpg?size=208x274&quality=96&sign=ebde538fbe4fca50bf2a8ce1320d06a8&type=album)

##### БД мобильного приложения
![](https://sun9-49.userapi.com/impg/RtJAlvtAdXn1WFHe7cA9-rCH_jsRZOfzE-WBvQ/K59ac87p4SU.jpg?size=225x180&quality=96&sign=68beac00e918f55e4a5f70213e744618&type=album)
##


##

#### [Визуализация процессов при помощи _Sequence diagram_](https://app.diagrams.net/#G1LRt97hgE0UZMJUCE8OFtyhFLSXPlEMP4)
##### Процесс добавления паспортных данных в личный кабинет
![](https://sun9-73.userapi.com/impg/QTDxNMyUDkoAd5QOU8iceOkdR8GKh4_qlslt6w/3fHPNeBNF-I.jpg?size=550x557&quality=96&sign=600275a070431d119e8dcf9bfb18b6f2&type=album)
##### Процесс удаления паспортных данных
![](https://sun21-1.userapi.com/impg/ko7-9IktJjU_DSl62N1LpnLSKUrBk-6ZYIpuPQ/nvcvLXhwBxU.jpg?size=638x571&quality=96&sign=c9b01e39935e7711cd216277bf8236a0&type=album)

*БД - базы данных*

*ЛК - личный кабинет*