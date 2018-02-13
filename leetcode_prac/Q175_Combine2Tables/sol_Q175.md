## Answer of Q175 - Combine Two Tables
The answer is simply as below:
```
SELECT Person.FirstName, Person.LastName, Address.City, Address.State FROM Person LEFT OUTER JOIN Address ON Person.PersonId=Address.PersonId;
```

However, I write additional to create a test table:
```
CREATE TABLE Person (PersonId int, FirstName varchar(255), LastName varchar(255));
INSERT INTO Person (PersonId, FirstName, LastName) VALUES ('1', 'Wang', 'Allen');
INSERT INTO Person (PersonId, FirstName, LastName) VALUES ('2', 'Zhang', 'ZJ');
INSERT INTO Person (PersonId, FirstName, LastName) VALUES ('3', 'Li', 'Meili');
INSERT INTO Person (PersonId, FirstName, LastName) VALUES ('4', 'Liu', 'Choulou');

CREATE TABLE Address (
AddressId INTEGER PRIMARY KEY  AUTOINCREMENT  NOT NULL, 
PersonId INTEGER NOT NULL,
City VARCHAR, 
State VARCHAR,
FOREIGN KEY(PersonId) REFERENCES Person(PersonId)
);
INSERT INTO Address (AddressId, PersonId, City, State) VALUES ('1', '2', 'New York City', 'New York');
INSERT INTO Address (AddressId, PersonId, City, State) VALUES ('3', '1', 'Honolulu', 'Hawaii');
INSERT INTO Address (AddressId, PersonId, City, State) VALUES ('2', '3', 'Beijing', 'China');

```
