Task manager Django app / Трекер задач

Проект на Heroku: https://quiet-harbor-46674.herokuapp.com/

Для расширения функцианала приложения необходимо быть авторизованным пользователем, поэтому необходимо зайти в администартивную панель, используйте следующие данные:
        
        логин - pws_admin
        пароль - sf_password

Разворачиваем проект:

1. Скачайте репозиторий
2. Создайт виртуальное окружение: 

        python -m venv env
       
3. Активируйте виртуальное окружение: 

        source env/bin/activate
        
4. Чтобы установить все требуемые библиотеки python в новом окружении выполните команду: 

        pip install -r requirements.txt
   
   Если у вас macOS до выполнения команды pip install -r requirements.txt выполните команду:       
   
           env LDFLAGS="-I/usr/local/opt/openssl/include -L/usr/local/opt/openssl/lib" pip install psycopg2==2.8.4      
   
   Для предотвращения появления ошибки (error: command 'gcc' failed with exit status 1.) при установке зависимостей.
   
5. Примените миграции для создания бд: 

       python manage.py migrate

6. Чтбы запустить сервер введите команду: 

       python manage.py runserver

7. Для входа в администравтивную панель проекта создайте суперпользователя при помощи команды: 

       python manage.py createsuperuser

*** При создании категории(category) в административной панели, в поле slug используйте бувы атинского алфавита.

8. На вкладке 'Текущее время и дата' вы получите их значени, которые закешируются на 5 минут.
