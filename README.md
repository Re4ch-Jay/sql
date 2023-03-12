# sql


```sql

create database assignment5_groupb_phat_panhareach;
use assignment5_groupb_phat_panhareach;

create table employee(
	role varchar(255),
    name varchar(255),
    building varchar(10),
    years_employed int
);

insert into employee(role, name, building, years_employed) 
values
("Engineer", "Becky A.", "1e", 4),
("Engineer", "Dan B.", "1e", 2),
("Engineer", "Sharon F.", "1e", 6),
("Engineer", "Dan M.", "1e", 4),
("Engineer", "Malcom S.", "1e", 1),
("Artist", "Tylar S.", "2w", 2),
("Artist", "Sherman D.", "2w", 8),
("Artist", "Jakob J.", "2w", 6),
("Artist", "Lillia A.", "2w", 7),
("Artist", "Brandon J.", "2w", 7),
("Manager", "Scott K.", "1e", 9),
("Manager", "Shirlee M.", "1e", 3),
("Manager", "Daria O.", "2w", 6);
select * from employee;

select * from employee where years_employed > 3;
select role, name, years_employed from employee where name like "%Da%";
select * from employee where building = "1e" order by years_employed desc;
select * from employee where building = '2w' order by years_employed ASC LIMIT 1;
	select max(years_employed) from employee;
SELECT role, AVG(years_employed) as avg_years_employed FROM employee GROUP BY role;
select building, count(years_employed) from employee group by building;
select sum(years_employed) as total_year_employed_by_engineer from employee where role = "Engineer";
select count(role) as number_of_artists from employee where role = "Artist";
select role, count(name) as empyees_amount from employee group by role;

```

```sql
create database assignment4_groupb_phat_panhareach;

use assignment4_groupb_phat_panhareach;

create table Employee (
	emp_num int primary key,
    emp_lname varchar(255),
	emp_fname varchar(255),
	emp_initial varchar(10) null,
	emp_hiredate date,
	job_code int
);


insert into Employee
	(emp_num, emp_lname, emp_fname, emp_initial, emp_hiredate, job_code) 
values
	(101, "News", "John", "G", "2000-11-08", 502),
    (102, "Senior", "David", "H", "1989-07-12", 501),
    (103, "Arbough", "June", "E", "1996-12-01", 500),
    (104, "Ramoras", "Anne", "K", "1987-11-15", 501),
    (105, "Johnson", "Alice", "K", "1993-02-01", 502),
    (106, "Smithfield", "William", "", "2004-05-22", 500),
    (107, "Alonzo", "Maria", "D", "1993-10-10", 500),
    (108, "Washington", "Ralph", "B", "1991-08-22", 501),
	(109, "Smith", "Larry", "W", "1997-08-18", 501);
   
select * from Employee where job_code=502;    
update Employee set emp_num = 501 where emp_num = 107;    
select * from Employee order by emp_fname, job_code desc;
delete from Employee where emp_fname = "William" and emp_lname = "Smithfield" and emp_hiredate = "2004-06-22" and job_code=500;    
alter table Employee add emp_pct int;
alter table Employee add proj_num int;
update Employee set proj_num = 18 where job_code = 500;
update Employee set proj_num = 25 where job_code >= 502;
update Employee set proj_num = 14 where job_code >= 501 and emp_hiredate < "1994-01-01";

```

