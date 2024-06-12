utente_registrato
id | BIGINT | UNIQUE | AI | PK | NOTNULL | INDEX
type_id | BIGINT | NOTNULL | FK
restaurant_id | BIGINT | NOTNULL | FK   
name | VARCHAR(50) | NOTNULL 
email | VARCHAR | NOT NULL | UNIQUE
password | VARCHAR(50) | NOTNULL | MIN:3 | MAX:50
vat number | CHAR(11) | NOTNULL
adress_of_user | VARCHAR(150) | NOTNULL

company
id | BIGINT | UNIQUE | AI | PK | NOTNULL | INDEX
type_id | BIGINT | NOTNULL | FK
restaurant_id | BIGINT | NOTNULL | FK 
order_id | BIGINT | NOTNULL | FK 
dish_id |  BIGINT | NOTNULL | FK 
restaurant_name | VARCHAR(100) | NOTNULL 
opening_time | TIME | NOTNULL
closing_time | TIME | NOTNULL
phone_number | TINYINT | NULLABLE
restaurant_image | VARCHAR(500) | NULLABLE
vote | FLOAT(1,1) | NULLABLE
adress | VARCHAR(100) | NOTNULL

dishes
id | BIGINT | UNIQUE | AI | PK | NOTNULL | INDEX
allergens_id | TINYINT | NOTNULL | FK
order_id | | BIGINT | NOTNULL | FK
dish_name | VARCHAR(50) | NOTNULL | FK
dish_image | VARCHAR(500) | NOTNULL
ingridients | TEXT | NOTNULL
price | FLOAT(3,2) | NOTNULL
availability | TINYINT | DEFAULT(0)

orders
id | BIGINT | UNIQUE | AI | PK | NOTNULL | INDEX
dish_name | VARCHAR(50) | NOTNULL | FK
order_price | FLOAT(3,2) | NOTNULL
order_status | VARCHAR(50) | NOTNULL

allergens
id | BIGINT | UNIQUE | AI | PK | NOTNULL | INDEX
allergen | VARCHAR(50) | NOTNULL

allergen_and_dish
allergens_id | TINYINT | NOTNULL | FK
dish_name | VARCHAR(50) | NOTNULL | FK

type_of_cusines
id | BIGINT | UNIQUE | AI | PK | NOTNULL | INDEX
type | VARCHAR(50) | NOTNULL | FK

type_of_cusines_and_UR
type_id | BIGINT| NOTNULL | FK
user_id | BIGINT | NOTNULL | FK
