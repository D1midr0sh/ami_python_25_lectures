# Вопросы на коллоквиум

Коллоквиум будет состоять из следующего набора вопросов:

2 простых вопроса + 2 средних вопроса + 2 сложных вопроса + доп вопросы.

Простой вопрос весит 0.5 баллов, средний вопрос весит 1 балл, сложный вопрос весит 2 балла. Дополнительными вопросами можно получить еще 3 балла, чтобы добрать до 10.

Список простых, средних и сложных вопросов будет представлен в этом файле. Списка дополнительных вопросов нет - они зависят от принимающего.

Дополнительным вопросом может быть:

- Попросить студента прокомментировать код.

- Ответить на какой-то вопрос на понимание глубже чем сложных вопрос.

## IO. Типы данных.

### Простые вопросы

<details>
<summary><b>Какие способы чтения данных вы знаете?</b></summary>

`input`, `read`
</details>

<details>
<summary><b>Какие базовые типы данных в Python вы знаете?</b></summary>

`int`, `float`, `str`, `bool`, `NoneType`, etc.
</details>

<details>
<summary><b>Как преобразовать строку в целое число?</b></summary>

`int("123")`
</details>

<details>
<summary><b>Какие битовые операции вы знаете?</b></summary>

&, |, ~, ^, <<, >>
</details>

<details>
<summary><b>Как работает оператор **?</b></summary>

Возведение в степень
</details>

<details>
<summary><b>Как работает and в условиях?</b></summary>

Если левый операнд условия ложный, то правый не будет тронут интерпретатором
</details>

<details> 
<summary><b>Что будет выведено ниже?</b></summary> 

Битовый сдвиг вправо на n позиций эквивалентен целочисленному делению на 2^n. 8 >> 2 = 8 / 4 = 2. 
</details>

```python
x = 8
result = x >> 2
print(result)
```

<details> 
<summary><b>Какие преобразования корректны?</b></summary> 

Все кроме `int("3.14")`
</details>

```python
int("42"), float("3.14"), int("3.14"), str(123), int(342.11)
```

<details>
<summary><b>Что выведет?</b></summary>

`[2, 4, 6]`
</details>

```python
list(range(2,8,2))
```

---

## Ввод-вывод с файла. Циклы и условия.

### Простые вопросы

<details>
<summary><b>Какие ключевые слова связанные с циклами и условиями вы знаете?</b></summary>

`if`, `else`, `elif`, `break`, `continue`, `for`, `while`, etc...
</details>

<details>
<summary><b>В чем разница между if и match?</b></summary>

`if` - проверка булевых выражений, `match` - соответствие паттернам в структурах.
</details>

<details>
<summary><b>Что будет выведено?</b></summary>

Hello, Guest
</details>

```python
user = None
name = user and user.get("name") or "Guest"
print(f"Hello {name}")
```

<details>
<summary><b>Как работает цикл while?</b></summary>

Цикл `while` выполняет блок кода до тех пор, пока условие истинно. Синтаксис: `while условие: код`. Проверка условия происходит перед каждой итерацией.
</details>

<details>
<summary><b>Как работает цикл for?</b></summary>

Цикл `for` перебирает элементы итерируемого объекта (списка, строки, range и т.д.). Синтаксис: `for элемент in коллекция: код`. На каждой итерации переменная принимает значение следующего элемента.
</details>

---

### Средние вопросы

<details>
<summary><b>Что делает метод flush у файла?</b></summary>

Метод `flush()` принудительно записывает буферизованные данные из памяти в файл на диске, не дожидаясь закрытия файла или заполнения буфера.
</details>

<details> 
<summary><b>Что будет выведено ниже?</b></summary>

Лягушка и цветок
Не уверен
Не уверен
</details>

```python
lists = [["🐸", "🌸"], ["🐸", "🌸", "🌹"], None]

for lst in lists:
    match lst:
        case ["🐸", ("🌹" | "🌸" | "🌺" | "🌻" | "🌼")]:
            print("Лягушка и цветок")
        case _:
            print("Не уверен")
```

---

