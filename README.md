# sql

```sql
select cName, Major from Apply where cName = "Standford"; 


create table College(
	cName varchar(255) primary key, 
    state varchar(255), 
    enrollment int
);

insert into College(cName, state, enrollment) values("Standford", "CA", 15000);
insert into College(cName, state, enrollment) values("Berkeley", "CA", 36000);
insert into College(cName, state, enrollment) values("MIT", "MA", 10000);
insert into College(cName, state, enrollment) values("Cornell", "NY", 21000);

create table Student(
	sID int primary key, 
	sName varchar(255), 
    GPA float(1), 
    sizeHS int
);

insert into Student(sID, sName, GPA, sizeHS) values (123, "Amy", 3.9, 1000);
insert into Student(sID, sName, GPA, sizeHS) values (234, "Bob", 3.6, 1500);
insert into Student(sID, sName, GPA, sizeHS) values (345, "Craig", 3.5, 500);
insert into Student(sID, sName, GPA, sizeHS) values (456, "Doris", 3.9, 1000);
insert into Student(sID, sName, GPA, sizeHS) values (567, "Edward", 2.9, 2000);
insert into Student(sID, sName, GPA, sizeHS) values (678, "Fay", 3.8, 200);
insert into Student(sID, sName, GPA, sizeHS) values (789, "Gary", 3.4, 800);
insert into Student(sID, sName, GPA, sizeHS) values (987, "Halen", 3.7, 800);
insert into Student(sID, sName, GPA, sizeHS) values (876, "Irene", 3.9, 400);
insert into Student(sID, sName, GPA, sizeHS) values (765, "Jay", 2.9, 1500);
insert into Student(sID, sName, GPA, sizeHS) values (654, "Amy", 3.9, 1000);
insert into Student(sID, sName, GPA, sizeHS) values (543, "Craig", 3.4, 2000);

create table Apply(
	sID int, cName varchar(255), Major varchar(255), decision varchar(1),
    foreign key (sID) references Student(sID),
    foreign key (cName) references College(cName)
);
insert into Apply(sID, cName, Major, decision) values(123, "Standford", "CS", "Y");
insert into Apply(sID, cName, Major, decision) values(123, "Standford", "EE", "N");
insert into Apply(sID, cName, Major, decision) values(123, "Berkeley", "CS", "Y");
insert into Apply(sID, cName, Major, decision) values(123, "Cornell", "EE", "Y");
insert into Apply(sID, cName, Major, decision) values(234, "Berkeley", "Biology", "N");
insert into Apply(sID, cName, Major, decision) values(345, "MIT", "Bioengineering", "Y");
insert into Apply(sID, cName, Major, decision) values(345, "Cornell", "Bioengineering", "N");
insert into Apply(sID, cName, Major, decision) values(345, "Cornell", "CS", "Y");
insert into Apply(sID, cName, Major, decision) values(345, "Cornell", "EE", "N");
insert into Apply(sID, cName, Major, decision) values(678, "Standford", "History", "Y");
insert into Apply(sID, cName, Major, decision) values(987, "Standford", "CS", "Y");
insert into Apply(sID, cName, Major, decision) values(987, "Berkeley", "CS", "Y");
insert into Apply(sID, cName, Major, decision) values(876, "Standford", "CS", "N");
insert into Apply(sID, cName, Major, decision) values(876, "MIT", "Marine Biology", "N");
insert into Apply(sID, cName, Major, decision) values(876, "MIT", "History", "Y");
insert into Apply(sID, cName, Major, decision) values(765, "Standford", "History", "Y");
insert into Apply(sID, cName, Major, decision) values(765, "Cornell", "History", "N");
insert into Apply(sID, cName, Major, decision) values(765, "Cornell", "History", "N");
insert into Apply(sID, cName, Major, decision) values(765, "Cornell", "Psychology", "Y");
insert into Apply(sID, cName, Major, decision) values(543, "MIT", "CS", "N");

select * from College where enrollment > 20000;
select cName from College where state="MA";
select * from Student where GPA > 3.0;
select sName, GPA from Student where sName="Helen";
select * from Apply where Major="CS";



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
