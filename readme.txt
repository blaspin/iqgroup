Первоначальный запуск приложения:
1. Откройте папку проекта в терминале
2. Для запуска сервера выполните команду php artisan serve
3. Для миграции выполните php artisan migrate
4. Готово! Для просмотра url для работы с API выполните команду php artisan route:list
5. Также вы можете заполнить базу данных тестовыми данными командой php artisan db:seed

Запросы(в качестве передачи данных используются headers):
getToken(POST получает токен для дальнейшего пользования API): 
	in: name, password
	out: api_token, response_status
req(GET получает список запросов пользователя): 
	in: api_token
	out: json, response_status
req/{id}(GET получает конкретный запрос пользователя):
	in: api_token, {id}
	out: json, response_status
req(POST пользователь создаёт новый запрос):
	in: api_token, topic, message
	out: response_status
req/control(GET просмотр всех заявок(только для менеджеров)):
	in: api_token
	out: json, response_status
req/control(PUT обновление заявки(только для менеджеров)):
	in: api_token, id, status(uri encoded) и/или comment
	out: response_status