### Сложные вопросы

<details>
<summary><b>Как правильно читать данные из файла, если объём файла - несколько терабайт?</b></summary>

Нужно читать файл частями (чанками), используя методы вроде `read(size)` или итерацию по строкам `for line in file`. Это позволяет не загружать весь файл в память сразу.
</details>

---

## Контейнеры.

### Простые вопросы

<details>
<summary><b>Что такое множество?</b></summary>

Множество (`set`) - это неупорядоченная коллекция уникальных элементов. Поддерживает операции объединения, пересечения, разности. Элементы должны быть хешируемыми.
</details>

<details>
<summary><b>Что такое словарь?</b></summary>

Словарь (`dict`) - это коллекция пар ключ-значение. Ключи должны быть уникальными и хешируемыми. Обеспечивает быстрый доступ к значениям по ключу за O(1) в среднем.
</details>

<details>
<summary><b>Какое применение множеств и словарей вы знаете?</b></summary>

Множества: удаление дубликатов, проверка принадлежности, математические операции с множествами. Словари: хранение настроек, кэширование, подсчет элементов, быстрый поиск по ключу.
</details>

<details>
<summary><b>Что делает этот код?</b></summary>

Создает множество квадратов четных чисел от 0 до 9: `{0, 4, 16, 36, 64}`. Это set comprehension с фильтрацией по условию.
</details>

```python
{x**2 for x in range(10) if x % 2 == 0}
```

<details>
<summary><b>Какой объект является хешируемым?</b></summary>

Хешируемыми являются неизменяемые типы: `int`, `float`, `str`, `tuple` (если содержит только хешируемые элементы), `frozenset`, `None`, `bool`. Изменяемые типы (`list`, `dict`, `set`) - не хешируемы.
</details>

<details>
<summary><b>Что может быть ключом в словаре?</b></summary>

Любой хешируемый объект: числа, строки, кортежи (с хешируемыми элементами), `frozenset`, пользовательские объекты с `__hash__()`.
</details>

<details>
<summary><b>Что может быть значением в словаре?</b></summary>

Любой объект Python - нет ограничений. Значения могут быть изменяемыми или неизменяемыми: списки, словари, множества, функции, классы и т.д.
</details>

<details>
<summary><b>Что такое хеш?</b></summary>

Хеш - это целое число, получаемое с помощью хеш-функции из объекта. Используется для быстрого поиска в словарях и множествах. Одинаковые объекты должны иметь одинаковые хеши.
</details>

---

### Средние вопросы

<details>
<summary><b>Как берется хеш у кортежа?</b></summary>

Хеш кортежа вычисляется на основе хешей всех его элементов. Если в кортеже есть нехешируемый элемент (например, список), возникнет `TypeError`.
</details>

<details>
<summary><b>Что вы знаете о методах keys(), values(), items() в словаре? Какой тип у возвращаемых значений?</b></summary>

</details>

<details>
<summary><b>Как можно изменить кортеж?</b></summary>

Кортеж неизменяем, но можно изменить изменяемые объекты внутри него (например, список в кортеже). Также можно создать новый кортеж на основе старого с помощью конкатенации или среза.
</details>

<details>
<summary><b>Как проверить объект на хешируемость?</b></summary>

Можно вызвать `hash(obj)` и поймать исключение `TypeError`, или проверить `isinstance(obj, collections.abc.Hashable)`.
</details>

<details>
<summary><b>Как сделать множество ключом в словаре?</b></summary>

Множество `set` нельзя использовать как ключ, но можно использовать `frozenset` - неизменяемый аналог множества, который является хешируемым.
</details>

<details>
<summary><b>Что будет храниться в итоговом словаре?</b></summary>

`{True: 1.0}`. В Python `True == 1 == 1.0` и все они имеют одинаковый хеш, поэтому в словаре остается только один ключ (`True` - первый), а значение обновляется последним присвоением (`1.0`).
</details>

```python
{True: True, 1: 1, 1.0: 1.0}
```

<details>
<summary><b>Что будет напечатано в примере ниже?</b></summary>

