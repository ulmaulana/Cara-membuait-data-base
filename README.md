# Cara membuat Data Base Tabel pada XAMPP

## Buka aplikasi XAMPP
>1. Start _`Apache`_ dan _`Sql`_ sampai berwarna hijau

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/0706fc2a-7878-4ccc-b020-c15708715038)

>2. Buka shell disebelah pojok kanan atas

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/a6df591c-4b80-4953-b427-fb8c7bf37aba)

>3. Setelah shell terbuka, masukan perintah
```
mysql -u root
```

>4. Agar tidak error karena duplicate, mari masukan perintah ini untuk melihat list database yang sudah kita buat sebelumnya
```
show databases;
```
>disini akan muncul daftar database yang sudah kita buat

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/dc4ee412-ed4d-47e9-b567-6e888e8906ea)

>5. Sebagai contoh, saya akan membuat database Mahasiswa (dbMahasiswa), kita akan memasukkan command berikut untuk membuat dbMahasiswa
```
create database dbMahasiswa;
```
>Contoh dalam gambar ini ketika sudah berhasil melakukan create

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/cd0c3dbb-3647-449e-822d-b53b00795a0d)

>6. Setelah selesai create, kita akan menggunakan dbMahasiswa untuk membuat tabel, dengan cara memasukkan command berikut
```
use dbMahasiswa
```
>Tampilan ketika sudah change dari none ke dbMahasiswa

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/b4ecbf70-66f0-4185-ba8f-b7a6b381d683)

>7. Setelah memasukkan command _`use dbMahasiswa`_ kita akan membuat _`Tabel`_
Contoh kode ini untuk dbMahasiswa, kalian bisa menyesuaikan apabila bukan tabel untuk dbMahasiswa
```
CREATE TABLE dbMahasiswa (
    ID_Mahasiswa VARCHAR(10) PRIMARY KEY,
    Nama VARCHAR(100) NOT NULL,
    Tanggal_Lahir DATE NOT NULL,
    Program_Studi VARCHAR(50) NOT NULL,
    Tahun_Masuk YEAR NOT NULL
);
```
>Setelah berhasil menginput kode, silahkan cek tabel dengan cara memasukkan command
```
desc dbMahasiswa;
```
![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/59ad45f7-da40-4a32-90cf-b4322ce12fe2)

>8. Setelah tabel database dbMahasiswa sudah dibuat, disini kita akan melakukan ALTER (digunakan untuk mengubah struktur objek yang sudah ada dalam database), dan DROP COLUMN (digunakan untuk menghapus baris data dari sebuah tabel).
>8.1 _`ALTER`_ disini kita akan menambahkan email dengan menggunakan _`ALTER`_. Kita akan memasukkan perintah
```
ALTER TABLE dbMahasiswa
ADD COLUMN email VARCHAR(100);
```
>Gambar setelah berhasil melakukkan perintah _`ALTER`_

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/f22124f3-cde7-4ca7-835f-bd537cd22f4b)

>9. Menghapus teks pada suatu baris dengan menggunakan _`Drop Column`_
Masukkan perintah
```
ALTER TABLE dbMahasiswa DROP COLUMN ID_Mahasiswa;
```
>9.1 Gambar ketika sudah berhasil melakukan delete pada suatu baris database

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/f9f3235b-d8c0-4dbe-b5f7-38f3128bfa65)

