# Structured Query Language (SQL).
<details>
	<summary>Click here for initial table setup (Create Tables EMP, DEPT, SALGRADE and insert data)</summary>

<details>
	<summary>For Sql Plus</summary>

## 0. Create Tables EMP, DEPT, SALGRADE and insert data.
### 1. DEPT table
**Create Table**
```sql
CREATE TABLE DEPT(
	DEPTNO DECIMAL(2) PRIMARY KEY,
	DNAME VARCHAR(14),
	LOC VARCHAR(13)
);
```
**Insert data**
```sql
INSERT ALL 
	INTO DEPT VALUES(10,'ACCOUNTING','NEW YORK') 
	INTO DEPT VALUES(20,'RESEARCH','DALLAS') 
	INTO DEPT VALUES(30,'SALES','CHICAGO') 
	INTO DEPT VALUES(40,'OPERATIONS','BOSTON') 
SELECT * FROM dual;
```

### 2. EMP table
**Create table**
```sql
CREATE TABLE EMP(
	EMPNO DECIMAL(4) NOT NULL,
	ENAME VARCHAR(10),
	JOB VARCHAR(9),
	MGR DECIMAL(4),
	HIREDATE DATE,
	SAL DECIMAL(7,2) DEFAULT 0.00 NOT NULL,
	COMM DECIMAL(7,2),
	DEPTNO DECIMAL(2),
FOREIGN KEY(DEPTNO) REFERENCES DEPT(DEPTNO) ON DELETE CASCADE);
```
**Insert data**
```sql
INSERT ALL 
    INTO EMP VALUES (7369, 'SMITH', 'CLERK', 7902, '17-DEC-80', 800.00, NULL, 20) 
    INTO EMP VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '20-FEB-81', 1600.00, 300.00, 30) 
    INTO EMP VALUES (7521, 'WARD', 'SALESMAN', 7698, '22-FEB-81', 1250.00, 500.00, 30) 
    INTO EMP VALUES (7566, 'JONES', 'MANAGER', 7839, '02-APR-81', 2975.00, NULL, 20) 
    INTO EMP VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '28-SEP-81', 1250.00, 1400.00, 30) 
    INTO EMP VALUES (7698, 'BLAKE', 'MANAGER', 7839, '01-MAY-81', 2850.00, NULL, 30) 
    INTO EMP VALUES (7782, 'CLARK', 'MANAGER', 7839, '09-JUN-81', 2450.00, NULL, 10) 
    INTO EMP VALUES (7788, 'SCOTT', 'ANALYST', 7566, '09-DEC-82', 3000.00, NULL, 20) 
    INTO EMP VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000.00, NULL, 10) 
    INTO EMP VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500.00, 0.00, 30) 
    INTO EMP VALUES (7876, 'ADAMS', 'CLERK', 7788, '12-JAN-83', 1100.00, NULL, 20) 
    INTO EMP VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950.00, NULL, 30) 
    INTO EMP VALUES (7902, 'FORD', 'ANALYST', 7566, '03-DEC-81', 3000.00, NULL, 20) 
    INTO EMP VALUES (7934, 'MILLER', 'CLERK', 7782, '12-DEC-83', 1300.00, NULL, 10) 
SELECT * FROM dual;
```

### 3. SALGRADE table
**Create table**
```sql
CREATE TABLE SALGRADE(
	GRADE NUMBER(10),
	LOSAL NUMBER(10),
	HISAL NUMBER(10)
);
```
**Insert data**
```sql
INSERT ALL 
	INTO SALGRADE VALUES(1,700,1200) 
	INTO SALGRADE VALUES(2,1201,1400) 
	INTO SALGRADE VALUES(3,1401,2000) 
	INTO SALGRADE VALUES(4,2001,3000) 
	INTO SALGRADE VALUES(5,3001,9999) 
SELECT * FROM dual;
```
</details>
<details>
	<summary>For MySql</summary>
	
## 0. Create Tables EMP, DEPT, SALGRADE and insert data.
### 1. DEPT table
**Create Table**
```sql
CREATE TABLE DEPT(
	DEPTNO DECIMAL(2) PRIMARY KEY,
	DNAME VARCHAR(14),
	LOC VARCHAR(13)
);
```
**Insert data**
```sql
INSERT INTO DEPT (deptno, dname, loc) 
VALUES
    (10, 'ACCOUNTING', 'NEW YORK'),
    (20, 'RESEARCH', 'DALLAS'),
    (30, 'SALES', 'CHICAGO'),
    (40, 'OPERATIONS', 'BOSTON');
```

### 2. EMP table
**Create table**
```sql
CREATE TABLE EMP(
	EMPNO DECIMAL(4) NOT NULL,
	ENAME VARCHAR(10),
	JOB VARCHAR(9),
	MGR DECIMAL(4),
	HIREDATE DATE,
	SAL DECIMAL(7,2) DEFAULT 0.00 NOT NULL,
	COMM DECIMAL(7,2),
	DEPTNO DECIMAL(2),
FOREIGN KEY(DEPTNO) REFERENCES DEPT(DEPTNO) ON DELETE CASCADE);
```
**Insert data**
```sql
INSERT INTO EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno) 
VALUES
    (7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800.00, NULL, 20),
    (7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600.00, 300.00, 30),
    (7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250.00, 500.00, 30),
    (7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975.00, NULL, 20),
    (7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250.00, 1400.00, 30),
    (7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850.00, NULL, 30),
    (7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450.00, NULL, 10),
    (7788, 'SCOTT', 'ANALYST', 7566, '1982-12-09', 3000.00, NULL, 20),
    (7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000.00, NULL, 10),
    (7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500.00, 0.00, 30),
    (7876, 'ADAMS', 'CLERK', 7788, '1983-01-12', 1100.00, NULL, 20),
    (7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950.00, NULL, 30),
    (7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000.00, NULL, 20),
    (7934, 'MILLER', 'CLERK', 7782, '1983-12-12', 1300.00, NULL, 10);
```

