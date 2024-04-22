* Revising the Select Query I  
  ```
  select * from city where population > 100000 and countrycode='USA';
  ```
* Revising the Select Query II  
  ```
  select name from city where population > 120000 and countrycode='USA';
  ```
* Select All  
  ```
  select * from city;
  ```
* Select by ID  
  ```
  select * from city where id=1661;
  ```
* Japanese Cities' Attributes  
  ```
  select * from city where countrycode='JPN'
  ```
* Japanese Cities' Names  
  ```
  select name from city where countrycode='JPN';
  ```
* Weather Observation Station 1  
  ```
  select city,state from station;
  ```
* Weather Observation Station 3  
  ```
  select distinct city from station where ID%2=0;
  ```
* Weather Observation Station 3  
  ```
  select round(sum(lat_n),2),round(sum(long_w),2) from station;
  ```
* Weather Observation Station 4  
  ```
  select count(city) - count(distinct city) from station;
  ```
* Weather Observation Station 5  
  ```
  select city, length(city) from station order by 2 asc,city asc limit 1;
  select city, length(city) from station order by 2 desc,city asc limit 1;
  ```
* Weather Observation Station 6  
  ```
  select city from station where left(city,1) in ('a','e','i','o','u');
  ```
* Weather Observation Station 7  
  ```
  select distinct city  from station where right(city,1) in ('a','e','i','o','u'); 
  ```
* Weather Observation Station 8  
  ```
  select city from station where right(city,1) in ('a','e','i','o','u') and left(city,1) in ('a','e','i','o','u');
  ```
* Weather Observation Station 9  
  ```
  select distinct city from station where left(city,1) not in ('a','e','i','o','u');
  ```
* Weather Observation Station 10  
  ```
  select distinct city from station where right(city,1) not in ('a','e','i','o','u');
  ```
* Weather Observation Station 11
  ```
  select distinct city from station where left(city,1) not in ('a','e','i','o','u') or right(city,1) not in ('a','e','i','o','u');
  ```
* Weather Observation Station 12
  ```
  select distinct city from station where left(city,1) not in ('a','e','i','o','u') and right(city,1) not in ('a','e','i','o','u');
  ```
* Higher than 75 marks  
  ```
  select name from students where marks>75 order by right(name, 3) , ID;
  ```
* Employee names  
  ```
  select name from employee order by name;
  ```
* Employee salary  
  ```
  select name from employee where salary>2000 and months<10 order by employee_id;
  ```
* Revising Aggregations - The Count Function  
  ```
  select count(*) from city where population>100000;
  ```
* Revising Aggregations - The Sum Function  
  ```
  select sum(population) from city where district='california';
  ```
* Average Population  
  ```
  select round(avg(population)) from city; ```
* Japan Population  
  ```
  select sum(population) from city where countrycode='JPN';
  ```
* Average population of each continent  
  ```
  select country.continent, floor(avg(city.population)) from city join country
  on city.countrycode=country.code group by country.continent;
  ```
* Top earners
  ```
  select max(salary*months),count(*)
  from employee where
  months*salary=(select max(salary*months) from employee);
  ```
