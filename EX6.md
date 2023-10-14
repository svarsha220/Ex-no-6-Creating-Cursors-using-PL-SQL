# Ex. No: 6 Creating Cursors using PL/SQL

## AIM: 
To create a cursor using PL/SQL.

## Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

## Program:
### Create employee table
```
create table EMPLOYEE3 (empid NUMBER, empname VARCHAR(20), dept VARCHAR(10),salary NUMBER);
```
### PLSQL Cursor code
```
SQL> SET SERVEROUTPUT ON;
SQL> DECLARE
  2  CURSOR employee_cursor IS
  3  SELECT * FROM employe;
  4  emp_id NUMBER;
  5  emp_name VARCHAR2(20);
  6  emp_dept VARCHAR2(20);
  7  emp_salary NUMBER;
  8  BEGIN
  9  OPEN employee_cursor;
 10  LOOP
 11  FETCH employee_cursor INTO emp_id, emp_name, emp_dept, emp_salary;
 12  EXIT WHEN employee_cursor%NOTFOUND;
 13  DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
 14  DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
 15  DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
 16  DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
 17  DBMS_OUTPUT.PUT_LINE('.........................');
 18  END LOOP;
 19  CLOSE employee_cursor;
 20  END;
 21  /

```
## Output:
![dbms 6 1](https://github.com/svarsha220/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/127709117/a43f8f28-7c20-472b-952f-90cfdbf3588b)


## Result:
Hence cursor has been created using PL/SQL.
