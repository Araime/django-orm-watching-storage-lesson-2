# Пульт охраны банка

Внимание! Если вы попали попали на данный репозиторий случайно, то вы не
сможете его запустить, т.к. у вас нет данных для доступа к БД, но вы можете
использовать код вёрстки и механизм реализации запросов в своих целях.

Программа "Пульт охраны банка" подключается к базе данных, отправляет запросы и 
отображает данные на локальном сайте. 

### Как установить?

#### Скачать

Python3 должен быть уже установлен. Скачать этот репозиторий себе на компьютер.

Рекомендуется использовать [virtualenv/venv](https://docs.python.org/3/library/venv.html)
для изоляции проекта.

#### Быстрая настройка venv

Начниая с версии Python 3.3 виртуальное окружение идёт в комплекте в виде модуля
venv. Чтобы его установить и активировать нужно выполнить следующие действия в
командной строке:  

Указать репозиторий в качестве каталога.
```
cd C:\Users\Ваш_пользователь\Downloads\django-orm-watching-storage-master
```
Установить виртуальное окружение в выбраном каталоге.
```
Python -m venv env
```
В репозитории появится папка виртуального окружения env
<a href="https://imgbb.com/"><img src="https://i.ibb.co/Hn4C6PD/image.png" alt="image" border="0"></a>

Активировать виртуальное окружение.
```
env\scripts\activate
```
Теперь вы работаете в виртуальном окружении.
<a href="https://imgbb.com/"><img src="https://i.ibb.co/tqRT7Z6/2.png" alt="2" border="0"></a>

#### Установить зависимости

Используйте `pip` (или `pip3`, есть конфликт с Python2) для установки 
зависимостей:

```python
pip install -r requirements.txt
```

### Добавить данные для БД

Необходимо в корне репозитория создать файл .env и добавить в него следующие
параметры:

```
HOST=Адрес вашей БД
NAME=Имя БД
USER=Имя пользователя
PASSWORD=Пароль
SECRET_KEY=Секретный ключ сайта
DEBUG=Найстройка режима отладки(True или False)
```

### Использование

Скрипт запускается командой:
```
python manage.py runserver 0.0.0.0:8000
```
Скрипт запущен, сайт доступен по локальному адресу [http://127.0.0.1:8000/](http://127.0.0.1:8000/)  
(или по локальному адресу [http://0.0.0.0:8000/](http://0.0.0.0:8000/))

Программа получает карты всех сотрудников банка и отображает только активные 
пропуска на главной странице.  

Также реализованы дополнительные функции:  

  1. На отдельной странице сайта вы можете посмотреть, кто в данный момент 
находится в хранилище и продолжительность пребывания.  
  1. На главной странице, когда вы нажимаете на имя сотрудника, вы можете 
получить список его посещений за все время. Если продолжительность 
сеанса составляла более одного часа, в столбце "был ли сеанс 
подозрительным?" отображается флаг True."

### Цель проекта

Код написан в образовательных целях на онлайн-курсе для веб-разработчиков 
[dvmn.org](https://dvmn.org).