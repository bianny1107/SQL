# SQL

## **Concepto**
<p>SQL es un lenguaje de consulta estructurado que permite acceder y manipular bases de datos.
<br>
     
- DBMS (Database Management System): Es el sistema que permite gestionar la base de datos. 
- RDBMS (Relational Database Management System): Es un sistema que permite gestionar una base de datos relacional. Se trata de la base de SQL y de los sistemas de bases de datos modernos.
     Los datos de una RDBMS se almacenan en tablas (se trata de una colección de entrada de datos relacionadas), que están formadas por columnas (que son los campos verticales) y registros o filas (que son los campos horizontales). <br>

**OJO**: SQL no distingue entre mayúsculas y minúsculas. Además, la mayoría de líneas se cierran con punto y coma. 

</p>

## Base de datos
<p>
Para hacer todos los ejemplos, estaremos utilizando una base de datos de pedidos, conformada por las siguientes tablas:
<br>

<table>
     <tr>
          <td>
               <table>
                    <thead>
                         <tr>
                              <th colspan="2" style="text-align: center;">Customers</th>
                         </tr>
                         <tr>
                              <td>Nombre del campo</td>
                              <td>Tipo de dato</td>
                         </tr>
                    </thead>
                    <tbody>
                         <tr>
                              <td>customer_id</td>
                              <td>INT</td>
                         </tr>
                         <tr>
                              <td>first_name</td>
                              <td>VARCHAR(50)</td>
                         </tr>
                         <tr>
                              <td>last_name</td>
                              <td>VARCHAR(50)</td>
                         </tr>
                         <tr>
                              <td>age</td>
                         <td>VARCHAR(3)</td>
                         </tr>
                         <tr>
                              <td>country</td>
                              <td>VARCHAR(50)</td>
                         </tr>
                    </tbody>
               </table>
          </td>
          <td>
               <table>
                    <thead>
                         <tr>
                              <th colspan="2" style="text-align: center;">Orders</th>
                         </tr>
                         <tr>
                              <td>Nombre del campo</td>
                              <td>Tipo de dato</td>
                         </tr>
                    </thead>
                    <tbody>
                         <tr>
                              <td>order_id</td>
                              <td>INT</td>
                         </tr>
                         <tr>
                              <td>item</td>
                              <td>VARCHAR(50)</td>
                         </tr>
                         <tr>
                              <td>amount</td>
                              <td>INT</td>
                         </tr>
                         <tr>
                              <td>customer_id</td>
                              <td>INT</td>
                         </tr>
                    </tbody>
               </table>
          </td>
          <td>
               <table>
                    <thead>
                         <tr>
                              <th colspan="2" style="text-align: center;">Shippings</th>
                         </tr>
                         <tr>
                              <td>Nombre del campo</td>
                              <td>Tipo de dato</td>
                         </tr>
                    </thead>
                    <tbody>
                         <tr>
                              <td>shipping_id</td>
                              <td>INT</td>
                         </tr>
                         <tr>
                              <td>status</td>
                              <td>VARCHAR(20)</td>
                         </tr>
                         <tr>
                              <td>customer</td>
                              <td>INT</td>
                         </tr>
                    </tbody>
               </table>
          </td>
     </tr>
</table>

<br>
Cada tabla contiene los siguientes datos: <br><br>