`-2 -2` и `{-1: 'minus one', -2: 'minus two'}`. Хеш для `-1` равен `-2` (особенность Python), но это не мешает словарю различать ключи `-1` и `-2`, так как проверяется также равенство ключей.
</details>

```python
print(hash(-1), hash(-2))
data = {
    -1: "minus one",
    -2: "minus two"
}
print(data)
```

<details>
<summary><b>Что из этого может быть ключом в словаре?</b></summary>

Все перечисленные объекты могут быть ключами: `int`, `str`, `tuple` (с хешируемыми элементами), `frozenset`, `None` - все они хешируемые и неизменяемые.
</details>

```python
d = {
    1: "int",
    "a": "str",
    (1, 2): "tuple",
    frozenset([1, 2]): "frozenset",
    None: None,
}
```

<details>
<summary><b>Что выведет код и почему?</b></summary>

Код вызовет `TypeError: unhashable type: 'list'`. Список `[1, 2]` - изменяемый тип, он не может быть ключом словаря, так как не является хешируемым.
</details>

```python
my_dict = {}
my_dict[([1, 2])] = "hello"
print(my_dict)
```

<details>
<summary><b>Что эффективнее и почему?</b></summary>

Способ 1 (`if key in my_dict`) эффективнее - это прямая проверка наличия ключа за O(1). Способ 2 создает дополнительный вызов метода и проверку на `None`, что медленнее. Плюс способ 2 не сработает, если значение в словаре само равно `None`.
</details>

```python
# Способ 1
if key in my_dict:
    ...

# Способ 2
if my_dict.get(key) is not None:
    ...
```

---

### Сложные вопросы

<details>
<summary><b>Что вы знаете о методах keys(), values(), items() в словаре? Какой тип у возвращаемых значений?</b></summary>

`keys()` возвращает представление ключей (`dict_keys`), `values()` - значений (`dict_values`), `items()` - пар ключ-значение (`dict_items`). Это динамические представления, отражающие изменения словаря.
</details>

<details>
<summary><b>Верно ли утверждение, что неизменяемые объекты являются хешируемыми?</b></summary>

Не всегда. Большинство неизменяемых типов хешируемы, но кортеж с изменяемыми элементами (например, `(1, [2, 3])`) - неизменяемый, но не хешируемый, так как содержит нехешируемый список.
</details>

<details>
<summary><b>Почему мы можем добавлять сколько угодно элементов в список, словарь или множество?</b></summary>

Эти структуры динамически изменяют размер. Когда емкость заполняется, выделяется новая большая область памяти, и элементы копируются туда. Используется амортизированная стратегия роста.
</details>

<details>
<summary><b>Как развернуть значения и ключи местами в словаре? В чем могут быть проблемы?</b></summary>

`{v: k for k, v in d.items()}`. Проблемы: значения могут быть не хешируемыми (вызовет ошибку) или не уникальными (часть данных потеряется, останется последнее значение).
</details>

<details>
<summary><b>Какой из способов создать словарь валидный?</b></summary>

Валидны все, кроме `{(1, 2, []): None}` - кортеж содержит список, который нехешируем. Остальные варианты правильны: `None`, `int()` (0), `input` (функция), `frozenset()`, числа, строки, `int` (класс) - все хешируемые.
</details>

```python
(
    {None: None},
    {(1, 2, []): None},
    {int(): None},
    {input: None},
    {frozenset(): None},
    {3: None},
    {"key": None},
    {int: None},
)
```

<details>
<summary><b>Что выведет этот код?</b></summary>

`None`. Объекты `p1` и `p2` - это разные экземпляры класса с разными хешами (по умолчанию основан на id). Хотя у них одинаковые значения атрибутов, они не считаются равными для словаря без переопределения `__hash__` и `__eq__`.
</details>

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

