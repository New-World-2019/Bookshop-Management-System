# BookShop Management System
Create a MySQL Database

DataBase Name : Management

And Tables : 

Books

    int id			// Primary Key
	string name
	string auth
	int price
	int qty

```cpp
create table books(id INT(11) primary key not null auto_increment,name VARCHAR(100),auth VARCHAR(100),price INT(11),qty INT(11));
```

suppliers

	int id				//Primary Key
	string name
	long int phn
	string addr_line1
	string addr_line2
	string addr_city
	string addr_state

```cpp
create table suppliers(id INT(11) primary key not null auto_increment,name VARCHAR(100),phn BIGINT(11),addr_line1 VARCHAR(100),addr_line2 VARCHAR(100),addr_city VARCHAR(100),addr_state VARCHAR(100));
```

purchases

	int ord_id			//Primary Key
	int book_id		    //FK ref (books)
	int sup_id			//FK ref (suppliers)
	int qty
	date dt_ordered
	int eta
	char received		// Check(T or C or F) def (F)
	int inv
	

```cpp
create table purchases(ord_id INT(11) primary key not null auto_increment,book_id INT(11),sup_id INT(11),qty INT(11),dt_ordered DATE,eta INT(11),received CHAR(1) default('F'),inv INT(11),FOREIGN KEY(book_id) REFERENCES books(id),FOREIGN KEY(sup_id) REFERENCES suppliers(id));
```

employees

	int id				//Primary Key
	string name
	string addr_line1
	string addr_line2
	string addr_city
	string addr_state
	long int phn
	date date_of_joining
	long int salary
	string mgr_status	//check(T or F) def f

```cpp
create table employees(id INT(11) primary key not null auto_increment,name VARCHAR(100),addr_line1 VARCHAR(100),addr_line2 VARCHAR(100),addr_city VARCHAR(100),phn BIGINT(11),date_of_joining DATE,salary BIGINT(11),mgr_status CHAR(1) default('F'));
```


members

    int id				//Primary Key
	string name
	string addr_line1
	string addr_line2
	string addr_city
	string addr_state
	long int phn
	date beg_date
	date end_date
	string valid

```cpp
create table members(id INT(11) primary key not null auto_increment,name VARCHAR(100),addr_line1 VARCHAR(100),addr_line2 VARCHAR(100),addr_city VARCHAR(100),addr_state VARCHAR(100),phn BIGINT(11),beg_date DATE,end_date DATE,valid VARCHAR(100));
 ```
sales

	int invoice_id		//Primary key
    int member_id		//FK ref member(id)
	int book_id		//FK ref books(id)
	int qty
	int amount
	date date_s
```cpp
create table sales(invoice_id INT(11) primary key not null auto_increment,member_id INT(11),book_id INT(11),qty INT(11),amount INT(11),date_s DATE,FOREIGN KEY(member_id) REFERENCES members(id),FOREIGN KEY(book_id) REFERENCES books(id));
 ```