<table>
     <tr>
          <td>
               <table>
                    <thead>
                         <tr>
                              <th colspan="5" style="text-align: center;">Customers</th>
                         </tr>
                         <tr>
                              <td>customer_id</td>
                              <td>first_name</td>
                              <td>last_name</td>
                              <td>age</td>
                              <td>country</td>
                         </tr>
                    </thead>
                    <tbody>
                         <tr>
                              <td>1</td>
                              <td>Jhon</td>
                              <td>Doe</td>
                              <td>31</td>
                              <td>USA</td>
                         </tr>
                         <tr>
                              <td>2</td>
                              <td>Robert</td>
                              <td>Luna</td>
                              <td>22</td>
                              <td>USA</td>
                         </tr>
                         <tr>
                              <td>3</td>
                              <td>David</td>
                              <td>Robinson</td>
                              <td>22</td>
                              <td>UK</td>
                         </tr>
                         <tr>
                              <td>4</td>
                              <td>John</td>
                              <td>Reinhardt</td>
                              <td>25</td>
                              <td>UK</td>
                         </tr>
                         <tr>
                              <td>5</td>
                              <td>Betty</td>
                              <td>Doe</td>
                              <td>28</td>
                              <td>UAE</td>
                         </tr>
                    </tbody>
               </table>
          </td>
          <td>
               <table>
                    <thead>
                         <tr>
                              <th colspan="4" style="text-align: center;">Orders</th>
                         </tr>
                         <tr>
                              <td>order_id</td>
                              <td>item</td>
                              <td>amount</td>
                              <td>customer_id</td>
                         </tr>
                    </thead>
                    <tbody>
                         <tr>
                              <td>1</td>
                              <td>Keyboard</td>
                              <td>400</td>
                              <td>4</td>
                         </tr>
                         <tr>
                              <td>2</td>
                              <td>Mouse</td>
                              <td>300</td>
                              <td>4</td>
                         </tr>
                         <tr>
                              <td>3</td>
                              <td>Monitor</td>
                              <td>12000</td>
                              <td>3</td>
                         </tr>
                         <tr>
                              <td>4</td>
                              <td>Keyboard</td>
                              <td>400</td>
                              <td>1</td>
                         </tr>
                         <tr>
                              <td>5</td>
                              <td>Mousepad</td>
                              <td>250</td>
                              <td>2</td>
                         </tr>
                    </tbody>
               </table>
          </td>
          <td>
               <table>
                    <thead>
                         <tr>
                              <th colspan="3" style="text-align: center;">Shippings</th>
                         </tr>
                         <tr>
                              <td>shipping_id</td>
                              <td>status</td>
                              <td>customer</td>
                         </tr>
                    </thead>
                    <tbody>
                         <tr>
                              <td>1</td>
                              <td>Pending</td>
                              <td>2</td>
                         </tr>
                         <tr>
                              <td>2</td>
                              <td>Pending</td>
                              <td>4</td>
                         </tr>
                         <tr>
                              <td>3</td>
                              <td>Delivered</td>
                              <td>3</td>
                         </tr>
                         <tr>
                              <td>4</td>
                              <td>Pending</td>
                              <td>5</td>
                         </tr>
                         <tr>
                              <td>5</td>
                              <td>Delivered</td>
                              <td>1</td>
                         </tr>
                    </tbody>
               </table>
          </td>
     </tr>
</table>

</p>

## Sintaxis
<p>
Statements: Las sentencias SQl están conformadas por palabras clave (keyword).
Los comandos SQL más importantes son: <br>
     
- SELECT: Permite extraer elementos de la base de datos.
- UPDATE: Permite actualizar data en una base de datos.
- DELETE: Permite eliminar data en una base de datos.
- INSERT INTO: Permite insertar data en una base de datos.

<br>

- CREATE DATABASE: Permite crear una base de datos.
- ALTER DATABASE: Permite modificar la base de datos.

<br>
          
- CREATE TABLE: Crea una tabla.
- ALTER TABLE: Altera la tabla.
- DROP TABLE: Elimina la tabla.

<br>
          
- CREATE INDEX: Crea un índice (clave de búsqueda).
- DROP INDEX: Elimina el índice.
</p>


### SELECT
<p>
     <table>
          <tr>
               <td>Sintaxis para seleccionar uno o varios datos de una tabla</td>
               <td>SELECT nombre_dato FROM nombre_tabla</td>
               <td><img src="https://github.com/user-attachments/assets/fd807242-6bf3-4800-aa83-fbab4f2627fac" alt="select1" width="80"></td>
          </tr>
          <tr>
               <td>Sintaxis para seleccionar todos los datos de una tabla</td>
               <td>SELECT * FROM nombre_tabla</td>
               <td><img src="https://github.com/user-attachments/assets/69dd6594-f3d2-45b7-82fb-1af9d7f83e2c" alt="select2" width="80"></td>
          </tr>
     </table>
</p>

#### SELECT DISTINCT
<p>
Cuando en una tabla hay valores duplicados, SELECT DISTINCT permite mostrarlos solo una vez.
<br>

<table>
     <tr>
          <td>SELECT DISTINCT nombre_dato FROM nombre_tabla</td>
          <td><img src="https://github.com/user-attachments/assets/46018758-61ce-41b3-a091-20da53a2eeb2" alt="selectDistinct" width="80"></td>
     </tr>
</table>
</p>

##### SELECT COUNT DISTINCT
<p>
Devuelve la cantidad de valores hallados al ejecutar DISTINCT.
<br>

<table>
     <tr>
          <td>SELECT COUNT(DISTINCT(nombre_dato) FROM nombre_tabla)</td>
          <td><img src="https://github.com/user-attachments/assets/322cbf7d-675b-4688-9c95-ef4ff88adabd" alt="selectCountDistinct" width="80"></td>
     </tr>
</table>
</p>

### WHERE
<p>Se utiliza para extraer datos que cumplen con una condición especificada.</p>

<table>
     <tr>
          <td>SELECT nombre_dato FROM nombre_tabla WHERE condicion</td>
          <td><img src="https://github.com/user-attachments/assets/e7ca546a-cd46-4274-97bc-4d49214692d3" alt="where" width="80"></td>
     </tr>
</table>