p1 = Point(1, 2)
p2 = Point(1, 2)
my_dict = {p1: "hello"}
print(my_dict.get(p2))
```

---

## Ссылки. Изменяемость.

### Простые вопросы

<details>
<summary><b>Что выведет этот код?</b></summary>

`4`. Переменная `b` ссылается на тот же список, что и `a`. Когда мы изменяем список через `b`, изменения видны и через `a`.
</details>

```python
a = [1, 2, 3]
b = a
b.append(4)
print(len(a))
```

<details>
<summary><b>Что выведет этот код?</b></summary>

`5`. Числа - неизменяемые объекты. Операция `y += 1` создает новый объект и присваивает его `y`, а `x` продолжает ссылаться на старое значение 5.
</details>

```python
x = 5
y = x
y += 1
print(x)
```

<details>
<summary><b>Что такое переменная?</b></summary>

Переменная в Python - это имя (метка), которое ссылается на объект в памяти. Переменная не содержит сам объект, а только ссылку на него.
</details>

<details>
<summary><b>Как проверить что две переменные ссылаются на один и тот же объект?</b></summary>

Используя оператор `is`: `a is b`. Также можно сравнить идентификаторы: `id(a) == id(b)`.
</details>

<details>
<summary><b>Что выведет этот код?</b></summary>

`[1, 2, 3, 4]`. Операция `+` создает новый список, который не связан с оригинальными. Изменение `a` не влияет на `c`.
</details>

```python
a = [1, 2]
b = [3, 4]
c = a + b
a.append(5)
print(c)
```

---

### Средние вопросы

<details>
<summary><b>В чем разница между поверхностным и глубоким копированием?</b></summary>

Поверхностное (`copy.copy()`) создает новый объект, но внутренние объекты остаются теми же. Глубокое (`copy.deepcopy()`) рекурсивно копирует все вложенные объекты, создавая полностью независимую копию.
</details>

<details>
<summary><b>Можно ли сравнивать объекты при помощи is?</b></summary>

Да, но `is` проверяет идентичность объектов (одинаковые ли это объекты в памяти), а не равенство значений. Для сравнения значений используйте `==`. Обычно `is` применяют для `None`, `True`, `False`.
</details>

<details>
<summary><b>Что выведет код и почему?</b></summary>

`[1, 2, 3, 4]`. Сначала `lst.append(4)` изменяет исходный список. Затем `lst = [5, 6, 7]` создает новый локальный список и переназначает локальную переменную `lst`, но не влияет на `my_list`.
</details>

```python
def modify(lst):
    lst.append(4)
    lst = [5, 6, 7]

my_list = [1, 2, 3]
modify(my_list)
print(my_list)
```

<details>
<summary><b>Что выведет код и почему?</b></summary>

</details>

```python
a = [[0] * 5] * 5
a[0][1] = 2
a
```

<details>
<summary><b>Что выведет код и почему?</b></summary>

</details>

```python
a = [10, 20]
b = [a, 30]
a.append(b)
a[2][0][2][0][2]
```

---

### Сложные вопросы

<details>
<summary><b>Как устроен список под капотом? Почему мы можем хранить объекты разных типов?</b></summary>

</details>

<details>
<summary><b>Как работает вставка в список?</b></summary>

</details>

<details>
<summary><b>Что выведет код и почему?</b></summary>

</details>

```python
t = (1, 2, [3, 4])
t += [5, 6]
print(t)
```

<details>
<summary><b>Что выведет код и почему?</b></summary>

</details>

```python
def create_functions():
    return [lambda x: x + i for i in range(3)]

functions = create_functions()
results = [f(10) for f in functions]
print(results)
```

<details>
<summary><b>Что такое рекурсия. Какое у рекурсии должно быть обязательное свойство?</b></summary>

</details>

---

## Функции.

### Простые вопросы

<details>
<summary><b>Можно ли принимать функцию в качестве аргумента и возвращать из функции? Почему?</b></summary>

</details>

<details>
<summary><b>Функция - это изменяемый или неизменяемый объект?</b></summary>

</details>

<details>
<summary><b>Что выведет код и почему?</b></summary>

</details>

```python
def func(x):
    x = x + 1
    return x

