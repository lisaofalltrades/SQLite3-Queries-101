# Most Common Queries

## SELECT

Ex 1. Get all the data for all the submissions.

  ```sql
SELECT * FROM submissions;
```
Results:
  ```sql
1|1|1|2016-08-12 13:50:08|2016-08-12 13:50:08
2|2|1|2016-08-12 13:50:08|2016-08-12 13:50:08
3|3|1|2016-08-12 13:50:08|2016-08-12 13:50:08
4|3|2|2016-08-12 13:50:08|2016-08-12 13:50:08
5|4|2|2016-08-12 13:50:08|2016-08-12 13:50:08
6|5|2|2016-08-12 13:50:08|2016-08-12 13:50:08
7|6|3|2016-08-12 13:50:08|2016-08-12 13:50:08
8|6|3|2016-08-12 13:50:08|2016-08-12 13:50:08
9|7|4|2016-08-12 13:50:08|2016-08-12 13:50:08
10|8|4|2016-08-12 13:50:08|2016-08-12 13:50:08
11|9|4|2016-08-12 13:50:08|2016-08-12 13:50:08
12|10|1|2016-08-12 13:50:08|2016-08-12 13:50:08
13|10|4|2016-08-12 13:50:08|2016-08-12 13:50:08
14|1|2|2016-08-12 13:50:08|2016-08-12 13:50:08
15|1|2|2016-08-12 13:50:08|2016-08-12 13:50:08
16|2|5|2016-08-12 13:50:08|2016-08-12 13:50:08
17|2|5|2016-08-12 13:50:08|2016-08-12 13:50:08
18|3|6|2016-08-12 13:50:08|2016-08-12 13:50:08
19|4|5|2016-08-12 13:50:08|2016-08-12 13:50:08
20|5|7|2016-08-12 13:50:08|2016-08-12 13:50:08
```
## WHERE

Ex 1. Show all the data for any submissions made for the challenge with id 1.
  ```sql
SELECT * FROM submissions WHERE challenge_id = 1;
```
Results:
  ```sql
1|1|1|2016-08-12 13:50:08|2016-08-12 13:50:08
2|2|1|2016-08-12 13:50:08|2016-08-12 13:50:08
3|3|1|2016-08-12 13:50:08|2016-08-12 13:50:08
12|10|1|2016-08-12 13:50:08|2016-08-12 13:50:08
```
Ex 2. Show the names and email addresses of any users with a "@gmail.com" email address.
  ```sql
SELECT name, email FROM users WHERE email LIKE "%@gmail.com%";
```
Results:
  ```sql
Dustin Wells|dustin@gmail.com
Jane X. Miller|jane@gmail.com
Raymond Oakley|raymond@gmail.com
Floyd Belle|floyd@gmail.com
Latoya Butler|latoya@gmail.com
Linda Davis|linda@gmail.com
Lisa Nguyen|lisapizza@gmail.com
```
## JOIN

Ex 1. Show the names and email addresses of any users who made a submission for the challenge named "sinatra-vs-rails".
  ```sql
SELECT users.name, users.email FROM users JOIN submissions ON users.id = submissions.user_id JOIN challenges ON challenge_id = challenges.id WHERE challenges.name LIKE '%sinatra-vs-rails%';
```
Results:
  ```sql
Gerald Woodard|gerald@outlook.com
Ray Locke|ray@yahoo.com
Jane Miller|jane@gmail.com
Dustin Wells|dustin@gmail.com
Dustin Wells|dustin@gmail.com
```
Ex 2. Show all the data for submissions made by the user named "Jason Parker".
  ```sql
SELECT * FROM submissions JOIN users ON users.id = submissions.user_id WHERE users.name = 'Jason Parker';
```
Results:
  ```sql
12|10|1|2016-08-12 13:50:08|2016-08-12 13:50:08|10|Jason Parker|jason@outlook.com|2016-08-12 13:50:08|2016-08-12 13:50:08
13|10|4|2016-08-12 13:50:08|2016-08-12 13:50:08|10|Jason Parker|jason@outlook.com|2016-08-12 13:50:08|2016-08-12 13:50:08
```