### 3. SALGRADE table
**Create table**
```sql
CREATE TABLE SALGRADE (
    GRADE INT,
    LOSAL INT,
    HISAL INT
);
```
**Insert data**
```sql
INSERT INTO SALGRADE (GRADE, LOSAL, HISAL)
VALUES
    (1, 700, 1200),
    (2, 1201, 1400),
    (3, 1401, 2000),
    (4, 2001, 3000),
    (5, 3001, 9999);
```
</details>
</details>

## 1. DBMS & R-DBMS
### I. DBMS
- Stands for <code>Data Base Management System</code>.
- It is a software which uses query language, by using query language, database users develop a query, the developed query is used to interact with the database to retrieve the required data as an output.
- Features of DBMS
  - C - Create/Add
  - R - Read/Retrieve
  - U - Update/Modify
  - D - Delete/Drop
  - Providing Authentication for Database users.
  - Providing Securities for Database.
- In DBMS data is stored in a file format & files may have different extentions due to that <code>relationship can't be established</code>.
  
### II. RDBMS
- Stands for <code>Relational Data Base Management System</code>.
- Any DBMS which follows Relational model of Database becomes R-DBMS.
- It is a software which uses SQL as a language, by using SQL, database users develop a query, the developed query is used to interact with the database to retrieve the required data as an output.
- Features of DBMS
  - C, R, U, D.
  - Authentication.
  - Securities.
- In DBMS data is stored in a table format. The table will be having a common column, we apply key fields (Primary & Foreign keys) to the common columns and establish relationship between the data.

### III. Difference between DBMS & R-DBMS
<table>
  <tr>
    <th>DBMS</th>
    <th>R-DBMS</th>
  </tr>
  <tr>
    <td>• The Data is stored in file format.</td>
    <td>• The Data is stored in Table format.</td>
  </tr>
  <tr>
    <td>• Relationship between the Data can't be established.</td>
    <td>• Relationship between the Data can be established.</td>
  </tr>
  <tr>
    <td>• It uses Query Language.</td>
    <td>• It Uses SQL.</td>
  </tr>
  <tr>
    <td>• Normalisation can't be applied.</td>
    <td>• Normalisation can be applied.</td>
  </tr>
</table>

**Note:**
- Table / Object / Entity
- Columns / Fields / Attributes
- Rows / Records / Tuples

<img src="https://github.com/user-attachments/assets/108ed383-b982-45f6-9f2f-d2dec44adf5d" width="250">

- **Table:** It is a combination of Rows & Column.
- **Cell:** It is a intersection point of rows & columns.

## 2. R-DBMS softwares available in the market.
- Oracle DB.
- MySql.
- Microsoft SQL server.
- Postgre SQL.
- IBM DB-2.
- Maria DB.

## 3. Datatypes in SQL.
- The type of data stored in a perticuler column of a table is called datatype.
- We can assign only one datatype to a single column.
- Datatypes are mandatory for all the columns of a table.
- In SQL we have 4 datatypes.
  - Char
  - VarChar
  - Number
  - Date