x = 5
func(x)
print(x)
```

<details>
<summary><b>Чем отличается return от print внутри функции?</b></summary>

</details>

<details>
<summary><b>Что такое аргументы по умолчанию в функции? Для чего используются и в чем их особенность?</b></summary>

</details>


<details>
<summary><b>Что выведет этот код и почему?</b></summary>

</details>

```python
def test():
    pass

result = test()
print(result)
```

---

### Средние вопросы

<details>
<summary><b>Что выведет этот код и почему?</b></summary>

</details>

```python
def add_item(item, items=[]):
    items.append(item)
    return items

print(add_item(1))
print(add_item(2))
```

<details>
<summary><b>Что выведет этот код и почему?</b></summary>

</details>

```python
def func(a, b, c):
    return a + b + c

print(func(a=1, 2, 3))
```

<details>
<summary><b>Что такое *args и **kwargs? Как они работаю?</b></summary>

</details>

<details>
<summary><b>Что выведет этот код и почему?</b></summary>

</details>

```python
def func(a, b, c):
    return a + b + c

params = {'a': 1, 'b': 2, 'c': 3}
print(func(**params))
```

---

### Сложные вопросы

<details>
<summary><b>Что такое лямбда-функции? В чем их ограничения и когда их стоит использовать?</b></summary>

</details>

<details>
<summary><b>Поясните каждый принимаемый аргумент в этой функции.</b></summary>

</details>

```python
from typing import Literal


def create_mythical_creature(
    species: Literal["dragon", "griffin", "phoenix", "unicorn"],
    name: str,
    /,
    *abilities: list[str],
    rarity: Literal["common", "rare", "epic", "legendary"] = "common",
    habitat: str = "unknown",
    **physical_traits: dict[str, int | str],
) -> dict[str, object]:
    return {
        "species": species,
        "name": name,
        "abilities": list(abilities),
        "rarity": rarity,
        "habitat": habitat,
        "physical_traits": physical_traits,
        "description": f"A {rarity} {species} named {name} with {len(abilities)} abilities",
    }
```

---

## Классы.

### Простые вопросы

<details>
<summary><b>Что такое класс и экземпляр класса?</b></summary>

</details>

<details>
<summary><b>Что такое магический метод?</b></summary>

</details>

<details>
<summary><b>Для чего нужен магический метод __init__?</b></summary>

</details>

<details>
<summary><b>Что такое self и зачем мы его передаем первым параметром в аргументы методов класса?</b></summary>

</details>

<details>
<summary><b>В чем разница между атрибутами класса и атрибутами экземпляра?</b></summary>

</details>


<details>
<summary><b>Что выведет и почему?</b></summary>

</details>

```python
class A:
    items = []
    
    def add(self, x):
        self.items.append(x)

a1 = A()
a2 = A()
a1.add(1)
a2.add(2)
print(a1.items)
print(a2.items)
```

<details>
<summary><b>Что выведет и почему?</b></summary>

</details>

```python
class Counter:
    count = 0
    
    def __init__(self):
        self.count += 1

c1 = Counter()
c2 = Counter()
print(c1.count)
print(c2.count)
print(Counter.count)
```

---

### Средние вопросы

<details>
<summary><b>В чем разница между статичным методом и обычным методом класса?</b></summary>

</details>

<details>
<summary><b>Как реализовать приватные атрибуты в питоне?</b></summary>

</details>

<details>
<summary><b>Что такое свойства (properties) и для чего они нужны?</b></summary>

</details>

<details>
<summary><b>Что выведет этот код и почему?</b></summary>

</details>

```python
class A:
    def __init__(self):
        self.setup()

    def setup(self):
        print("A")


class B(A):
    def __init__(self):
        super().__init__()

    def setup(self):
        print("B")


obj = B()
```

---

### Сложные вопросы

<details>
<summary><b>Что такое абстрактные классы и когда их использовать?</b></summary>

</details>

<details>
<summary><b>Для чего нужны __slots__ и как они работают?</b></summary>

</details>

<details>
<summary><b>Что будет напечатано и почему?</b></summary>

</details>

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __eq__(self, other):
        return isinstance(other, Person) and self.name == other.name

    def __hash__(self):
        return hash(self.name)


p1 = Person("Alice", 25)
p2 = Person("Alice", 30)
print(p1 == p2)
print(hash(p1) == hash(p2))

d = {p1: "first"}
d[p2] = "second"
print(len(d))
```

