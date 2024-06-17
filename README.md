#guvi db design 

1 create database guvi;
2 use guvi;
```
create table user(
userid int primary key auto_increment,
username varchar(25) unique,
useremail varchar(255) unique,
usermobile varchar(10) not null
);user table created (studentsdata) .here insertion of students data's in user table 


create table course(
course_id int auto_increment primary key,
userid int,
course_name varchar(25),
course_duration varchar(255),
course_fees varchar(25),
foreign key(userid) references user(userid)
); .here insertion of students data's course data in course table 
````
```
create table admissions(
userid int,
course_id int,
admission_fees varchar(25),
foreign key(userid) references user(userid),
foreign key(course_id) references course(course_id)
);.here insertion of students data's addmissons data in addmission table
````
`````
create table codekataa(
userid int,
solved_problem varchar(25) not null,
foreign key(userid) references user(userid)
);here insertion of students data's codekataa data in codekataa table
```
```***``
create table mentor(
userid int,
course_id int not null,
mentor_name varchar(25) ,
foreign key(userid) references user(userid),
foreign key(course_id) references course(course_id)
);here insertion of students data's mentor data in  mentor table
````
```***``
create table studentsAttendance(
A_id int,
userid int,
A_date datetime default now(),
status boolean default true,
foreign key(userid) references user(userid)
);here insertion of students data's studentsAddendance data in attendance table
~~~~
```***``

create table task(
userid int,
submited_task varchar(25) not null,
task_mark varchar(25) ,
foreign key(userid) references user(userid)
);here insertion of students data's task data in task table
`````
```
create table leaderboard(
userid int,
course_id int,
batch varchar(25) not null,
submited_task varchar(25) not null,
foreign key(userid) references user(userid),
foreign key(course_id) references course(course_id)
);here insertion of students data's studentsleaderboard data in leaderboard table
````
```
create table queries (
userid int,
topics varchar(2000),
reasons_queries varchar(2550),
foreign key (userid) references user(userid)
);here insertion of students data's studentsqueriess data in queries table
`````
