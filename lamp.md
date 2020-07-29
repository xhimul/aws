## LAMP
- https://www.tecmint.com/install-lamp-with-phpmyadmin-in-ubuntu-20-04/


## Create User to Access the BookstoreDB Database
MariaDB [BookstoreDB]> `CREATE USER bookstoreuser@localhost IDENTIFIED BY 'YourPasswordHere';`\
MariaDB [BookstoreDB]> `GRANT ALL PRIVILEGES ON  BookstoreDB.* to bookstoreuser@localhost;`\
MariaDB [BookstoreDB]> `FLUSH PRIVILEGES;`
