В любом случае перед тем как начать работать с rails должны быть произведены настройки postgres
	sudo -i -u  postgres psql - запустить консольный менеджер от имени(роли postgres) db postgres
	\l (list) посмотреть все базы данных
	\l+ рашширенные характеристики баз данных
	\du - узнать какие роли есть в системе 
	\с имя_бызы_данных - коннектится с базой данных
	\dt - показать таблицы базы данных
	ИМЯ ТЕКУЩЕГО ПОЛЬЗОВАТЕЛЯ является имененм роли в базе данных
	
	CREATE ROLE new_role_name; -создание новой роли из psql 
	createuser test_user - создание роли из консоли
	DROP ROLE IF EXISTS role_name;
	
		создание быэкапа
			pg_dump -h хост -U имя_роли -F формат_дампа -f путь_к_дампу имя_БД
			pg_dump -h localhost -U mybase -F c -f /home/user/backups/dump.tar.gz mybase
		Восстановление из резервной копии выполняется аналогичным образом: 	
			pg_restore -h хост -U имя_роли -F формат_дампа -d имя_базы путь_к_дампу 
	\h CREATE ROLE - посмотреть возможные права
	ALTER ROLE role_name WITH атрибуты из предъидущей команды; - поменять права роли
	
	\password user - установить пароль для роли
	\q - выход
	
	CREATE DATABASE назыание_базы днанных OWNER имя_владельца - Созание базы данных от имени postgress внутри psql

Часть 1 создание rails приложения с базой данных postgreSQL
	rails new имя приложения --database=postgresql
	следовать инструкции из yml файла
	1.Создание базы данных из консоли 
	createdb имя_БД (название совпадает в db.yml) 
	
	
Часть 2 изменение базы данных с sqlite3 на PostgreSql
	добавить gem 'pg' в гемфайл
	bundle install 
	внести изменения в config/database.yml
		development:  
			adapter:
			encoding:
			database:
			host:
			pool:
			username:
			userpassword:
			
