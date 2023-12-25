# 📌 bash

Иногда есть необходимость работать с удаленными серверами, не имеющими графического интерфейса. В этом случае полезно иметь возможность использовать команды bash. Они позволяют нам выполнять обычные действия, такие как создание, редактирование, удаление файлов и папок через CLI.

Хочу поделиться некоторыми командами bash, которые использовала для выполнения задач во время обучения.

## Задание 1

##### Работа с файлами и директориями
```bash
# Открыть домашнюю директорию:
cd ~
# Определить имя папки, в которой вы находитесь:
pwd
# Создать внутри этой папки каталог  с именем test1:
mkdir test1
# Перейти в папку test1:
cd test1
# Создать файл 1,2 и 3 внутри каталога test1:
touch 1 2 3
# Проверить содержимое каталога test1:
ls
# Перейти в домашнюю директорию:
cd ~
# Создать папку test2 внутри домашней директории:
mkdir test2
# Удалить папку test2:
rm -R test2
# Удалить файл 2 из папки test1:
rm test1/2
# Создать папку в домашней директории test3 и добавить в нее два файла:
mkdir test3 && touch test3/4 test3/5
# Удалить папку test3:
rm -R test3
# Создать папку test4 в домашней директории:mkdir test4:
mkdir test4
# Переместить файлы 1 и 3 из папки test1 в папку test4:
mv test1/1 test4 
mv test1/3 test4
# Добавить в файл 1 три строки со словами line:
echo -e "line\n line\n line\n" >> 1
# Посмотреть содержимое файла 1:
cat 1
# Добавьте в файл 3 три строки со словами line:
echo -e "line\n line\n line\n" >> 3
# Просмотрите содержимое двух файлов (1 и 3) сразу:
cat 1 3 
# Используя один из редакторов замените все строки в файле 1:
echo "line" | sed 's/line/Ll/' ./1
```
## Задание 2
##### Редактирование файлов, проверка и завершение процессов, пинг веб-сайтов
```bash
# Зайти в домашнюю директорию:
cd ~
# Создать папку test 3:
mkdir test3
# Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4:
cd test3
touch 4 5 6 && echo -e "rоw1\nrоw2\nrоw3\nrоw4" | tee  *
# Найдите строку row2 в файле 5:
grep -i rоw2 test3/5
# Найдите строку row в папке test3:
grep -r "rоw" test3
# Посчитайте сколько строк с содержимым row в файле 6:
grep row test3/6 | wc -l
# Найдите файл 5 внутри папки test3:
find test3 -type f -name "5"
# Используя команду find, удалите файл 5:
find test3 -type f -name "5" -delete
# Используя команду echo, добавьте слово test в файл 4:
echo -e "test" >> test3/4
# Замените слово test в файле 4 на fail:
sed -i 's/test/fail/' test3/4
# Добавьте в файл 4 слово test так, чтобы сохранилось содержимое:
echo -e "test" >> test3/4
# Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе:
ps aux
# Убейте процесс 666 в консоли:
kill 666
# Узнайте доступность ресурса artsiomrusau.com, используя ping:
ping artsiomrusau.com
# Отправьте 5 пакетов на сайт artsiomrusau.com:
ping -c 5 artsiomrusau.com
# Используя GET и команду curl, получите информацию о зарегистрированных питомцах на https://petstore.swagger.io/:
curl -X GET https://petstore.swagger.io/v2/pet/findByStatus?status=available
# Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/:
curl -X POST https://petstore.swagger.io/v2/user -H 'Content-Type: application/json' -d '{"id":9878546789,"username": "BASH","firstName": "LINUX","lastName": "TERMINAL","email": "string@null.com","password": "zbl","phone": "879789789","userStatus": 0}'
```

```

