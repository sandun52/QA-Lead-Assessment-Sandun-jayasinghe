SELECT u.*
FROM users u
JOIN orders o ON u.user_id = o.user_id
GROUP BY u.user_id
HAVING COUNT(o.order_id) > 5;

 SELECT 
    o.order_id,
    o.order_date,
    o.total_amount,
    c.customer_id,
    c.first_name,
    c.last_name,
    c.email
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id;


SELECT COUNT(*) AS low_inventory_count
FROM products
WHERE inventory_quantity < 10;
