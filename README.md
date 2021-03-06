# Task manager Django app / Трекер задач

     Django, Sqlite3, Memcached

Проект на Heroku: https://quiet-harbor-46674.herokuapp.com/

Разворачиваем проект локально:

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


Описание проекта:

1. При локальном запуске при переходе по адресу http://127.0.0.1:8000/ перед вами будет следующий интерфейс приложения

   ![Главная](/screenshots/screen_1.png)

2. Для того чтобы добавить задачи, категории и приоритеты необходимо войти от имени админимстратора в панель Django 

   - Административная панель Django

   ![Административная панель](/screenshots/screen_4.png)
   
   - Спсиок задач
   
   ![Спсиок задач](/screenshots/screen_5.png)
   
   - Подробная информация о задаче
   
   ![Информация о задаче](/screenshots/screen_6.png)
   
   - Список категорий
   
   ![Список категорий](/screenshots/screen_7.png)
   
   - Подробная информация о категории
   
    *** При создании категории(category) в административной панели, в поле slug используйте бувы атинского алфавита
   
   ![Информация о категории](/screenshots/screen_8.png)
   
   - Список приоритетов
   
   ![Список приоритетов](/screenshots/screen_9.png)
   
   - Подробная информация о приоритете
   
   ![Информация о приоритете](/screenshots/screen_10.png)

3. После добавления задач, категорий и приоритетов через административную панель, на главной странице будет отображена следующая информация:
   
   ![Главная](/screenshots/screen_2.png)
   
   - При переходе в конкретную категорию будут отображены только те задачи которые описаны в ней
   
   ![Задачи одной категории](/screenshots/screen_11.png)
   
   - При выборе определенной задачи можно получить подробную информацию по ней
   
   ![Информация выбранной о задаче](/screenshots/screen_12.png)
   
 4. Перейдя в меню на страницу "Текущее время и дата" вперед вами появятся текущее число и дата (datetime.now). Страница (и дата на ней) кэшироваться на 5 минут (для этогоиспользуется memcached). Это значит, что при первом доступе на этой странице сохраняется дата, но в ближайшие 5 минут от этого она не изменяется.
   
   ![Главная](/screenshots/screen_3.png)


