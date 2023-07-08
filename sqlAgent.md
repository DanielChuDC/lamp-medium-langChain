```js
graph TD
Start --> A
A(Action: info-sql)--> C(Action: list-tables-sql)
C --> E(Action: query-sql)
E -->  F(Action: info-sql 2)
F -->  D(Action: query-sql 2 )
D --> End

    
%% Observations %%
A --> |"`Observation: 
Error: Wrong target table name: the table order 
was not found in the database`"| A
C --> |"`Observation: 
The table order does not exist in the database. I should check the correct table name.
Output: orders, suppliers`"| C
E --> |"`QueryFailedError: 
column supplier does not exist. The correct table name for orders is orders. 
I should use that in my query`"| E
F --> |"`Observation: 
The column supplier does not exist in the orders table. I should check the column names in the orders table.
Output: TABLE public.orders`" | F
D --> |"`Observation: 
The column name for supplier in the orders table is supplier name. I should use that in my query.
supplier name:xxx, total_sales:xxx`"| D


```