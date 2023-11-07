# Ex. No: 6 Creating Cursors using PL/SQL

DATE : 08.09.2023

### AIM:
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:

### Create employee table
```
CREATE TABLE employee4 (empid NUMBER,empname VARCHAR(10),dept VARCHAR(10),salary NUMBER);
INSERT INTO employee4 VALUES (1, 'aishu', 'manager', 50000);
INSERT INTO employee4 VALUES (2, 'harsha', 'sales executive',45000);
select * from employee4;
```

### PLSQL Cursor code
```
declare
  2  cursor employee4_cursor is
  3  select empid,empname,dept,salary
  4  from employee4;
  5  emp_id number;
  6  emp_name varchar(20);
  7  emp_dept varchar(20);
  8  emp_salary number;
  9  begin
 10  open employee4_cursor;
 11  loop
 12  fetch employee4_cursor into emp_id,emp_name,emp_dept,emp_salary;
 13  exit when employee4_cursor%NOTFOUND;
 14  DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
 15  DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
 16  DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
 17  DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
 18  end loop;
 19  close employee4_cursor;
 20  end;
 21  /
```


### Output:
![dbms 6 cursor op](https://github.com/AtchayaSundaramoorthy/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393516/b7866557-6881-4c06-878b-9db4f8a03ec5)


### Result:
THE PROGRAM HAS BEEN IMPLEMENTED SUCCESSFULLY
