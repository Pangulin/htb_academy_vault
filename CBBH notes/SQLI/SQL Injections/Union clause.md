
we can use the UNION function to string multiple queries together referencing diffrent tables

this only works though if we select the same numbers of collumns from both tables.
For that to work we need to find out how many collumns the "first" table has in order to match it.

this can be done by using junk data wich we put in place to test: 

<span style="color:rgb(255, 0, 0)">select * from departments UNION select NULL,NULL from employees</span><span style="color:rgb(255, 0, 0)">;</span> 

here we see an exxample where there are 2 collumns 

+---------+--------------------+
| dept_no | dept_name          |
+---------+--------------------+
| d009    | Customer Service   |
| d005    | Development        |
| d002    | Finance            |
| d003    | Human Resources    |
| d001    | Marketing          |
| d004    | Production         |
| d006    | Quality Management |
| d008    | Research           |
| d007    | Sales              |
| NULL    | NULL               |
+---------+--------------------+

now using this logic we can select datasets from multiple tables with something like this: 

<span style="color:rgb(255, 0, 0)">select * from departments UNION select emp_no,NULL from employees;</span>

which will return something like this: 

+--------------+--------------------+
| dept_no      | dept_name          |
+--------------+--------------------+
| d009         | Customer Service   |
| d005         | Development        |
| d002         | Finance            |
| d003         | Human Resources    |
| d001         | Marketing          |
| d004         | Production         |
| d006         | Quality Management |
| d008         | Research           |
| d007         | Sales              |
| Georgi       | NULL               |
| Vivian       | NULL               |
| Temple       | NULL               |
....
....
....

(datasets that have duplicates only get selected once like this)