![image](https://github.com/ulmaulana/Cara-membuat-data-base/assets/152008359/32208e3a-ed9d-48a1-a5f7-7934d3f6a322)

## Tutorial dicukupkan sampai sini, Sekian Terima kasih. Wassalamu'alaikum Warrahmatullahi Wabarakatuh.


## Cheat Sheet
>Berikut saya paparkan Cheat Sheet mySQL agar mempermudah kita mengingat dan belajar mySQL!
>Credit, thanks to [bradtraversy](https://gist.github.com/bradtraversy/c831baaad44343cc945e76c2e30927b3)

# MySQL Cheat Sheet 1
Tentu! Berikut ini adalah cheat sheet untuk beberapa perintah dasar yang sering digunakan dalam manajemen basis data:

### MySQL/MariaDB:

#### Interaksi dengan Database:
- **Login ke Database:**
  ```
  mysql -u username -p
  ```
- **Pilih Database:**
  ```
  USE nama_database;
  ```
- **Tampilkan Semua Database:**
  ```
  SHOW DATABASES;
  ```

#### Interaksi dengan Tabel:
- **Tampilkan Semua Tabel:**
  ```
  SHOW TABLES;
  ```
- **Tampilkan Struktur Tabel:**
  ```
  DESCRIBE nama_tabel;
  ```
- **Tampilkan Data dari Tabel:**
  ```
  SELECT * FROM nama_tabel;
  ```

#### Manipulasi Data:
- **Tambah Data:**
  ```
  INSERT INTO nama_tabel (kolom1, kolom2, ...) VALUES (nilai1, nilai2, ...);
  ```
- **Perbarui Data:**
  ```
  UPDATE nama_tabel SET kolom1 = nilai1, kolom2 = nilai2 WHERE kondisi;
  ```
- **Hapus Data:**
  ```
  DELETE FROM nama_tabel WHERE kondisi;
  ```

#### Mengelola Tabel:
- **Buat Tabel:**
  ```
  CREATE TABLE nama_tabel (
      kolom1 tipe_data,
      kolom2 tipe_data,
      ...
  );
  ```
- **Ubah Tabel (Tambah Kolom):**
  ```
  ALTER TABLE nama_tabel ADD nama_kolom tipe_data;
  ```
- **Hapus Tabel:**
  ```
  DROP TABLE nama_tabel;
  ```

### PostgreSQL:

#### Interaksi dengan Database:
- **Login ke Database:**
  ```
  psql -U username -d nama_database
  ```
- **Tampilkan Semua Database:**
  ```
  \l
  ```
- **Pilih Database:**
  ```
  \c nama_database
  ```

#### Interaksi dengan Tabel:
- **Tampilkan Semua Tabel:**
  ```
  \dt
  ```
- **Tampilkan Struktur Tabel:**
  ```
  \d nama_tabel
  ```
- **Tampilkan Data dari Tabel:**
  ```
  SELECT * FROM nama_tabel;
  ```

#### Manipulasi Data:
- **Tambah Data:**
  ```
  INSERT INTO nama_tabel (kolom1, kolom2, ...) VALUES (nilai1, nilai2, ...);
  ```
- **Perbarui Data:**
  ```
  UPDATE nama_tabel SET kolom1 = nilai1, kolom2 = nilai2 WHERE kondisi;
  ```
- **Hapus Data:**
  ```
  DELETE FROM nama_tabel WHERE kondisi;
  ```

#### Mengelola Tabel:
- **Buat Tabel:**
  ```
  CREATE TABLE nama_tabel (
      kolom1 tipe_data,
      kolom2 tipe_data,
      ...
  );
  ```
- **Ubah Tabel (Tambah Kolom):**
  ```
  ALTER TABLE nama_tabel ADD COLUMN nama_kolom tipe_data;
  ```
- **Hapus Tabel:**
  ```
  DROP TABLE nama_tabel;
  ```

### MongoDB:

#### Interaksi dengan Database:
- **Login ke Database:**
  ```
  mongo
  ```
- **Tampilkan Semua Database:**
  ```
  show dbs
  ```
- **Pilih Database:**
  ```
  use nama_database
  ```

#### Interaksi dengan Koleksi:
- **Tampilkan Semua Koleksi:**
  ```
  show collections
  ```
- **Tampilkan Data dari Koleksi:**
  ```
  db.nama_koleksi.find()
  ```

#### Manipulasi Data:
- **Tambah Data:**
  ```
  db.nama_koleksi.insert({field1: value1, field2: value2, ...})
  ```
- **Perbarui Data:**
  ```
  db.nama_koleksi.update({kondisi}, {$set: {field1: value1, field2: value2, ...}})
  ```
- **Hapus Data:**
  ```
  db.nama_koleksi.remove({kondisi})
  ```

#### Mengelola Koleksi:
- **Buat Koleksi:**
  ```
  db.createCollection("nama_koleksi")
  ```
- **Hapus Koleksi:**
  ```
  db.nama_koleksi.drop()
  ```

Ini hanya beberapa perintah dasar yang paling umum digunakan. Setiap sistem basis data memiliki sintaks yang berbeda, jadi pastikan untuk merujuk ke dokumentasi resmi sistem basis data yang Anda gunakan untuk informasi lebih lanjut.

# MySQL Cheat Sheet 2

> Help with SQL commands to interact with a MySQL database

## MySQL Locations
* Mac             */usr/local/mysql/bin*
* Windows         */Program Files/MySQL/MySQL _version_/bin*
* Xampp           */xampp/mysql/bin*

## Add mysql to your PATH

```bash
# Current Session
export PATH=${PATH}:/usr/local/mysql/bin
# Permanantly
echo 'export PATH="/usr/local/mysql/bin:$PATH"' >> ~/.bash_profile
```

On Windows - https://www.qualitestgroup.com/resources/knowledge-center/how-to-guide/add-mysql-path-windows/

## Login

```bash
mysql -u root -p
```

## Show Users

```sql
SELECT User, Host FROM mysql.user;
```

## Create User

```sql
CREATE USER 'someuser'@'localhost' IDENTIFIED BY 'somepassword';
```

## Grant All Priveleges On All Databases

```sql
GRANT ALL PRIVILEGES ON * . * TO 'someuser'@'localhost';
FLUSH PRIVILEGES;
```

## Show Grants

```sql
SHOW GRANTS FOR 'someuser'@'localhost';
```

## Remove Grants

```sql
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'someuser'@'localhost';
```

## Delete User

```sql
DROP USER 'someuser'@'localhost';
```

## Exit

```sql
exit;
```

## Show Databases

```sql
SHOW DATABASES
```

## Create Database

```sql
CREATE DATABASE acme;
```

## Delete Database

```sql
DROP DATABASE acme;
```

## Select Database

```sql
USE acme;
```

## Create Table

```sql
CREATE TABLE users(
id INT AUTO_INCREMENT,
   first_name VARCHAR(100),
   last_name VARCHAR(100),
   email VARCHAR(50),
   password VARCHAR(20),
   location VARCHAR(100),
   dept VARCHAR(100),
   is_admin TINYINT(1),
   register_date DATETIME,
   PRIMARY KEY(id)
);
```

## Delete / Drop Table

```sql
DROP TABLE tablename;
```

## Show Tables

```sql
SHOW TABLES;
```

## Insert Row / Record

```sql
INSERT INTO users (first_name, last_name, email, password, location, dept, is_admin, register_date) values ('Brad', 'Traversy', 'brad@gmail.com', '123456','Massachusetts', 'development', 1, now());
```

## Insert Multiple Rows

```sql
INSERT INTO users (first_name, last_name, email, password, location, dept,  is_admin, register_date) values ('Fred', 'Smith', 'fred@gmail.com', '123456', 'New York', 'design', 0, now()), ('Sara', 'Watson', 'sara@gmail.com', '123456', 'New York', 'design', 0, now()),('Will', 'Jackson', 'will@yahoo.com', '123456', 'Rhode Island', 'development', 1, now()),('Paula', 'Johnson', 'paula@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now()),('Tom', 'Spears', 'tom@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now());
```

## Select

```sql
SELECT * FROM users;
SELECT first_name, last_name FROM users;
```

## Where Clause

```sql
SELECT * FROM users WHERE location='Massachusetts';
SELECT * FROM users WHERE location='Massachusetts' AND dept='sales';
SELECT * FROM users WHERE is_admin = 1;
SELECT * FROM users WHERE is_admin > 0;
```

## Delete Row

```sql
DELETE FROM users WHERE id = 6;
```

## Update Row

```sql
UPDATE users SET email = 'freddy@gmail.com' WHERE id = 2;

```

## Add New Column

```sql
ALTER TABLE users ADD age VARCHAR(3);
```

## Modify Column

```sql
ALTER TABLE users MODIFY COLUMN age INT(3);
```

## Order By (Sort)

```sql
SELECT * FROM users ORDER BY last_name ASC;
SELECT * FROM users ORDER BY last_name DESC;
```

## Concatenate Columns

```sql
SELECT CONCAT(first_name, ' ', last_name) AS 'Name', dept FROM users;

```

## Select Distinct Rows

```sql
SELECT DISTINCT location FROM users;

```

## Between (Select Range)

```sql
SELECT * FROM users WHERE age BETWEEN 20 AND 25;
```

## Like (Searching)

```sql
SELECT * FROM users WHERE dept LIKE 'd%';
SELECT * FROM users WHERE dept LIKE 'dev%';
SELECT * FROM users WHERE dept LIKE '%t';
SELECT * FROM users WHERE dept LIKE '%e%';
```

## Not Like

```sql
SELECT * FROM users WHERE dept NOT LIKE 'd%';
```

## IN

```sql
SELECT * FROM users WHERE dept IN ('design', 'sales');
```

## Create & Remove Index

```sql
CREATE INDEX LIndex On users(location);
DROP INDEX LIndex ON users;
```

## New Table With Foreign Key (Posts)

```sql
CREATE TABLE posts(
id INT AUTO_INCREMENT,
   user_id INT,
   title VARCHAR(100),
   body TEXT,
   publish_date DATETIME DEFAULT CURRENT_TIMESTAMP,
   PRIMARY KEY(id),
   FOREIGN KEY (user_id) REFERENCES users(id)
);
```

## Add Data to Posts Table

```sql
INSERT INTO posts(user_id, title, body) VALUES (1, 'Post One', 'This is post one'),(3, 'Post Two', 'This is post two'),(1, 'Post Three', 'This is post three'),(2, 'Post Four', 'This is post four'),(5, 'Post Five', 'This is post five'),(4, 'Post Six', 'This is post six'),(2, 'Post Seven', 'This is post seven'),(1, 'Post Eight', 'This is post eight'),(3, 'Post Nine', 'This is post none'),(4, 'Post Ten', 'This is post ten');
```

## INNER JOIN

```sql
SELECT
  users.first_name,
  users.last_name,
  posts.title,
  posts.publish_date
FROM users
INNER JOIN posts
ON users.id = posts.user_id
ORDER BY posts.title;
```

## New Table With 2 Foriegn Keys

```sql
CREATE TABLE comments(
	id INT AUTO_INCREMENT,
    post_id INT,
    user_id INT,
    body TEXT,
    publish_date DATETIME DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY(id),
    FOREIGN KEY(user_id) references users(id),
    FOREIGN KEY(post_id) references posts(id)
);
```

## Add Data to Comments Table

```sql
INSERT INTO comments(post_id, user_id, body) VALUES (1, 3, 'This is comment one'),(2, 1, 'This is comment two'),(5, 3, 'This is comment three'),(2, 4, 'This is comment four'),(1, 2, 'This is comment five'),(3, 1, 'This is comment six'),(3, 2, 'This is comment six'),(5, 4, 'This is comment seven'),(2, 3, 'This is comment seven');
```

## Left Join

```sql
SELECT
comments.body,
posts.title
FROM comments
LEFT JOIN posts ON posts.id = comments.post_id
ORDER BY posts.title;

```

## Join Multiple Tables

```sql
SELECT
comments.body,
posts.title,
users.first_name,
users.last_name
FROM comments
INNER JOIN posts on posts.id = comments.post_id
INNER JOIN users on users.id = comments.user_id
ORDER BY posts.title;

```

## Aggregate Functions

```sql
SELECT COUNT(id) FROM users;
SELECT MAX(age) FROM users;
SELECT MIN(age) FROM users;
SELECT SUM(age) FROM users;
SELECT UCASE(first_name), LCASE(last_name) FROM users;

```

## Group By

```sql
SELECT age, COUNT(age) FROM users GROUP BY age;
SELECT age, COUNT(age) FROM users WHERE age > 20 GROUP BY age;
SELECT age, COUNT(age) FROM users GROUP BY age HAVING count(age) >=2;

```