### I. Char.
- If a column is assigned with <code>Char</code> datatype, it can store the following values.
  - Alphabets(A to Z, a to z).
  - Numbers (0 to 9).
  - Special characters (!, @, #, $, %)
- The default size for char data type is <code>one(1)</code>

**Example-1**
<table>
  <caption>char(3)</caption>
  <tr>
    <td><3</td><td>✔</td>
  </tr>
  <tr>
    <td>=3</td><td>✔</td>
  </tr>
  <tr>
    <td>>3</td><td>❌</td>
  </tr>
</table>

**Example-2**
<table>
  <caption>char(3)</caption>
  <tr>
    <th>c1</th><th>Correct/Incorrect</th>
  </tr>
  <tr>
    <th>ABD</th><th>✔</th>
  </tr>
  <tr>
    <th>123</th><th>✔</th>
  </tr>
  <tr>
    <th>A2</th><th>✔</th>
  </tr>
  <tr>
    <th>$</th><th>✔</th>
  </tr>
  <tr>
    <th>1234</th><th>❌</th>
  </tr>
  <tr>
    <th>$1A</th><th>✔</th>
  </tr>
  <tr>
    <th>0A10</th><th>❌</th>
  </tr>
</table>

**Example-3**
<table>
  <caption>char</caption>
  <tr>
    <th>c1</th><th>Correct/Incorrect</th>
  </tr>
  <tr>
    <th>0</th><th>✔</th>
  </tr>
  <tr>
    <th>A1</th><th>❌</th>
  </tr>
  <tr>
    <th>$</th><th>✔</th>
  </tr>
  <tr>
    <th>ABC</th><th>❌</th>
  </tr>
  <tr>
    <th>C</th><th>✔</th>
  </tr>
</table>

### II. VarChar.
- If a column is assigned with <code>VarChar</code> datatype, it can store the following values.
  - Alphabets(A to Z, a to z).
  - Numbers (0 to 9).
  - Special characters (!, @, #, $, %)
- There is no default size for VarChar data type <code>(size is compulsory)</code>.
      
#### Difference between Char & R-VarChar.
<table>
  <tr>
    <th>Char</th>
    <th>VarChar</th>
  </tr>
  <tr>
    <td align='center'>
      <table>
        <tr>
          <th colspan='5'>c1</th>
        </tr>
        <tr><td>A</td><td>B</td><td>_</td><td>_</td><td>_</td></tr>
      </table>
    </td>
    <td align='center'>
      <table>
        <tr>
          <th colspan='6'>c1</th>
        </tr>
        <tr><td>A</td><td>B</td><td> </td><td> </td><td> </td></tr>
      </table>
    </td>
  </tr>
  <tr>
    <td>• The Unallocated memory blocks are filled with space, Which consumes memory.</td>
    <td>• The Unallocated memory blocks are filled with null, Which doesnot consumes memory.</td>
  </tr>
  <tr>
    <td>• It follows fixed allocation of memory.</td>
    <td>• It follows variable allocation of memory.</td>
  </tr>
  <tr>
    <td>• The default size is one (1).</td>
    <td>• There is no default size.</td>
  </tr>
  <tr>
    <td>• We can store upto 2000 characters.</td>
    <td>• We can store upto 4000 characters.</td>
  </tr>
</table>

### III. Number.
- If a column is assigned with <code>Number</code> datatype, it can store only <code>digits (0 to 9)</code>.
- The default size for char data type is <code>one(1)</code>

**Example-1**
<table>
  <caption>number(2)</caption>
  <tr>
    <td><2</td><td>✔</td>
  </tr>
  <tr>
    <td>=2</td><td>✔</td>
  </tr>
  <tr>
    <td>>2</td><td>❌</td>
  </tr>
</table>

**Example-2**
<table>
  <caption>number(2)</caption>
  <tr>
    <th>c1</th><th>Correct/Incorrect</th>
  </tr>
  <tr>
    <th>49</th><th>✔</th>
  </tr>
  <tr>
    <th>263</th><th>❌</th>
  </tr>
  <tr>
    <th>AB</th><th>❌</th>
  </tr>
  <tr>
    <th>$0</th><th>❌</th>
  </tr>
  <tr>
    <th>A1</th><th>❌</th>
  </tr>
  <tr>
    <th>-49</th><th>✔</th>
  </tr>
  <tr>
    <th>0</th><th>✔</th>
  </tr>
</table>

#### Precision & Scale.
Number datatype can also be user with 2 arguments.
  - **Example:** Number(precision & scale)
  - **Precision:** It represents the total no of digits including the decimal.
  - **Scale:** It represents the max no of decimal values.
  - **Precision - Scale (p-s):** It represents the max no of Integers.                 
    **Example**
  <table>
    <caption>number(4, 2)</caption>
    <tr>
      <th>c1</th><th>Correct/Incorrect</th>
    </tr>
    <tr>
      <th>99.99</th><th>✔</th>
    </tr>
    <tr>
      <th>9.99</th><th>✔</th>
    </tr>
    <tr>
      <th>9.9</th><th>✔</th>
    </tr>
    <tr>
      <th>99.9</th><th>✔</th>
    </tr>
    <tr>
      <th>999.9</th><th>❌</th>
    </tr>
    <tr>
      <th>9.999</th><th>❌</th>
    </tr>
    <tr>
      <th>99</th><th>✔</th>
    </tr>
    <tr>
      <th>9</th><th>✔</th>
    </tr>
    <tr>
      <th>999</th><th>❌</th>
    </tr>
    <tr>
      <th>0.99</th><th>✔</th>
    </tr>
    <tr>
      <th>0.9</th><th>✔</th>
    </tr>
    <tr>
      <th>0</th><th>✔</th>
    </tr>
    <tr>
      <th>9999</th><th>❌</th>
    </tr>
    <tr>
      <th>-99</th><th>✔</th>
    </tr>
  </table>

### IV. Date.
- If a column is assigned with date datatype, it can store only the date values. The default date formate in Oracle is DD-MMM-YY

**Example-1**
<table>
  <caption>date</caption>
  <tr>
    <td>20-OCT-21</td><td>✔</td>
  </tr>
  <tr>
    <td>OCT-20-21</td><td>❌</td>
  </tr>
  <tr>
    <td>>20/10/21</td><td>❌</td>
  </tr>
</table>

## 4. Constraints in SQL.
- Constraints are the rules of validations applied a columns of a taable.
- Constraints are optional but highly recommended or highly preferable.
- We can apply multiple constraints for a single column.
- **The Constraints used are**
  1. Not null
  2. Unique
  3. Check
  4. Primary key
  5. Foreign key

### I. Not null.
- Null
  - It is neither zero nor space.
  - It won't consume any memory.
  - Any Arithmetic operation performed with a null will result in a null.
  - In Oracle, nulls are not same because they are compared by their addresses.
- If a column is assigned with not null constraint, it cannot store null values, means the caolumn cannot have empty cell but the same column can store duplicate values.           
  **Example**
  <table>
    <caption>number(3), not null</caption>
    <tr>
      <th>c1</th><th>Correct/Incorrect</th>
    </tr>
    <tr>
      <th>263</th><th>✔</th>
    </tr>
    <tr>
      <th>56.3</th><th>✔</th>
    </tr>
    <tr>
      <th>null</th><th>❌</th>
    </tr>
    <tr>
      <th>49</th><th>✔</th>
    </tr>
    <tr>
      <th>AB</th><th>❌</th>
    </tr>
    <tr>
      <th>-49</th><th>✔</th>
    </tr>
  </table>

  ### II. Unique.
  - If a column is assigned with unique constraints, it cannot store duplicate values.
  - But the same column can store null values.               
    **Example-1**
    <table>
      <caption>number(3), unique</caption>
      <tr>
        <th>c1</th><th>Correct/Incorrect</th>
      </tr>
      <tr>
        <th>143</th><th>✔</th>
      </tr>
      <tr>
        <th>143</th><th>❌</th>
      </tr>
      <tr>
        <th>null</th><th>✔</th>
      </tr>
      <tr>
        <th>null</th><th>✔</th>
      </tr>
      <tr>
        <th>AB</th><th>❌</th>
      </tr>
      <tr>
        <th>12</th><th>✔</th>
      </tr>
    </table>

    **Example-2**
    <table>
      <caption>number(3), not null, unique</caption>
      <tr>
        <th>c1</th><th>Correct/Incorrect</th>
      </tr>
      <tr>
        <th>null</th><th>❌</th>
      </tr>
      <tr>
        <th>133</th><th>✔</th>
      </tr>
      <tr>
        <th>133</th><th>❌</th>
      </tr>
      <tr>
        <th>420</th><th>✔</th>
      </tr>
      <tr>
        <th>AB</th><th>❌</th>
      </tr>
    </table>

  ### III. Check.
  - It is used to limit the value for a particular column of a table.
  - Check constraint is also called as domain constraint.
  - Domain is a  set of valid values.             
    **Example-1**
    <table>
      <caption>number(2), not null, (age>=18)</caption>
      <tr>
        <th>age</th><th>Correct/Incorrect</th>
      </tr>
      <tr>
        <th>22</th><th>✔</th>
      </tr>
      <tr>
        <th>99</th><th>✔</th>
      </tr>
      <tr>
        <th>17</th><th>❌</th>
      </tr>
      <tr>
        <th>18</th><th>✔</th>
      </tr>
      <tr>
        <th>18</th><th>✔</th>
      </tr>
      <tr>
        <th>100</th><th>❌</th>
      </tr>
      <tr>
        <th>9</th><th>❌</th>
      </tr>
      <tr>
        <th>null</th><th>❌</th>
      </tr>
    </table>

## 5. SQL Query Sub Languages.
1. DQL -> Data Query Language.
2. DDL -> Data Definition Language.
3. DML -> Data Manipulation Language.
4. TCL -> Transaction Control Language.
5. DCL -> Data Control Language.

### Statements of Sub language.
Each & Every Sub language is having certain statements.
1. DQL -> Select
2. DDL -> Create, Alter, Rename, Truncate & Drop
3. DML -> Insert, Update & Delete
4. TCL -> Rollback, Commit & Save point
5. DCL -> Grant & Revoke

## 6. DQL -> Data Query Language.
- It is used to fetch or retrieve the data from the database.
- Select Statement is used to fetch or retrieve the data from the perticular table in the database.
- Select statement has 3 possibilities.
  - Projections
  - Selections
  - Joins

### I. Projections.
- Fetching or Retrieving the data from perticuler table by selecting all the columns or only required columns is called as projections.
- By default all the rows will be selected in projections.
- We can restrict the column but not the rows.            
  **Syntax:**             
  ② &nbsp;&nbsp; **SELECT** * / [distinct] \<col_name\> / \<expression\> [\<alias\>]                   
  ① &nbsp;&nbsp; **FROM** \<table_name\>;                                          

#### Queries on Projections.

1. WAQTD the names of all the employees.
	```sql
	SELECT ename
	FROM emp;
	```
2. WAQTD the designation, employee id & salary for all the  employee.
	```sql
	SELECT job, empno, sal
	FROM emp;
	```
3. WAQTD the manager number, date of joining, & commission for all the employee.
	```sql
	SELECT mgr, hiredate, comm
	from emp;
	```
4. WAQTD the employee number & department number for all employees.
	```sql
	SELECT empno, deptno
	from emp;
	```
5. WAQTD the details for all the employees.
	```sql
	SELECT *
	from emp;
	```
6. WAQTD the employee details along with salary for all the employees.
	```sql
	SELECT emp.*, sal
	from emp;
	```

```text
Note:
  • SQL is a case insensitive language.
  • To display list of tables in the Database, we use "Select * from tab;"
  • SET: Set command is used to set the lines size & page size.
	Example: set lines 100 pages 100;
  • Describe: Discribe command is used to discribe the table structure.
	Example: describe <table_name>;
   • Switch: It is used to switch between the database users.
```

**Distinct Clause**
- It is used to remove the duplicates from the output.
- It should be used before the column name.
- It removes the duplicates only in the output but not in the table.
- Distinct clause is not manditory.
- If a single column is used with distinct clause, unique values will be provided only for that column.
- If multiple columns are used with distinct clause, unique combination of values are provided.

7. WAQTD the unique department number values from employee table.
	```sql
	SELECT DISTINCT deptno
	from emp;
	```
8. WAQTD the salary values without duplicates.
	```sql
	SELECT DISTINCT sal
	from emp;
	```
9. WAQTD the unique combination of job & department number.
	```sql
	SELECT DISTINCT job, deptno
	from emp;
	```
10. WAQTD the combination of salary & manager number without repetition.
	```sql
	SELECT DISTINCT sal, mgr
	from emp;
	```

**Expression**
- It is a combination of Operator & Operands.
	Example: **a + b**
	Where "a" & "b" are the Operands and "+" is a Operator.
- Operands: They are the inputs used in an expressions.
- There are 2 types of Operands are there.
	- **Column type operands:** If a column name is used as an input in the expression, it is called column type operand.
 		Example: **sal + 100**
   		Where "sal" is a column type operand.
	- **Literal type operands:** If a direct value is used as an input in the expression it is called as an literal type operand.
 		- Literal type operand is further classified into 3 types.
			1. Number literal.
 				Example: **sal + 100**
				Where "100" is a number literal.
			2. Character literal.
 				Example: **'Hi ' + ename**
				Where "Hi" is a character literal.
			3. Date literal.
 				Example: **hiredate + '27-oct-21'**
				Where "27-oct-21" is a date literal.

11. WAQTD the annual salary for all the employees.
	```sql
	SELECT sal * 12
	from emp;
	```
12. WAQTD the half term & annual commission for all the employee.
	```sql
	SELECT comm * 6, comm * 12
	from emp;
	```
13. WAQTD the sal with a bonus of 500 & with a penalty of 200.
	```sql
	SELECT sal + 500, sal - 200
	from emp;
	```
14. WAQTD the 25% of hike of sal for all the employees.
	```sql
	SELECT sal + sal * (25/100)
	from emp;
	```
 	```sql
	SELECT sal * 1.25
	from emp;
	```
15. WAQTD the 75% deduction & 50% hike of sal for all the employees.
 	```sql
	SELECT sal - sal * 0.25, sal + sal * 0.5
	from emp;
	```
 	```sql
	SELECT sal * 0.75, sal * 1.5
	from emp;
	```
16. WAQTD the 25% hike on annual salary.
 	```sql
	SELECT sal * 12 * 1.25
	from emp;
	```

**Alias**
- It is an alternative name given for an expression, column names & functions.
- It is not mandatory but used to get user convenient output.
- If Alias contains special character in it then it should be used within the double quotes.
- We can not use keyword of sql as an Alias.               
	**Syntax:**
	```sql
	SELECT <expression/function/column_name> <alias>
	```
	 ```sql
	SELECT <expression/function/column_name> as <alias>
	```

17. WAQTD the annual salary for all the employees with alias.
	```sql
	SELECT sal * 12 as Annual_Salary
	from emp;
	```
18. WAQTD the half term & annual commission for all the employee with alias.
	```sql
	SELECT comm * 6 as Half_Term_Salary, comm * 12 as Annual_Salary
	from emp;
	```
19. WAQTD the sal with a bonus of 500 & with a penalty of 200 with alias.
	```sql
	SELECT sal + 500 as Salary_With_Bonus, sal - 200 as Salary_With_Penalty
	from emp;
	```
20. WAQTD the 25% of hike of sal for all the employees with alias.mp;
 	```sql
	SELECT sal * 1.25 as "Salary_With_25%_Hike"
	from emp;
	```
21. WAQTD the 75% deduction & 50% hike of sal for all the employees with alias.
 	```sql
	SELECT sal * 0.75 as "Salary_With_75%_Deduction", sal * 1.5 as "Salary_With_50%_Hike"
	from emp;
	```
22. WAQTD the 25% hike on annual salary with alias.
 	```sql
	SELECT sal * 12 * 1.25 as "25%_Hike_On_Annual_Salary"
	from emp;
	```

### II. Selections.
- Fetching or Retrieving the data from perticuler table by selecting all the columns or only required columns along with required rows is called as projections.
- Here both columns & Rows can be restricted.                  
  **Syntax:**             
  ③ &nbsp;&nbsp; **SELECT** * / [distinct] \<col_name\> / \<expression\> [\<alias\>]                
  ① &nbsp;&nbsp; **FROM** \<table_name\>                  
  ② &nbsp;&nbsp; [**WHERE** \<row_filter_condition\>];      

**Where Clause**
- It is used to filter the records of a table.
- It works based on the condition specified.
- It works in the format of **Row_By_Row**, ie., The condition will be checked for each & every row.
- If the condition is true, where clause will select that record.
- If the condition is false, where clause will reject that record.           
  Example where clause condition: LHS > RHS              
  Where ">" is a Operator.

**Types of Operators**
|Types|Operators|
|-----|---------|
|Arithmetic Operators|"+", "-", "/", "*"|
|Logical Operators|AND, OR, NOT|
|Relational/Comparison Operators|"=", "!=", ">", "<", ">=", "<="|
|Set Operators|UNION, INTERSECT, MINUS, UNION ALL|
|Concatination Operator|"\|\|"|
|Subquery Operators|ANY, ALL|
|Special Operators|IS, IS NOT, IN, NOT IN, LIKE, NOT LIKE, BETWEEN, NOT BETWEEN|

#### Queries on Selections.
1. WAQTD the department number for smith.
	```sql
	SELECT deptno
	FROM emp
 	WHERE ename = 'SMITH';
	```
2. WAQTD the employee Allen's salary.
	```sql
	SELECT sal
	FROM emp
 	WHERE ename = 'ALLEN';
	```
3. WAQTD the employee names & date of joining to work in department number 30.
	```sql
	SELECT ename, hiredate
	FROM emp
 	WHERE deptno = 30;
	```
4. WAQTD the employee details for salesman.
	```sql
	SELECT *
	FROM emp
 	WHERE job = 'SALESMAN';
	```
5. WAQTD the salary & commission for the employee reporting to 7698.
	```sql
	SELECT sal, comm
	FROM emp
 	WHERE mgr = 7698;
	```
6. WAQTD the employee number for the employees who joined on 2nd april 1981.
	```sql
	SELECT empno
	FROM emp
 	WHERE hiredate = '02-apr-81';
	```
7. WAQTD the emp names earning atleast 2000 as there salary.
	```sql
	SELECT ename
	FROM emp
 	WHERE sal >= 2000;
	```
8. WAQTD the designation & manager number for the employee id 7654.
	```sql
	SELECT job, mgr
	FROM emp
 	WHERE empno = 7654;
	```
9. WAQTD the department number for the employee who joined after the year 1981.
	```sql
	SELECT deptno
	FROM emp
 	WHERE hiredate > '31-dec-81';
	```
	```sql
	SELECT deptno
	FROM emp
 	WHERE hiredate >= '01-jan-81';
	```
10. WAQTD the employee details for all the employees expect smith.
	```sql
	SELECT *
	FROM emp
 	WHERE ename != 'SMITH';
	```

**Order By Clause**
- Order by clause is used to arrange or sort the output in ascending or descending order.
- Order by clause affects only the output but not the table data.
- Order by clause always executes at the last.
- Order by clause should be the last statement in a query.
- By default it sorts in ascending order.
	**Syntax:**             
	③ &nbsp;&nbsp; **SELECT** * / [distinct] \<col_name\> / \<expression\> [\<alias\>]                
	① &nbsp;&nbsp; **FROM** \<table_name\>                  
	② &nbsp;&nbsp; [**WHERE** \<row_filter_condition\>];
	④ &nbsp;&nbsp; **ORDER BY** \<reference_column\> [ASC]/DESC;

11. WAQTD the salary values in ascending order.
	```sql
	SELECT sal
	FROM emp
 	ORDER BY sal ASC;
	```
	```sql
	SELECT sal
	FROM emp
 	ORDER BY sal;
	```
12. WAQTD the commission values in descending order.
	```sql
	SELECT comm
	FROM emp
 	ORDER BY comm DESC;
	```
13. WAQTD the employee names & salary only for Clerk & sort the output WRT salary in descending order.
	```sql
	SELECT ename, sal
	FROM emp
 	WHERE job = 'CLERK'
 	ORDER BY sal DESC;
	```
14. WAQTD the employee names in alphabetical order.
	```sql
	SELECT ename
	FROM emp
 	OEDER BY ename;
	```
15. WAQTD the annual salary in ascending order for all the employees only if annual salary is greater then 15,000.
	```sql
	SELECT sal * 12
	FROM emp
 	WHERE sal * 12 > 15000
 	ORDER BY sal * 12;
	```
	```sql
	SELECT sal * 12 as anusal
	FROM emp
 	WHERE sal * 12 > 15000
 	ORDER BY anusal;
	```
**Logical Operator**
- It is used to specify multiple condition in **WHERE** clause.
- If we are using (n) number of conditions we have to write (n-1) number of logical operators.
- We should use AND condition when all the conditions has to be satisfied.
- We use OR condition when any one of the conditions has to be satisfied.

16. WAQTD the employee details working as a salesman in the department number 30.
	```sql
	SELECT *
	FROM emp
 	WHERE job = 'SALESMAN' AND deptno = 30;
	```
17. WAQTD the employee details reporting to 7902 or 7698.
	```sql
	SELECT *
	FROM emp
 	WHERE mrg = 7902 OR mgr = 7698;
	```
18. WAQTD the employee names working in the department number 20 or 30.
	```sql
	SELECT ename
	FROM emp
 	WHERE deptno = 20 OR deptno = 30;
	```
19. WAQTD the employee details for Smith & Allen. ⭐⭐⭐
	```sql
	SELECT *
	FROM emp
 	WHERE ename = 'SMITH' OR ename = 'ALLEN';
	```
20. WAQTD the employee details working as a manager but earning salary more then 2000.
	```sql
	SELECT *
	FROM emp
 	WHERE job = 'MANAGER' AND sal > 2000;
	```
21. WAQTD the employee details working in the department number 20 but reporting to 3839.
	```sql
	SELECT *
	FROM emp
 	WHERE deptno = 20 AND mgr = 3839;
	```
22. WAQTD the employee names working as a Clerk or Salesman.
	```sql
	SELECT ename
	FROM emp
 	WHERE job = 'CLERK' OR job = 'SALESMAN';
	```
23. WAQTD the employee details earning atmost 3000 as a Clerk.
	```sql
	SELECT *
	FROM emp
 	WHERE sal <= 3000 AND job = 'CLERK';
	```
24. WAQTD the employee details working as a Clerk or Manager in the department number 20.
	```sql
	SELECT *
	FROM emp
 	WHERE (job = 'CLERK' OR job = 'MANAGER') AND deptno = 20;
	```

```text
Note:
	If column names are same in multiple conditions then we should always use OR operator.
```

**IN Operator**
- It is a special operator to optimize the query length.
- It avoids the multiple usage of OR operators.
- It is a multivalued operator, ie., it can handle single LHS & multiple RHS.
  **Syntax:**
  1. LHS in RHS
  2. LHS in (RHS_1, RHS_2, RHS_3)

**NOT Operator**
- Not Operator **can be used with any Special Operators**.
- It is used to revert the condition.
  **Syntax:**
  1. LHS not in RHS
  2. LHS not in (RHS_1, RHS_2, RHS_3)

25. WAQTD the employee details for allen, ward & jones.
	```sql
	SELECT *
	FROM emp
 	WHERE ename IN ('ALLEN', 'WARD', 'JONES');
	```
26. WAQTD the employee details who joined on February 20th 1981 & April 19th 1987.
	```sql
	SELECT *
	FROM emp
 	WHERE hiredate IN ('20-feb-81', '19-apr-87');
	```
27. WAQTD the employee names who are earning commission 300, 500 or 0.
	```sql
	SELECT ename
	FROM emp
 	WHERE comm IN (300, 500, 0);
	```
28. WAQTD the employee details who are not working as Clerk & Salesman.
	```sql
	SELECT *
	FROM emp
 	WHERE job NOT IN ('CLERK', 'SALESMAN');
	```
29. WAQTD the employee details who are not working at department number 20 & 30.
	```sql
	SELECT *
	FROM emp
 	WHERE deptno NOT IN (20, 30);
	```
30. WAQTD the employee details reporting to 7698 & 7839.
	```sql
	SELECT *
	FROM emp
 	WHERE mgr IN (7698, 7839);
	```

**BETWEEN Operator**
- It is used to select the data from given range.
- It is also called as range operator.
- It is also called as inclusive operator.
- It should be used when the condition is in the format of range.
	**Syntax:**
  	1. LHS BETWEEN LLV and ULV;
  	2. LHS NOT BETWEEN LLV and ULV;
  	**Note:**
	LLV - Lower Limit Value.
	ULV - Upper Limit Value.
	LLV Should be always lesser then ULV.

31. WAQTD the employee details earning salary between 2000 to 5000.
	```sql
	SELECT *
	FROM emp
 	WHERE sal BETWEEN 2000 AND 5000;
	```
32. WAQTD the employee details who got hired in the year 1981.
	```sql
	SELECT *
	FROM emp
 	WHERE hiredate BETWEEN '01-jan-81' AND '31-dec-81';
	```
33. WAQTD the employee details earning commission with in the range 500 & 1500.
	```sql
	SELECT *
	FROM emp
 	WHERE comm BETWEEN 500 AND 1500;
	```
34. WAQTD the employee details who's employee number is not between 7500 to 7900.
	```sql
	SELECT *
	FROM emp
 	WHERE empno NOT BETWEEN 7500 AND 7900;
	```
35. WAQTD the employee details who did not joined the company in the year 1980.
	```sql
	SELECT *
	FROM emp
 	WHERE hiredate NOT BETWEEN '01-jan-80' AND '31-dec-80';
	```

**IS Operators**
- It is used to compare with the **NULL** value.
- There is no other operator in SQL to compare with a NULL value, expect **IS** Operator.
	**Syntax**
  	1. LHS IS NULL
  	2. LHS IS NOT NULL

36. WAQTD the employee details who are not earning any comm.
	```sql
	SELECT *
	FROM emp
 	WHERE comm IS NULL;
	```
37. WAQTD the employee details who are not reporting to any manager.
	```sql
	SELECT *
	FROM emp
 	WHERE mgr IS NULL;
	```
38. WAQTD the employee details reporting to a manger but not earning commission.
	```sql
	SELECT *
	FROM emp
 	WHERE mgr IS NOT NULL AND comm IS NULL;
	```
39. WAQTD the employee details earning some commission but not having a manager.
	```sql
	SELECT *
	FROM emp
 	WHERE comm IS NOT NULL AND mgr IS NULL;
	```

**LIKE Operator**
- It is used to perform pattern matching & wild card search.
  **Syntax:**
  	1. LHS LIKE 'pattern'
  	2. LHS NOT LIKE 'pattern'
- The RHS of a like operator is a pattern.
- Pattern should be written within single quotes.
- Like operator can take only one pattern at a time.
- Pattern is a combination of ordinary characters & meta characters.

**Meta Characters ('%', '_')**
'%' -> It represents n-number of characters (n >= 0)
'_' -> It represents a single character.

```text
Note:
	Percentage & Underscore have this special functionality only WRT 'LIKE' operator.
```

40. WAQTD the 
	```sql
	SELECT 
	FROM emp
 	WHERE ;
	```

### III. Joins.

#### Queries on Joins.
---------------------------------------------------------------------------------------------------------------------------------------

## 7. SQL Query execution order.

③ &nbsp;&nbsp; **SELECT** * / [distinct] \<col_name\> / \<expression\> [\<alias\>]                
① &nbsp;&nbsp; **FROM** \<table_name\>                  
② &nbsp;&nbsp; [**WHERE** \<row_filter_condition\>]                
④ &nbsp;&nbsp; [**ORDER BY** \<ref_col\> [ASC] / DESC];          


⑤ &nbsp;&nbsp; **SELECT** \<group_by_expression\>            
① &nbsp;&nbsp; **FROM** \<table_name\>            
② &nbsp;&nbsp; [**WHERE** \<row_filter_condition\>]              
③ &nbsp;&nbsp; **GROUP BY** \<ref_col\>             
④ &nbsp;&nbsp; [**HAVING** \<group_filter_condition\>]               
⑥ &nbsp;&nbsp; [**ORDER BY** \<ref_col\> [ASC] / DESC];              

## 5. Sub-Query.

### Case-1 (To find the unknown value).
#### WAQTD the employee details who are working for the job same as Allen.
```sql
SELECT *
FROM emp
WHERE job = (SELECT job
             FROM emp
             WHERE ename='ALLEN');
```

### Case-2 (To Map 2 or more tables by using common columns).
#### WAQTD the employee names working in accounting dept.
```sql
SELECT ename
FROM emp
WHERE deptno = (SELECT deptno
                FROM dept
                WHERE dname='ACCOUNTING');
```

### Case-3 (To find nth-max or nth-min value).
#### WAQTD the 3rd-min salary.
```sql
SELECT min(sal)
FROM emp
WHERE sal > (SELECT min(sal)
             FROM emp
             WHERE sal > (SELECT min(sal)
                          FROM emp));
```

#### WAQTD the 4th-max salary.
```sql
SELECT max(sal)
FROM emp
WHERE sal < (SELECT max(sal)
             FROM emp
             WHERE sal < (SELECT max(sal)
                          FROM emp
                          WHERE sal < (SELECT max(sal)
                                       FROM emp)));
```

### Case-4 (To Map the table to it-self by using a different columns of the table).
#### WAQTD the subordinate name reporting to Smith.
```sql
SELECT ename
FROM emp
WHERE mar = (SELECT empno
             FROM emp
             WHERE ename='SMITH');
```

## 6. Joins.

### Types of joins
1. Cartesian Join / Cross Join.
2. Inner Join / Equi Join.
3. Non Equi Join.
4. Outer Join.
   - Left outer join.
   - Right outer join.
   - Full Outer join.
5. Self Join.

#### 1. Cartesian Join / Cross Join.
It Gives both valid and invalid records.
```sql
SELECT *
FROM emp A, dept B;
```

#### 2. Inner Join / Equi Join (Joining multiple tables with a common column or Joining multiple tables using equals(=) operator).
It Gives only valid records.
```sql
SELECT *
FROM emp A, dept B
WHERE A.deptno = B.deptno;
```

#### 3. Non Equi Join (Joining multiple tables without a common column or Joining multiple tables without using equals(=) operator).
It Gives only valid records.
```sql
SELECT ename, sal, grade
FROM emp, salgrade
WHERE sal BETWEEN losal and hisal; 
```

#### 4. Outer Join.

##### i. Left outer join.
It Gives valid records (Left & Right table) + invalud records (Left table).
```sql
SELECT * / col(s)
FROM table_1 A, table_2 B
WHERE A.cc = B.cc (+)
```

##### ii. Right outer join.
It Gives valid records (Left & Right table) + invalud records (Right table).
```sql
SELECT * / col(s)
FROM table_1 A, table_2 B
WHERE A.cc (+) = B.cc
```

##### iii. Full outer join.
It Gives valid records (Left & Right table) + invalud records (Left & Right table).
```sql
SELECT * / col(s)
FROM table_1 A, table_2 B
WHERE A.cc = B.cc (+)

UNION

SELECT * / col(s)
FROM table_1 A, table_2 B
WHERE A.cc (+) = B.cc
```

#### 5. Self Join (Joining a table to it self is called Slef join).

##### WAQTD subordinates names & Manager names for all the employees.
```sql
SELECT A.ename as sub, B.ename as mgr
FROM emp A, emp B
WHERE A.mgr = B.empno;
```

##### WAQTD subordinates names & Manager names for all the employees only if the subordinates are earning salary more then there managers.
```sql
SELECT A.ename as sub, B.ename as mgr
FROM emp A, emp B
WHERE A.mgr = B.empno and A.sal > B.sal;
```

## 7. Co-related sub-query.
### WAQTD the 4th maximum salary.
```sql
SELECT distinct sal
FROM emp A
WHERE 3 = (SELECT count(distinct  sal)
           FROM emp B
           WHERE A.sal < B.sal);
```

### WAQTD the 8th minimum salary.
```sql
SELECT distinct sal
FROM emp A
WHERE 7 = (SELECT count(distinct  sal)
           FROM emp B
           WHERE A.sal > B.sal);
```


## DDL - Data Definition Language.
### 1. Write a query to create a table.
```sql
CREATE TABLE Sachi(
  ID int NOT NULL UNIQUE,
  Name char(20) NOT NULL,
  Age int,
  Place char(20)
);
```

### 2. Write a query to rename the table.
```sql
RENAME sachi to Data;
```

### 3. Write a query to alter the table.

#### i. Rename a column.
```sql
ALTER TABLE data
RENAME COLUMN id to UserId;
```

#### ii. Add a column.
```sql
ALTER TABLE data
ADD Pincode int not null;
```

#### iii. delete a column.
```sql
ALTER TABLE data
DROP COLUMN Pincode;
```

#### iv. modify a column.
```sql
ALTER TABLE data
MODIFY Pincode varchar(20);
```

### 4. Write a query to truncate the table.
Truncate is used to remove all the records of a table.
```sql
TRUNCATE TABLE data;
```

### 5. Write a query to drop the table.
Drop is used to delete the table.

#### i. To delete a table and keep in bin.
```sql
DROP TABLE data;
```

#### ii. To restore table from bin.
```sql
FLASHBACK TABLE data TO BEFORE DROP;
```

#### iii. To delete a table permanently.

- Before Drop
```sql
DROP TABLE data PURGE;
```

- After Drop
```sql
PURGE TABLE data;
```

## DML - Data Manipulation Language.
### 1. Write a query to insert records into a table.
```sql
INSERT into sachi(id, name, age, place) values(4, 'Sachin_Kn', 27, 'Bengaluru');
```
```sql
insert into data values(1, 'Nagaraj Km', 55, 'Kerehosalli');
insert into data values(2, 'Sudha', 50, 'Kerehosalli');
insert into data values(3, 'Chethan', 25, 'Kerehosalli');
INSERT into data values(4, 'Sachin_Kn', 27, 'Bengaluru');
insert into data values(5, 'Vidya_Cm', 26, 'Bengaluru');
```

### 2. Write a query to update record of a table.
```sql
UPDATE data
SET name = 'Sudha Ys', age = 49
WHERE userid = 2;
```

### 3. Write a query to delete record of a table.
```sql
DELETE FROM data
WHERE userid = 10;
```

## Pseudo Columns & Rows.

### 1. WAQTD only top 5 records of a table.
```sql
SELECT *
FROM emp
WHERE rownum <= 5;
```

### 2. WAQTD the top 5 higest salary getting employees details.
```sql
SELECT *
FROM (SELECT *
      FROM emp
      ORDER BY sal DESC
)
WHERE ROWNUM <= 5;
```

### 3. WAQTD the top 5 higest salary.
```sql
SELECT sal
FROM (SELECT distinct sal
      FROM emp
      ORDER BY sal DESC
)
WHERE ROWNUM <= 5;
```
