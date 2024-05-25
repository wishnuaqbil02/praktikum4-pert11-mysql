# Tugas Praktikum 4 (Pertemuan ke 11) <img src=https://qph.fs.quoracdn.net/main-qimg-648763cc041459725b62108f4fdf5b91 width="110px">


|Nama|NIM|Kelas|Mata Kuliah|
|----|---|-----|------|
|**Wishnu Aqbil Ramadani**|**312310591**|**TI.23.A6**|**Basis Data**|

# SQL Query Filtering

## Membuat Table Pegawai
```sql
CREATE TABLE pegawai (
    id_pegawai VARCHAR(10) PRIMARY KEY,
    nama_depan VARCHAR(50),
    nama_belakang VARCHAR(50),
    email VARCHAR(100),
    telepon VARCHAR(15),
    tgl_kontrak DATE,
    id_job VARCHAR(10),
    gaji INT,
    tunjangan INT
);
```

## Memasukan Data ke Dalam Table
```SQL
INSERT INTO pegawai (id_pegawai, nama_depan, nama_belakang, email, telepon, tgl_kontrak, id_job, gaji, tunjangan) VALUES
('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
('E004', 'Emna', 'Bunton', 'enna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 900000),
('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 900000),
('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
```

# Tugas Praktikum

## Buat Table Pegawai dan Isi Data nya Seperti Berikut :

![gambar](dokumentasi3/sss1.png)

# Tugas Praktikum

### 1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !
### 2. Tampilkan pegawai yang tunjangannya NULL!
### 3. Tampilkan pegawai yang tunjangannya tidak NULL!
### 4. Tampilkan/hitung jumlah baris/record tabel pegawai!
### 5. Tampilkan/hitung jumlah total gaji di tabel pegawai!
### 6. Tampilkan/hitung rata-rata gaji pegawai!
### 7. Tampilkan gaji terkecil!
### 8. Tampilkan gaji terbesar!

# Soal nya!!

## 1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !
```SQL
SELECT * FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```
### output nya:

![gambar](dokumentasi3/sss2.png)

## 2. Tampilkan pegawai yang tunjangannya NULL!
```sql
SELECT * FROM pegawai WHERE tunjangan IS NULL;
```
### output nya:

![gambar](dokumentasi3/sss3.png)

## 3. Tampilkan pegawai yang tunjangannya tidak NULL!
```sql
SELECT * FROM pegawai WHERE tunjangan IS NOT NULL;
```
### output nya:

![gambar](dokumentasi3/sss4.png)

## 4. Tampilkan/hitung jumlah baris/record tabel pegawai!
```sql
SELECT COUNT(*) AS Jumlah_Baris FROM pegawai;
```

### output nya:

![gambar](dokumentasi3/sss5.png)

## 5. Tampilkan/hitung jumlah total gaji di tabel pegawai!
```sql
SELECT SUM(gaji) AS Jumlah_Total_Gaji FROM pegawai;
```

### output nya:

![gambar](dokumentasi3/sss6.png)

## 6. Tampilkan/hitung rata-rata gaji pegawai!
```sql
SELECT AVG(gaji) AS Rata_Rata_Gaji FROM pegawai;
```

### output nya:

![gambar](dokumentasi3/sss7.png)

## 7. Tampilkan gaji terkecil!
```sql
SELECT MIN(gaji) AS Gaji_Terkecil FROM pegawai;
```

### output nya:

![gambar](dokumentasi3/sss8.png)

## 8. Tampilkan gaji terbesar!
```sql
SELECT MAX(gaji) AS Gaji_Terbesar FROM pegawai;
```

### output nya:

![gambar](dokumentasi3/sss9.png)

# Membuat Table Hewan
```sql
CREATE TABLE hewan (
    id VARCHAR(10) PRIMARY KEY,
    name VARCHAR(50),
    owner VARCHAR(50),
    species VARCHAR(50),
    sex CHAR(1)
);
```
# Memasukkan Data ke Dalam Table
```sql
INSERT INTO hewan (id, name, owner, species, sex) VALUES
('P1', 'Puffball', 'Diane', 'Hamster', 'f'),
('P2', 'Claws', 'Gwen', 'cat', 'm'),
('P3', 'Fluffy', 'Haro 1d', 'cat', 'f'),
('P4', 'Buffy', 'Haro 1d', 'dog', 'f'),
('P5', 'Fang', 'Benny', 'dog', 'm'),
('P6', 'Bowser', 'Diane', 'dog', 'm'),
('P7', 'Chirpy', 'Gwen', 'bird', 'f'),
('P8', 'Whistler', 'Gwen', 'bird', NULL),
('P9', 'Slim', 'Benny', 'snake', 'm');
```

### output nya:

![gambar](dokumentasi3/sss11.png)

# Tugas Praktikum

### 1. Tampilkan jumlah hewan yang dimiliki setiap owner
### 2. Tampilkan jumlah hewan berdasarkan spesies
### 3. Tampilkan jumlah hewan berdasarkan jenis kelamin
### 4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin
### 5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin
### 6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja

# Soal nya!!

## 1. Tampilkan jumlah hewan yang dimiliki setiap owner
```sql
SELECT owner, COUNT(*) AS jumlah_hewan
FROM hewan
GROUP BY owner;
```

### output nya:

![gambar](dokumentasi3/sss12.png)

## 2. Tampilkan jumlah hewan berdasarkan spesies
```sql
SELECT species, COUNT(*) AS jumlah_hewan
FROM hewan
GROUP BY species;
```

### output nya:

![gambar](dokumentasi3/sss13.png)

## 3. Tampilkan jumlah hewan berdasarkan jenis kelamin
```sql
SELECT sex, COUNT(*) AS jumlah_hewan
FROM hewan
GROUP BY sex;
```

### output nya:

![gambar](dokumentasi3/sss14.png)

## 4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin
```sql
SELECT species, sex, COUNT(*) AS jumlah_hewan
FROM hewan
GROUP BY species, sex;
```

### output nya:

![gambar](dokumentasi3/sss15.png)

## 5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin
```sql
SELECT species, sex, COUNT(*) AS jumlah_hewan
FROM hewan
WHERE species IN ('cat', 'dog')
GROUP BY species, sex;
```

### output nya:

![gambar](dokumentasi3/sss16.png)

## 6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja
```sql
SELECT sex, COUNT(*) AS jumlah_hewan
FROM hewan
WHERE sex IS NOT NULL
GROUP BY sex;
```

### output nya:

![gambar](dokumentasi3/sss17.png)
