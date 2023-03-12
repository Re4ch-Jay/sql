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