---

## Исключения. Контекстные менеджеры.

### Простые вопросы

<details>
<summary><b>Для чего нужны исключения?</b></summary>

Подумайте
</details>

<details>
<summary><b>Как отлавливать исключения?</b></summary>

При помощи конструкции

```python
try:
    ...
except Exception:
    ...
```
</details>

<details>
<summary><b>Как перехватывать сразу несколько исключений?</b></summary>

Подумайте
</details>

<details>
<summary><b>Как работает ключевое слово else в блоке try...except?</b></summary>

Выполняется если не было проброшено исключений внутри блока try.
</details>

<details>
<summary><b>Как работает ключевое слово finally в блоке try...except?</b></summary>

Выполняется в любом случае.
</details>

<details>
<summary><b>Как создать кастомное исключение?</b></summary>

Унаследовать класс от `Exception`
</details>

<details>
<summary><b>Что такое контекстный менеджер?</b></summary>

Подумайте
</details>

---

### Средние вопросы

<details>
<summary><b>Какие минусы перехватывания Exception (имеется ввиду широкий диапазон исключений) вы можете назвать?</b></summary>

Подумайте
</details>

<details>
<summary><b>Зачем нам сохранять исключение в отдельную переменную?</b></summary>

Подумайте

</details>

```python
try:
    ...
except Exception as err:
    ...
```

<details>
<summary><b>Какие ключевые слова можно использовать в конструкции ловли исключений?</b></summary>

- `else` - расскажите как работает
- `finally` - расскажите как работает
</details>

<details>
<summary><b>Как работает этот блок кода?</b></summary>
Подумайте
</details>

```python
try:
    try:
        1 / 0
    except ZeroDivisionError as e:
        print("Логируем ошибку и пробрасываем дальше")
        raise ValueError("a") from e
except ValueError as err:
    print("c")
    raise ValueError("b") from err
```

<details>
<summary><b>Для чего нужен контекстный менеджер?</b></summary>

Подумайте
</details>

<details>
<summary><b>Какая сигнатура у магических методов, необходимых для реализации протокола контекстного менеджера?</b></summary>

Подумайте
</details>

---

### Сложные вопросы

<details>
<summary><b>В чем опасность этого контекстного менеджера? Что будет напечатано?</b></summary>

Подумайте
</details>

```python
class DatabaseConnection:
    def __enter__(self):
        print("Connecting to database...")
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        if exc_type is not None:
            print(f"Error: {exc_val}")
        print("Disconnecting from database...")
        return True


with DatabaseConnection():
    raise ValueError("Critical error!")
print("Program continues...")
```

<details>
<summary><b>Что делает и как работает этот код?</b></summary>

Подумайте
</details>

```python
from contextlib import contextmanager


@contextmanager
def magic_contextmanager() -> tp.Iterator[int]:
    print("before")
    try:
        yield 42
    except Exception as e:
        print(f"{e=}")
    finally:
        print("after")
```

---

## Протоколы и интерфейсы.

### Простые вопросы

<details>
<summary><b>Что такое протокол в Python? Приведите пример.</b></summary>

</details>

<details>
<summary><b>Что такое "Утиная типизация" (Duck Typing)? Объясните на примере.</b></summary>

</details>

<details>
<summary><b>Что такое "Гусиная типизация" (Goose Typing) и чем она отличается от утиной?</b></summary>

</details>

---

### Средние вопросы

<details>
<summary><b>Какие встроенные протоколы вы знаете? Приведите примеры.</b></summary>

</details>

<details>
<summary><b>Что такое структурная типизация (Structural Typing) и как она связана с протоколами?</b></summary>

</details>

<details>
<summary><b>Как абстрактные базовые классы (ABC) помогают в гусиной типизации?</b></summary>

</details>

<details>
<summary><b>В чем разница между isinstance() проверкой с ABC и утиной типизацией?</b></summary>

