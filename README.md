# LinuxTeacher-Docker

Установлено: на хостовую машину Ubuntu 24.04.

Домашнее задание:

**Цель домашнего задания:**

**Освоить базовые принципы работы с Docker, научиться создавать, настраивать и управлять контейнерами**

Установить на хостовую машину Docker:

<img width="1254" height="446" alt="image" src="https://github.com/user-attachments/assets/c29b4e33-c4a9-4189-a754-3d3a4fa6c975" />

Убеждаемся, что Docker установлен:

<img width="1254" height="67" alt="image" src="https://github.com/user-attachments/assets/1f88f94d-467e-4869-8028-6bebddf97f7d" />

Протестируем Dcoker:

<img width="1257" height="536" alt="image" src="https://github.com/user-attachments/assets/e0e99dc3-6a28-4a29-88fa-b2d8c8d65b92" />

Docker compose version:

<img width="1138" height="53" alt="image" src="https://github.com/user-attachments/assets/3f8fd0b5-6c54-404f-9146-8fee44bf4022" />

Docekr установлен

Продолжен. Создадим свой образ nginx на базе alpine:

<img width="1251" height="552" alt="image" src="https://github.com/user-attachments/assets/20b440ea-611a-4466-801f-ae0c6a3d88b9" />

Посмотрим список образов:

<img width="1251" height="101" alt="image" src="https://github.com/user-attachments/assets/21c3b9ca-fbb7-4f3b-8110-644fa02995f9" />

Видим наш образ nicknick/nginx:v1

Ураааа ))

Запустим наш nginx:

<img width="1246" height="69" alt="image" src="https://github.com/user-attachments/assets/53305a1e-5255-4c7f-9a69-48bc0ec4313f" />

<img width="1246" height="51" alt="image" src="https://github.com/user-attachments/assets/c8bc9e32-3063-41ab-bf7c-2afee382aad4" />

Получили доступ на наш nginx. Yes ))

Пройдемся по командам из ДЗ:

Запустим контейнер

<img width="1246" height="51" alt="image" src="https://github.com/user-attachments/assets/6aeb11d6-2433-4059-b040-25a2ebe9177b" />

<img width="1548" height="51" alt="image" src="https://github.com/user-attachments/assets/64267d76-1b35-467a-bbfd-c347239f89c5" />

Остановим контейнер

<img width="7" height="2" alt="image" src="https://github.com/user-attachments/assets/eee5cec2-eaab-4a11-852b-f5b7c48c1d26" />

Нашего контейнера нету:

<img width="1183" height="66" alt="image" src="https://github.com/user-attachments/assets/922e5183-4cdd-485e-a490-11a6838d8639" />

docker logs  - вывод был пустой

Будет приложен файл (inspect.txt) выводы команды - docker inspect 057a66be9e2c 

Создание второй версии своего образа

<img width="1183" height="511" alt="image" src="https://github.com/user-attachments/assets/4243e853-4574-42db-9c1f-3299aa73cd82" />


**В чем разница между Образом и контейнером**

**Образ** — это неизменяемый шаблон, содержащий всё необходимое для запуска приложения: код, среду выполнения, библиотеки, зависимости, переменные окружения и инструкции по запуску.
Ключевые характеристики образа:

**Неизменяемость.** После создания образ нельзя изменить напрямую. Если нужно обновить приложение, создаётся новый образ с дополнительными слоями. 

**Слоистая структура.** Образ состоит из нескольких слоёв файловой системы, каждый из которых представляет собой результат выполнения одной из инструкций в Dockerfile (например, 

копирование файлов или установка пакета). 

**Переносимость.** Образ можно передавать между разными средами (разработка, тестирование, продакшн), обеспечивая консистентность окружения. 

**Хранение.** Образы хранятся в реестрах (например, Docker Hub). 


**Контейнер** — это запущенный экземпляр образа. Это уже не просто шаблон, а работающая среда, в которой приложение выполняет свои задачи.

**Изменяемость (временно).** При запуске контейнера поверх образа добавляется тонкий слой для записи (read-write layer). Все изменения (создание файлов, модификация логов, установка временных пакетов) происходят именно в этом слое. 

**Изолированная среда.** Контейнер работает в изолированном окружении, используя ядро операционной системы хоста. Это обеспечивает изоляцию процессов и файловой системы. 

**Эфемерность.** По умолчанию данные внутри контейнера не сохраняются после его остановки и удаления. Для постоянного хранения используются тома (volumes). 

**Управляемость.** Контейнер можно запускать, останавливать, перемещать, удалять.
