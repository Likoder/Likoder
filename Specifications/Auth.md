# Авторизация

#### BL
* Пользователь хочет пройти аутентификацию на сервер, чтобы получить доступ к авторизации;
* Пользователь хочет пройти авторизацию через Youtrack, чтобы получить доступ к порталу.

#### BE:
#### Авторизация:

* После аутентификации доступа к серверу используется [`/portal.v1.AuthService/Auth/GetAuthURL`](https://git.tjump.ru/tages/tages-practice/analytics/-/blob/master/WW/gRPC/AuthService/GetAuthURL.md) возвращает ссылку с сервисом авторизации Youtrack
* После авторизации через сервис [Youtrack](https://youtrack-dev.tages.dev/hub/api/rest/oauth2/auth?access_type=offline&client_id=64fc07a1-24d0-4ddd-8846-5120689c232a&redirect_uri=https%3A%2F%2Ftages-admin-portal-dev.tages.dev&request_credentials=skip&response_type=code&scope=0-0-0-0-0&state=75955cd8-af99-41a8-8d86-f816c153d75f), система получает код , метод [`/portal.v1.AuthService/Auth`](https://git.tjump.ru/tages/tages-practice/analytics/-/blob/master/WW/gRPC/AuthService/Auth.md) проверяет его и возвращает `access_token`, `refresh_token`, `youtrack_refresh_token`
* При успешной авторизации пользователь попадает на страницу "Справочник", сервер возвращает данные из Youtrack, используя методы:
[`/portal.v1.EmployeeService/List`](https://git.tjump.ru/tages/tages-practice/analytics/-/blob/master/WW/gRPC/EmployeeService/List.md)
[`/portal.v1.vacationService/List`](https://git.tjump.ru/tages/tages-practice/analytics/-/blob/master/WW/gRPC/VacationService/List.md)
[`/portal.v1.OfficeInfoService/GetOfficeInfoServiceList`](https://git.tjump.ru/tages/tages-practice/analytics/-/blob/master/WW/gRPC/OfficeInfoService/GetOfficeInfoList.md)


#### Logout
* Когда приходит запрос от клиента `/portal.v1.AuthService/Logout` удалить `access_token`, `refresh_token`, `youtrack_refresh_token`

#### FE:
* При аутентификации пользователю необходимо заполнить форму:

|Name|Type|Description|
|-|--------|---|
|Login|string|Логин пользователя|
|Password|string|Пароль|

* После аутентификации для доступа к серверу происходит авторизации к порталу через заполнение формы Youtrack
