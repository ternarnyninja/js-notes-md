**Объекты хранят свойства (пары ключ-значение), где:**
-   Ключи свойств должны быть строками или символами (обычно строками).
-   Значения могут быть любого типа.

**Чтобы получить доступ к свойству, мы можем использовать:**

-   Запись через точку: `obj.property`.
-   Квадратные скобки `obj["property"]`. Квадратные скобки позволяют взять ключ из переменной, например, `obj[varWithKey]`.

**Дополнительные операторы:**

-   Удаление свойства: `delete obj.prop`.
-   Проверка существования свойства: `"key" in obj`.
-   Перебор свойств объекта: цикл for `for (let key in obj)`.

Объекты присваиваются и копируются по ссылке. Другими словами, переменная хранит не «значение объекта», а «ссылку» (адрес в памяти) на это значение.

---
Клонирование и объединение объектов, Object.assign
---
```
for (let key in user) { 
	clone[key] = user[key];
}
```

Кроме того, для этих целей мы можем использовать метод `Object.assign`

```
Object.assign(dest, [src1, src2, src3...])
```

-   Первый аргумент `dest` — целевой объект.
-   Остальные аргументы `src1, ..., srcN` (может быть столько, сколько нужно) являются исходными объектами
-   Метод копирует свойства всех исходных объектов `src1, ..., srcN` в целевой объект `dest`. То есть, свойства всех перечисленных объектов, начиная со второго, копируются в первый объект.
-   Возвращает объект `dest`.

Необходимо помнить, что `Object.assign` не делает глубокое клонирование объекта. 
Если внутри копируемого объекта есть свойство, значение которого не является примитивом, оно будет передано по ссылке.

---
Methods, This
---
-   Функции, которые находятся в объекте в качестве его свойств, называются «методами».
-   Методы позволяют объектам «действовать»: `object.doSomething()`.
-   Методы могут ссылаться на объект через `this`.
-   При объявлении любой функции в ней можно использовать `this`, но этот `this` не имеет значения до тех пор, пока функция не будет вызвана.
-   Эта функция может быть скопирована между объектами (из одного объекта в другой).
-   Когда функция вызывается синтаксисом «метода» – `object.method()`, значением `this` во время вызова является объект перед точкой.

Когда внутри стрелочной функции обращаются к `this`, то его значение берётся снаружи.

---
См. Также:
[[Объекты, общее]]
[[Оглавление]]