![SQL](https://raw.githubusercontent.com/David-Albarracin/README_MATERIALS/main/sql.png)

# Taller Practico Empleados 

Realiza las Siguientes Consultas sobre la base de Datos 

```sql
/*CREAR LAS TABLAS DE LA BASE DE DATOS*/

-- Creacion de la Tabla Departamento
CREATE TABLE departamento(
	`codigo` INT AUTO_INCREMENT,
    `nombre` VARCHAR(100),
	`presupuesto` DOUBLE,
    `gastos` DOUBLE,
    CONSTRAINT PK_departamento PRIMARY KEY (`codigo`)
);

mysql> DESCRIBE departamento;

+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| codigo      | int          | NO   | PRI | NULL    | auto_increment |
| nombre      | varchar(100) | YES  |     | NULL    |                |
| presupuesto | double       | YES  |     | NULL    |                |
| gastos      | double       | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
4 rows in set (0,00 sec)


-- Creacion de la tabla Empleado
CREATE TABLE empleado(
	`codigo` INT,
    `nit` VARCHAR(9),
    `nombre` VARCHAR(100),
    `apellido1` VARCHAR(100),
    `apellido2` VARCHAR(100),
    `codigo_departamento` INT(10),
    CONSTRAINT PK_empleado PRIMARY KEY (`codigo`),
    CONSTRAINT FK_codigo_departamento 
    FOREIGN KEY (`codigo_departamento`) 
    REFERENCES departamento(`codigo`) 
);

mysql> DESCRIBE empleado;
+---------------------+--------------+------+-----+---------+-------+
| Field               | Type         | Null | Key | Default | Extra |
+---------------------+--------------+------+-----+---------+-------+
| codigo              | int          | NO   | PRI | NULL    |       |
| nit                 | varchar(9)   | YES  |     | NULL    |       |
| nombre              | varchar(100) | YES  |     | NULL    |       |
| apellido1           | varchar(100) | YES  |     | NULL    |       |
| apellido2           | varchar(100) | YES  |     | NULL    |       |
| codigo_departamento | int          | YES  | MUL | NULL    |       |
+---------------------+--------------+------+-----+---------+-------+
6 rows in set (0,00 sec)


```

Ahora vamos a insertar unos datos de prueba 

```sql
-- Inserción de datos en la tabla departamentos

INSERT INTO departamento(`codigo`, `nombre`, `presupuesto`,`gastos`) VALUES
(1, 'Desarrollo', 120000, 6000),
(2, 'Sistemas', 150000, 21000),
(3, 'Recursos Humanos', 280000, 25000),
(4, 'Contabilidad', 110000, 3000),
(5, 'I+D', 375000, 380000),
(6, 'Proyectos', 0, 0),
(7, 'Publicidad', 0, 1000);

Query OK, 7 rows affected (0,00 sec)
Records: 7  Duplicates: 0  Warnings: 0

```

```sql
-- Inserción de datos en la tabla empleado
INSERT INTO empleado(
    `codigo`,
    `nit`,
    `nombre`, 
    `apellido1`, 
    `apellido2`, 
    `codigo_departamento`
) VALUES
    (1, '32481596F', 'Aarón', 'Rivero', 'Gómez', 1),
    (2, 'Y5575632D', 'Adela', 'Salas', 'Díaz', 2),
    (3, 'R6970642B', 'Adolfo', 'Rubio', 'Flores', 3),
    (4, '77705545E', 'Adrián', 'Suárez', NULL, 4),
    (5, '17087203C', 'Marcos', 'Loyola', 'Méndez', 5),
    (6, '38382980M', 'María', 'Santana', 'Moreno', 1),
    (7, '80576669X', 'Pilar', 'Ruiz', NULL, 2),
    (8, '71651431Z', 'Pepe', 'Ruiz', 'Santana', 3),
    (9, '56399183D', 'Juan', 'Gómez', 'López', 2),
    (10, '46384486H', 'Diego','Flores', 'Salas', 5),
    (11, '67389283A', 'Marta','Herrera', 'Gil', 1),
    (12, '41234836R', 'Irene','Salas', 'Flores', NULL),
    (13, '82635162B', 'Juan Antonio','Sáez', 'Guerrero', NULL);

Query OK, 13 rows affected (0,00 sec)
Records: 13  Duplicates: 0  Warnings: 0

```

## Consultas sobre una tabla 

1. Lista el primer apellido de todos los empleados.

   ```sql
   
   ```

2. 
