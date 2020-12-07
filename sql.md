# Moviebooking_db

#### Task #1: Create Database
```
create database moviebooking_db;
use moviebooking_db;

```
#### Task 2: Create users table
```
create table user(
id int primary key auto_increment,
user_id int not null,
name varchar(50) not null,
email varchar(50) not null,
password varchar(50) not null,
dob date,
gender char(1),
active boolean not null default 1,
created_date timestamp not null default current_timestamp,
modified_date timestamp not null default current_timestamp on update current_timestamp,
unique(email,user_id),
check ( gender in ('M','F'))

);

```

#### Task 2.1: insert values to users
```
insert into user (user_id,name,email,password,dob,gender) values ( 1,'celshia','celshia@gmail.com', 'pass123','1998-10-31','M');
```
#### Task 2.2: List all users
```
select * from user;
```

#### Task 2.3: create cities Table
```
create table cities(

city_id int primary key auto_increment,
city_name varchar(50) not null
);

``` 

#### Task 2.4: insert values into cities table
```
insert into cities (city_name) values ( 'chennai');
insert into cities (city_name) values ('Coimbatore');
insert into cities (city_name) values ('Dindigul');
```
### Task 2.5: List cities list
```
selelct * from cities;
```
#### Task 3: Create theatres table
```
create table theatres(

theatre_id int primary key auto_increment,
theatre_name varchar(50) not null,
foreign key(theatre_id) references cities(city_id)
);
```
#### Task 3.1: insert values to theatres
```
insert into theatres (theatre_name) values ( 'inox');
insert into theatres (theatre_name) values ('mayajal');
insert into theatres (theatre_name) values ('the forum vijaya mall');
insert into theatres (theatre_name) values ('The Cinema Brookefields');
insert into theatres (theatre_name) values ('Big Cinemas');
```
#### Task 3.2: list theatres
```
select * from theatres;

```
### Task 4: create movie table
```
create table movie(
id varchar(15),
name varchar(30),
imgpath varchar(100),
trailer varchar(100),
storyline text(1000),
director text(1000),
stars text(1000));

```
### Task 4.1: insert values to movie
```

insert into movie(id,name,imgpath,trailer,storyline,director,stars) values("01","Frozen","images/aaa.jpg", "https://www.youtube.com/watch?v=R-cdIvgBCWY", "When the newly crowned Queen Elsa accidentally uses her power to turn things into ice to curse her home in infinite winter, her sister Anna teams up with a mountain man, his playful reindeer, and a snowman to change the weather condition.", " Chris Buck, Jennifer Lee, Stevie Wermers, Kevin Deters", "Idina Menzel, Kristen Bell, Josh Gad, Jonathan Groff");
insert into movie(id,name,imgpath,trailer,storyline,director,stars) values("02","Avatar","images/bbb.jpg", "https://www.youtube.com/watch?v=5PSNL1qE6VY", "A paraplegic Marine dispatched to the moon Pandora on a unique mission becomes torn between following his orders and protecting the world he feels is his home.", "James Cameron", "Sam Worthington, Zoe Saldana, Sigourney Weaver");

```
### Task: 4.2 list movie list
```
select * from movie;

```
### Task 5: create tickets
```
create table tickets(
id int primary key auto_increment,
movieId int not null,
theatreId int not null,
seats int not null,
selectedseats int not null,
amount int not null,
createdBy int not null,
booking_id int not null,
createdDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP 
);

```
### TASK 5.1: insert into to tickets
```

insert into bookings(movieId,theatreId,seats,selectedseats,amount,createdBy,booking_id) values(01,100,1,1,120,1,1);


```


