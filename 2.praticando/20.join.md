# Join




## Criar esses exemplos:


Exemplo simples:

Criar um exemplo parecido com esse:

```sql
SELECT
	s.ShipperName,
    COUNT(o.OrderID)
    
    FROM orders AS o
	INNER JOIN shippers AS s
    ON o.ShipperID = s.ShipperID
    
    GROUP BY ShipperName;
```




-- Selecione a quantidade de pedidos feitos agrupados por funcionário.
-- Só me interessa de 14 pedidos pra cima.
-- Renomeio as colunas bonitinho e referencie o nome das tabelas.


    SELECT
		e.LastName		 AS Funcionário,
        COUNT(o.OrderID) AS Qtde_Pedidos_Atendido
        
        FROM orders AS o
        INNER JOIN employees AS e
        ON o.EmployeeID = e.EmployeeID
        
        GROUP BY e.EmployeeID
        HAVING Count(o.OrderID) > '14' 
        ORDER BY Count(o.OrderID) DESC	;




-- Faça a mesma query(consulta) de cima , porém quero apenas os funcionários 'Davolio', 'Fuller'
-- Por mais que seja apenas 2 funcionários , eu ainda assim preciso agrupar.
 SELECT
		e.LastName		 AS Funcionário,
        COUNT(o.OrderID) AS Qtde_Pedidos_Atendido
        
        FROM orders AS o
        INNER JOIN employees AS e
        ON o.EmployeeID = e.EmployeeID
        
		WHERE e.LastName IN ('Fuller','Davolio')
        GROUP BY e.EmployeeID
        HAVING Count(o.OrderID) > '20' 
        ORDER BY Count(o.OrderID) DESC	;