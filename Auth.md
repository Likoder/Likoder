# Авторизация

#### Бизнес-логика
* Пользователь хочет пройти аутентификацию на сервер, чтобы получить доступ к авторизации;
* Пользователь хочет пройти авторизацию через Youtrack, чтобы получить доступ к порталу.

#### BE:
#### Авторизация:

* После аутентификации доступа к серверу используется `/portal.v1.AuthService/Auth/GetAuthURL` возвращает ссылку с сервисом авторизации Youtrack
* После авторизации через сервис [Youtrack](https://youtrack-dev.tages.dev/hub/api/rest/oauth2/auth?access_type=offline&client_id=64fc07a1-24d0-4ddd-8846-5120689c232a&redirect_uri=https%3A%2F%2Ftages-admin-portal-dev.tages.dev&request_credentials=skip&response_type=code&scope=0-0-0-0-0&state=75955cd8-af99-41a8-8d86-f816c153d75f) если система получает код - возвращает `access_token`, `refresh_token`, `youtrack_refresh_token`
* При успешной авторизации пользователь попадает на страницу "Справочник", сервер возвращает данные из Youtrack, используя методы:
`/portal.v1.EmployeeService/List`
`/portal.v1.vacationService/List`
`/portal.v1.OfficeInfoService/GetOfficeInfoServiceList`

#### Дни рождения:
* При переходе во вкладку ["Дни рождения"](https://tages-admin-portal-dev.tages.dev/handbook/birthdays) сервер возвращает
`/portal.v1.FriendService/List` 
`/portal.v1.ChildrenService/List`

#### Logout
* Когда приходит запрос от клиента `/portal.v1.AuthService/Logout` удалить `access_token`, `refresh_token`, `youtrack_refresh_token`

#### FE:
* При аутентификации пользователю необходимо заполнить форму:

|Name|Type|Description|
|-|--------|---|
|Login|string|Логин пользователя|
|Password|string|Пароль|

* После аутентификации для доступа к серверу происходит авторизации к порталу через заполнение формы Youtrack
