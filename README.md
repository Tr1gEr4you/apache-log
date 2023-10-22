## Создать бд

```console
sudo -i -u postgres
psql -U username -d myDataBase -a -f path/to/table.sql
exit
```

## Запустить сервер с pipenv

```console
pip install pipenv
pipenv install
pipenv run python3 main.py
```

## Формат запроса

- `DataBase_update` - **POST** метод. Возвращает `{"status" : "ok"}`. Used to update database with log files. 
- `DataBase_get_log`- **GET** метод. Принимает два аргумента: `from` и `to`. Возвращает массив из **JSON**, each of them have `{"address" : "192.168.0.1", "date" : "2023-06-22-13-00-00}` structure. Date must be in **YYYY-MM-DD-HH-mm-dd** format. You can get all entries in database, by providing `from=all` argument. 
## Пример запроса

## http
```
POST http://127.0.0.1:5000/DataBase_update
{"status" : "ok"}

GET http://127.0.0.1:5000/DataBase_get_log?from=2023-06-22-12-45-10&to=2023-06-24-15-34-00
[{"address" : "192.168.0.1", "date" : "2023-06-22-13-00-00}, ...]

GET http://127.0.0.1:5000/DataBase_get_log?from=all
[{"address" : "192.168.0.1", "date" : "2023-06-22-13-00-00}, ...]
```