</details>

---

### Сложные вопросы

<details>
<summary><b>Как создать собственный протокол с помощью typing.Protocol?</b></summary>

</details>

<details>
<summary><b>Прокомментируйте этот код. Что мы можем делать с классом Deck? Это утиная или гусиная типизация?</b></summary>

</details>

```python
from collections import abc, namedtuple
from typing import Self

Card = namedtuple("Card", ["rank", "suit"])


class Deck(abc.MutableSequence):
    ranks = [str(n) for n in range(2, 11)] + list("JQKA")
    suits = "spades diamonds clubs hearts".split()

    def __init__(self) -> Self:
        self._cards = [Card(rank, suit) for suit in self.suits for rank in self.ranks]

    def __len__(self) -> int:
        return len(self._cards)

    def __getitem__(self, position: int) -> Card:
        return self._cards[position]

    def __setitem__(self, position: int, value: Card) -> None:
        self._cards[position] = value

    def __delitem__(self, position: int) -> None:
        del self._cards[position]

    def insert(
        self, position: int, value: Card
    ):
        self._cards.insert(position, value)
```

---

## Итераторы и генераторы.

### Простые вопросы

<details>
<summary><b>Как можно итерироваться по объекту?</b></summary>

При помощи циклов и встроенной функции `next()`.
</details>

<details>
<summary><b>По каким объектам можно итерироваться?</b></summary>

По итерируемым объектам (iterable).
</details>

<details>
<summary><b>Какой объект является итерируемым?</b></summary>

Объект, у которого реализован магический метод `__iter__()`.
</details>

<details>
<summary><b>Что такое итератор?</b></summary>

Объект, у которого реализованы магические методы `__iter__()` и `__next__()`.
</details>

<details>
<summary><b>Является ли итератор итерируемым объектом?</b></summary>

Да, является.
</details>

<details>
<summary><b>Является ли итерируемый объект итератором?</b></summary>

Нет, не является.
</details>

<details>
<summary><b>Что делает магический метод __next__?</b></summary>

Выдаёт следующий элемент итерируемого объекта.
</details>

<details>
<summary><b>Что такое генераторная функция?</b></summary>

Функция, внутри которой если ключевое слово `yield`
</details>


---

### Средние вопросы

<details>
<summary><b>Что делает магический метод __iter__?</b></summary>

Возвращает объект-итератор: либо `self`, либо отдельный класс, который позволяет итерироваться по исходному объекту.
</details>

<details>
<summary><b>Зачем нужны итераторы?</b></summary>

- **Стандартизация доступа**: Обеспечивают удобный механизм последовательного доступа к элементам коллекций без управления индексами
- **Эффективность памяти**: Позволяют работать с большими или бесконечными последовательностями без загрузки всех данных в память
- **Удобство использования**: Интеграция с конструкциями высокого уровня (цикл `for`)
</details>

<details>
<summary><b>Какое исключение выбрасывается при исчерпании итератора?</b></summary>

`StopIteration`
</details>

<details>
<summary><b>Как проверить объект на итерируемость?</b></summary>

Попробовать применить встроенную функцию `iter()` к объекту
</details>

<details>
<summary><b>Является ли объект с реализованным магическим методом __getitem__ итерируемым?</b></summary>
Да
</details>

<details>
<summary><b>Как обратиться к итерируемому объекту по индексу?</b></summary>

По дефолту никак, если очень хочется, то реализовываем `__getitem__`
</details>

<details>
<summary><b>Как пройтись по итератору заново?</b></summary>

Никак. Нужно создавать новый итератор
</details>

<details>
<summary><b>Что делает данный блок кода?</b></summary>

Это способ реализовать бесконечный ввод пока не получим "exit" на вход
</details>

```python
for _ in iter(input, "exit"):
    ...
```

<details>
<summary><b>Что такое генератор?</b></summary>

Это особый вид итератора, позволяющий итерироваться по последовательности данных без хранения полной последовательности в памяти. Генераторы генерируют объекты налету, что и делает их хорошим выбором для больших объёмов данных.
</details>

