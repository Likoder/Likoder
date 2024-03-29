# Задача:
**В мобильное приложение требуется добавить 
возможность, чтобы каждый пользователь мог указать 
свои паспортные данные, которые должны проверяться по ИНН, корректные данные должны отправляться в базу данных о пользователе. Также у пользователя должна быть возмоижность удалять паспортные данные через службу поддержки.**
##
1. (UI) Создание кнопки "Добавления паспортных данных" для пользователя в его личном кабинете. Данная кнопка должна переадресовывать на страницу для ввода паспортных данных(Пункт №2).
##
2. (UI) Создание страницы с использованием `API ФНС(innfl)`  для ввода паспортных данных:
- Фамилия;
- Имя;
- Отчество(при наличии);
- Дата рождения;
- Тип документа; 
- Серия и номер документа;
- Дата выдачи документа.<br>
И получения ИНН `(массив items[])`.
  1. **Валидация**<br>
  В строках: "Фамилия", "Имя", "Отчество" происвести валидацию так , чтобы допускалось 
  вводить только символы кириллицы,одиночные пробелы,дефисы,точки,
  запятые и круглые скобки.<br> 
  В строке "Cерия и номер документа" происвести валидацию так , чтобы допускалось вводить только от 9 до 10 символов

| Name|Type| Required fields           |Description    | 
|-----|----|---------------------------|-------------------------------------|
|fname|string| Обязательное поле         |Имя                                 | 
|lname|string| Обязательное поле         |Фамилия                             | 
|mname|string| Обязательное поле         |Отчество                            | 
|typeDoc|integer| Условно-обязательное поле |Вид документа, удостоверяющего личность:<br>  01 - Паспорт гражданина СССР<br>03 - Свидетельство о рождении<br>10 - Паспорт иностранного гражданина<br>12 - Вид на жительство в Российской Федерации<br>15 - Разрешение на временное проживание в Российской Федерации<br>19 - Свидетельство о предоставлении временного убежища на территории Российской Федерации<br>21 - Паспорт гражданина Российской Федерации<br>23 - Свидетельство о рождении, выданное уполномоченным органом иностранного государства
|dateOfBirth|date| Обязательное поле         |Дата рождения
|sernumDoc|string| Обязательное поле         |Серия и номер документа | 
|dateOfIssue|date| Необязательое поле        |Дата выдачи документа
##


3. (UI) После успешного ввода паспортных данных клиентом(клиент не должен иметь 1(`ban`) или 2(`deleted`), в поле `is_banned`, в Таблице(`user`) ) 
,поменять статус пользователя на 2(_В обработке_).
##
4. (Backend) Используя хендлер [GET /user](https://github.com/Likoder/Likoder/blob/main/GETuser.md), запросить данные пользователя. Далее проверить его сессию в БД(user).
##
5. (Backend) Запросить данные с сервера ФНС с помощью `API(innfl)`.
##
6. (Backend & Frontend) После ответа с ФНС , проверить данные, если все верно, 
отправить их в таблицу(`usersData`), с помощью хендлера 
[POST /user](https://github.com/Likoder/Likoder/blob/main/PostUser.md)
. Пользователю изменить статус на 1(_Подтвержден_), при отсутствии - статус 0
(_Неподтвержден_), в этом случае дать клиенту заполнить данные
вновь(не более 3 раз). 
В ином случае кнопка добавления документа исчезает из ЛК.   

##
7. (Backend) Создать раздел в службе поддержке 
"Удаление паспортных данных", в случае если 
аккаунт имеет статус "не подтверждённый" 
вывести ошибку "Аккаунт не имеет 
подтверждённых паспортных данных! Для 
верификации перейдите в личный кабинет!", в 
случае если аккаунт имеет статус 
"подтверждённый" использовать хендлер 
[DELETE /passP](https://github.com/Likoder/Likoder/blob/main/DeletePasp.md), ручку может использовать только юзер ,в БД(user) ,в поле "is_role" которого стоит 2(admin) , и поле is_banned не 1(ban) или 2(deleted), после удаления вновь 
отображать кнопку "Добавление паспортных данных" пользователю 
в ЛК.
##
#### Визуализация БД



![](https://sun9-54.userapi.com/impg/co1IjWvgWVlaX8j3oXP7zlX9rfhvS9SCgoY_uw/RiN_Hn9he2g.jpg?size=471x242&quality=96&sign=d145095b35aaa5a1e1321beb330097f3&type=album)


##


##

#### [Визуализация процессов при помощи _Sequence diagram_](https://app.diagrams.net/#G1LRt97hgE0UZMJUCE8OFtyhFLSXPlEMP4)
##### Процесс добавления паспортных данных в личный кабинет
![](https://sun9-73.userapi.com/impg/QTDxNMyUDkoAd5QOU8iceOkdR8GKh4_qlslt6w/3fHPNeBNF-I.jpg?size=550x557&quality=96&sign=600275a070431d119e8dcf9bfb18b6f2&type=album)
##### Процесс удаления паспортных данных
![](https://sun21-1.userapi.com/impg/ko7-9IktJjU_DSl62N1LpnLSKUrBk-6ZYIpuPQ/nvcvLXhwBxU.jpg?size=638x571&quality=96&sign=c9b01e39935e7711cd216277bf8236a0&type=album)

*БД - базы данных*

*ЛК - личный кабинет*
