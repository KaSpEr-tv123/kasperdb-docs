# Метод set
Функция `set` используется для установки значения в указанной таблице и ключе в базе данных. Если ключ уже существует в таблице, то его значение будет заменено на новое.

## Параметры
- `key` - строка, обязательный параметр, ключ для уникальной идентификации записи;
- `value` - любой тип данных, обязательный параметр, значение для сохранения в базе данных


## Пример использования
```python
from kasperdb import db, config
import random

config.debug = True #логи в консоли о действиях дб можно убрать.

db.create("t") #создать базу данных под названием t

data = db.get("t") #получаем то, что у нас в базе
print(data) #выводим базу

f = ["you're gay!", "you're not gay!"] #список "хрени"
data["you're gay?"] = random.choice(f) #записываем в переменную базы данных хандом херню из списка
db.set("t", data) #записываем новые данные

print(db.get("t")) #выводим результат добавления данных

db.delete("t") #удаляем базу данных t
```