<details>
<summary><b>В каких случаях применять генератор, а в каких просто итератор?</b></summary>

</details>

<details>
<summary><b>На какие подвиды делятся генераторы?</b></summary>

Генераторная функция, генератор и генераторное выражение
</details>

<details>
<summary><b>Что делает функция repeat?</b></summary>

</details>

```python
def repeat(iterable: tp.Iterable[int], times: int | None = None):
    for _ in range(times) if times is not None else iter(int, 1):
        yield from iterable
```

<details>
<summary><b>Какое исключение пробрасывается в генератор когда мы его закрываем?</b></summary>

`GeneratorExit`
</details>

---

### Сложные вопросы

<details>
<summary><b>Какие методы у генераторов вы знаете? Расскажите подробно про каждый из них</b></summary>

`send` - отправка сообщения в генератор: таким образом можно использовать генераторную функцию как канал коммуникации

`close` - соответственно закрыть этот канал коммуникации, чтобы на другом конце поняли, что больше не нужно в него писать/читать

`throw` - пробросить исключение в канал коммуникации: например, А передал плохие аргументы в генераторную фукнцию, B их прочитал и в ответ пробросил исключение
</details>

<details>
<summary><b>Что делает функция accumulator?</b></summary>

</details>

```python
def accumulator() -> tp.Generator[int, int, None]:
    total = 0
    while True:
        try:
            value = yield total
        except GeneratorExit:
            print(f"Generator is close, {total=}")
            raise

        if value is None:
            break
        total += value
```

<details>
<summary><b>В чем проблема в функцие cycle ниже?</b></summary>

Основная проблема заключается в том, что на вход в функцию подается итерируемый объект, в том числе итераторы и генераторы, соответственно, нужно учесть следующие случаи:

- пустой список
- итератор, нужно как-то побороть иссякаемость, например, положив в список
- бесконечный генератор, нужно как-то побороть моментальное переполнение памяти когда кладем в список - кладем лениво

</details>

```python
def cycle(iterable: tp.Iterable[tp.Any]) -> tp.Iterator[tp.Any]:
    while True:
        yield from iterable
```

---

## Namespaces. Декораторы.

### Простые вопросы

<details>
<summary><b>Что такое пространство имен (namespace) в Python? Какие типы namespaces существуют?</b></summary>

</details>

<details>
<summary><b>Что такое область видимости (scope) и как работает правило LEGB?</b></summary>

</details>

<details>
<summary><b>Что такое декоратор? Для чего используется декоратор?</b></summary>

</details>

<details>
<summary><b>Как работают ключевые слова global и nonlocal?</b></summary>

</details>

---

### Средние вопросы

<details>
<summary><b>Что такое замыкание (closure) и как оно связано с пространствами имен?</b></summary>

</details>

<details>
<summary><b>Как декоратор влияет на метаданные функции и как это исправить?</b></summary>

Тут про `functools.wraps`s
</details>

---

### Сложные вопросы

<details>
<summary><b>Объясните как это работает:</b></summary>

</details>

```python
import functools
import warnings
from collections.abc import Callable
from datetime import date, datetime
import typing as tp


P = tp.ParamSpec("P")
R = tp.TypeVar("R")


def deprecated(
    *, since: date | datetime | None = None
) -> Callable[[Callable[P, R]], Callable[P, R]]:
    def decorator(func: Callable[P, R]) -> Callable[P, R]:
        @functools.wraps(func)
        def wrapper(*args: P.args, **kwargs: P.kwargs) -> R:
            parts: list[str] = [f"Function {func.__name__}() is deprecated."]
            if since is not None:
                stamp = (
                    since.date().isoformat()
                    if isinstance(since, datetime)
                    else since.isoformat()
                )
                parts.append(f"Since {stamp}.")
            warnings.warn(" ".join(parts), DeprecationWarning)
            return func(*args, **kwargs)

        return wrapper

    return decorator
```

<details>
<summary><b>Как работают цепочки декораторов? Какие нюансы нужно учитывать при написании цепочки?</b></summary>

</details>

---