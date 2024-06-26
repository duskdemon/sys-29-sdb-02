# Домашнее задание к занятию "`Кеширование Redis/memcached`" - `Дунаев Дмитрий`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1. Кеширование 

Приведите примеры проблем, которые может решить кеширование. 

*Приведите ответ в свободной форме.*

---

### Решение 1. Кеширование

Кэширование помогает уменьшить время отклика в различных ситуациях путем сохранения данных, которые могут быть запрошены, в быстрое хранилище, например, в опреативную память. Как примеры использования:

1. Кэширование запросов DNS имен, позволяет быстрее открывать сайты в браузере;
2. Кэширование тяжелого запроса в базу данных, позволяет быстрее получить ответ;
3. Кэширование часто запрашиваемых файлов на файловом сервере позволяет быстрее отдать их, не считывая с медленного диска.

---

### Задание 2. Memcached

Установите и запустите memcached.

*Приведите скриншот systemctl status memcached, где будет видно, что memcached запущен.*

---

### Решение 2. Memcached

С помощью docker загружен и запущен контейнер с memcached, входим в него по telnet и запрашиваем stats:

![memcached](./img/sdb-02-cach-mc01.png)

---

### Задание 3. Удаление по TTL в Memcached

Запишите в memcached несколько ключей с любыми именами и значениями, для которых выставлен TTL 5. 

*Приведите скриншот, на котором видно, что спустя 5 секунд ключи удалились из базы.*

---

### Решение 3. Удаление по TTL в Memcached

Добавлены 3 значения name1, name2, name3, все они очистились спустя 5 секунд, т.к. TTL выставлен в 5:

![memcached TTL](./img/sdb-02-cach-mc02.png)

---

### Задание 4. Запись данных в Redis

Запишите в Redis несколько ключей с любыми именами и значениями. 

*Через redis-cli достаньте все записанные ключи и значения из базы, приведите скриншот этой операции.*

---

### Решение 4. Запись данных в Redis

Добавлены 3 значения name1, name2, name3 в redis через redis-cli, запрошены их значения:

![redis](./img/sdb-02-cach-rs01.png)

---

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже разобраться в материале.

### Задание 5*. Работа с числами 

Запишите в Redis ключ key5 со значением типа "int" равным числу 5. Увеличьте его на 5, чтобы в итоге в значении лежало число 10.  

*Приведите скриншот, где будут проделаны все операции и будет видно, что значение key5 стало равно 10.*

---

## Решение 5*. Работа с числами

Добавлено числовое значение 5, затем увеличено на 5, после чего значение стало равно 10:

![redis](./img/sdb-02-cach-rs02.png)
