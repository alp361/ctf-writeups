# Cat Viewer

## Description

> I built a little web site to search through my archive of cat photos.
> I hid a little something extra in the database too. See if you can find it!
> https://nessus-catviewer.chals.io/

## Solution

### 1 - Analyzing the Website
No source code was given for this challenge. <br> 
When I looked at the website, it was taking a parameter named `cat` and searching for cats with names like given value. <br>
As it turned out, it was searching the given value in the database with the `LIKE` operator and giving the matching values as a response.

### 2 - SQLi Detection

* I used the `"` as a value, and encountered with an error.

![sql_error](https://github.com/alp361/ctf-writeups/assets/69428956/7bb0b1e6-fd6d-4816-90b5-8e8c27a3a2b0)

* Then, I did a `UNION SELECT` attack to determine the number of columns and I was able to access the information that there are `4 columns`.

### 3 - Extracting Table and Column Names

* For extracting table name, I used `sqlmap` and I found that the table name is `cats`.

![db_table_name](https://github.com/alp361/ctf-writeups/assets/69428956/888e2149-54e6-4db0-a8fa-43580830bf94)

* For column names, I used the payload: `x" UNION SELECT sql,sql,sql,sql FROM sqlite_master WHERE type!='meta' AND sql NOT NULL AND name ='cats';--` <br>
It returned me the column names which are `id, image, name, flag`

![column_names_extracted](https://github.com/alp361/ctf-writeups/assets/69428956/6529cef8-68b9-401f-bbeb-2dfdade8633a)

### 4 - Retrieving the Flag

* Finally I retrieved the flag with this payload: `x" UNION SELECT flag,flag,flag,flag FROM 'cats';--`

![flag_found](https://github.com/alp361/ctf-writeups/assets/69428956/a2f883bc-b6dc-4129-8bf8-cfbcf92981dd)

  
```
flag{a_sea_of_cats}
```
