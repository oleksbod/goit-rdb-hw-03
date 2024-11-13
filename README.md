# goit-rdb-hw-03

1. Напишіть SQL команду, за допомогою якої можна:
- вибрати всі стовпчики (За допомогою wildcard “*”) з таблиці products;
```
SELECT *
FROM mydb.products;
```
- вибрати тільки стовпчики name, phone з таблиці shippers,
```
SELECT name, phone
FROM mydb.shippers;
```
та перевірте правильність її виконання в MySQL Workbench.

2. Напишіть SQL команду, за допомогою якої можна знайти середнє, максимальне 
та мінімальне значення стовпчика price таблички products, 
та перевірте правильність її виконання в MySQL Workbench.
```
SELECT 
	avg(price) as average_price, 
	min(price) as min_price, 
	max(price) as max_price
FROM mydb.products;
```

3. Напишіть SQL команду, за допомогою якої можна обрати унікальні значення колонок 
category_id та price таблиці products.
Оберіть порядок виведення на екран за спаданням значення price та виберіть тільки 10 рядків. 
Перевірте правильність виконання команди в MySQL Workbench.
```
SELECT DISTINCT category_id, price
FROM products
ORDER BY price DESC
LIMIT 10;
```

4. Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків), 
які знаходиться в цінових межах від 20 до 100, та перевірте правильність її виконання в MySQL Workbench.
```
SELECT COUNT(*) AS product_count
FROM mydb.products
WHERE price > 20 AND price < 100;
```

5. Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків) та середню ціну (price) 
у кожного постачальника (supplier_id), та перевірте правильність її виконання в MySQL Workbench.
```
SELECT 
	supplier_id, 
	COUNT(*) AS product_count, 
	AVG(price) AS average_price
FROM mydb.products
GROUP BY supplier_id;
```
