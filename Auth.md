# Авторизация

#### Бизнес-логика
* Пользователь хочет пройти аутентификацию на сервер, чтобы получить доступ к авторизации;
* Пользователь хочет пройти авторизацию через Youtrack, чтобы получить доступ к порталу.

#### BE:
#### Авторизация:
* После аутентификации доступа к серверу используется `/portal.v1.AuthService/Auth/GetAuthURL` возвращает ссылку с сервисом авторизации Youtrack
* После авторизации через сервис Youtrack если система получает код - возвращает `access_token`, `refresh_token`, `youtrack_refresh_token`
* При успешной авторизации пользователь попадает на страницу "Справочник", сервер возвращает данные из Youtrack, используя методы:
`/portal.v1.EmployeeService/List`
`/portal.v1.vacationService/List`
`/portal.v1.OfficeInfoService/GetOfficeInfoServiceList`

#### Добавить/удалить роль админа:
* После нажатия на кнопку "Добавить роль админа" сервер возвращает `/portal.v1.AdminService/SetRoleUser` 
* После нажатия на кнопку "Удалить роль админа" сервер возвращает `/portal.v1.AdminService/RevokeUserRole` 

#### Дни рождения:
* При переходе во вкладку "Дни рождения" сервер возвращает
`/portal.v1.FriendService/List` 
`/portal.v1.ChildrenService/List` 
***
(описать logout)
***
ux:

 используется `/portal.v1.AuthService/Auth`
ui:
* При аутентификации пользователю необходимо заполнить форму
(Пример формы)
* После аутентификации для доступа к серверу происходит авторизации к порталу через заполнение формы Youtrack
(пример формы)
* 




***
`/portal.v1.AdminService/UserList`

`/portal.v1.EventsService`

`/portal.v1.LibraryService`
`/portal.v1.kbaseService`
`/portal.v1.retroService`
`/portal.v1.socialProjectService`
ux:
ui:
