create table gym_members(
	      id number(10) primary key,
        name varchar2(20)not null,
        age number(3) not null check(age>0),
        joining_date date not null,
        expiration_date date not null,
	      city varchar2(20) not null,
        cost number(10) not null check(cost>0),
        height number(10) not null check(height>0),
        weight number(10) not null check(weight>0),
        created_at date default sysdate);

create sequence users_seq
	start with 1
	increment by 1;


insert into gym_members(id,name,age,joining_date,expiration_date,cost,city,height,weight)values
(users_seq.nextval,'Tanvi',22,'08-Nov-2022','08-Nov-2023',22000,'Pune',159,45);

insert into gym_members(id,name,age,joining_date,expiration_date,cost,city,height,weight)values
(users_seq.nextval,'Damon',24,'08-Oct-2022','08-Oct-2023',23000,'Pune',165,60);

insert into gym_members(id,name,age,joining_date,expiration_date,cost,city,height,weight)values
(users_seq.nextval,'Stefan',23,'05-Sep-2022','05-Sep-2023',24000,'Pune',160,55);

insert into gym_members(id,name,age,joining_date,expiration_date,cost,city,height,weight)values
(users_seq.nextval,'Elena',22,'02-Mar-2022','02-Sep-2022',22500,'Mumbai',150,40);

insert into gym_members(id,name,age,joining_date,expiration_date,cost,city,height,weight)values
(users_seq.nextval,'Caroline',22,'06-Apr-2022','06-Nov-2022',22400,'Mumbai',150,40);

insert into gym_members(id,name,age,joining_date,expiration_date,cost,city,height,weight)values
(users_seq.nextval,'Bonnie',22,'09-Nov-2021','09-May-2022',27000,'Bangalore',140,30);

select * from gym_members;

select * from gym_members where cost >20000;
 
select * from gym_members where city= 'Pune';

select * from gym_members where city = 'Mumbai' and age > 20;

select * from gym_members where months_between(joining_date,expiration_date) = 3;

select name, (weight/((height/100)*(height/100))) as bmi from gym_members;

select * from gym_members order by age desc;

select name, EXTRACT(YEAR FROM sysdate) - age as BIRTH_YEAR from gym_members where city = 'Mumbai';

