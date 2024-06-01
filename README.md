# Praktikum-5

## LATIHAN !!!

1. Lakukan join table Mahasiswa dan Dosen

2. Lakukan join tabel Matakuliah dan Dosen
   
3. Lakukan join table JadwalMengajar, Dosen, dan Matakuluan
   
4. Lakukan join tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen

## JOIN table Mahasiswa dan Dosen

### untuk tabel mahasiswa :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/71893328-520a-43da-90a5-4d48bf5ea86b)

### untuk tabel dosen :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/a3dcb934-c918-4c27-8d90-5fa8a102be00)

### untuk tabel krs mahasiswa :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/397a9055-0380-438f-8122-2fa04a7c5f9e)

### untuk tabel matakuliah :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/458d13b2-e473-4517-a8ce-8af7b6fd13f9)

### untuk tabel jadwal mengajar :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/cc4da049-4aea-4816-9cb8-6bd1c7bffa88)

# 1. Lakukan Join Table Mahasiswa Dan Dosen

## Untuk perintah bisa menggunakan (INNER JOIN)

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama, tb_mahasiswa.jk, tb_dosen.nama AS "Dosen" FROM tb_mahasiswa INNER JOIN tb_dosen ON tb_dosen.kd_ds = tb_mahasiswa.kd_ds;`

Hasilnya akan seperti ini :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/db6cbbb1-83ca-4c33-af1c-1fbb4fe4d628)

> Note Digunakan untuk menampilkan baris tabel yang memiliki nilai yang sama pada kolom yang terkait

## Untuk perintah bisa menggunakan (LEFT JOIN)

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama, tb_mahasiswa.jenis_kelamin, tb_dosen.nama AS "Dosen"
FROM tb_mahasiswa LEFT JOIN tb_dosen ON tb_dosen.kd_ds = tb_mahasiswa.kd_ds;`

Hasilnya akan seperti ini :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/fa42f349-504a-46d2-a03b-92c4ad3be9aa)

> Note Menampilkan semua data pada table A dan sebagian data pada table B yang bersinggungan dengan table A

## Untuk perintah bisa menggunakan (RIGHT JOIN)

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama, tb_mahasiswa.jk, tb_dosen.nama AS "Dosen" 
FROM tb_mahasiswa 
RIGHT JOIN tb_dosen ON tb_dosen.kd_ds = tb_mahasiswa.kd_ds;`

Hasilnya akan seperti ini :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/4715dc8a-4cf0-4af5-b14b-fb10b5688fe6)

> Note Menampilkan semua data pada table B dan sebagian data pada table A yang bersinggungan dengan table B

# 2 Lakukan join tabel Matakuliah dan Dosen #

## Untuk perintah bisa menggunakan :

`SELECT tb_matakuliah.kd_mk, tb_matakuliah.nama, tb_matakuliah.sks, tb_dosen.nama AS "Dosen Pengampu"
FROM tb_jadwalmengajar
LEFT JOIN tb_matakuliah ON tb_jadwalmengajar.kd_mk = tb_matakuliah.kd_mk
LEFT JOIN tb_dosen ON tb_jadwalmengajar.kd_ds = tb_dosen.kd_ds;`

Hasilnya akan seperti ini :
![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/3543d51c-166d-4f1c-b34f-ec2f7cbccc11)

## Untuk perintah bisa menggunakan :

`SELECT tb_jadwalmengajar.hari, tb_jadwalmengajar.jam, tb_jadwalmengajar.ruang, tb_dosen.nama AS "Dosen Pengampu", tb_jadwalmengajar.kd_mk, tb_matakuliah.nama, tb_matakuliah.sks 
FROM tb_jadwalmengajar 
LEFT JOIN tb_matakuliah ON tb_jadwalmengajar.kd_mk = tb_matakuliah.kd_mk 
LEFT JOIN tb_dosen ON tb_jadwalmengajar.kd_ds = tb_dosen.kd_ds;`

Hasilnya akan seperti ini :

![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/80b5e444-d0b8-4b08-8a3e-a95b3a22b09e)

# 3.Lakukan join tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen #

## Untuk perintah bisa menggunakan :

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama AS "nama", tb_matakuliah.nama AS "Matakuliah", tb_matakuliah.sks, tb_dosen.nama AS "Dosen Pengampu"
FROM tb_krsmahasiswa
JOIN tb_mahasiswa ON tb_krsmahasiswa.nim = tb_mahasiswa.nim
JOIN tb_matakuliah ON tb_krsMahasiswa.kd_mk = tb_matakuliah.kd_mk
JOIN tb_dosen ON tb_krsmahasiswa.kd_ds = tb_dosen.kd_ds;`

Hasilnya akan seperti ini :

![image](https://github.com/Heryantokurnia/Praktikum-5/assets/141998024/861d390b-70e8-4c99-a76d-eda1c5dcc1b3)


> ### Join tabel
>  join tabel merujuk pada penggabungan baris-baris data dari dua atau lebih tabel berdasarkan kolom yang memiliki nilai yang sama di setiap tabel. Join tabel memungkinkan kita untuk menggabungkan data dari tabel yang berbeda untuk menghasilkan hasil yang lebih lengkap dan terkait.

> ### Jenis2
> 1. **INNER JOIN** : Menggabungkan baris-baris data dari dua tabel berdasarkan kondisi join yang ditentukan. Hanya baris yang memiliki nilai yang cocok di kedua tabel yang akan dimasukkan ke dalam hasil join.
>
> 2. **LEFT JOIN** : Menggabungkan semua baris dari tabel kiri (left table) dengan baris yang cocok dari tabel kanan (right table) berdasarkan kondisi join. Jika tidak ada nilai yang cocok dalam tabel kanan, kolom-kolom dari tabel kanan akan memiliki nilai NULL dalam hasil join.
>
> 3. **RIGHT JOIN** : Adalah kebalikan dari LEFT JOIN. Ini menggabungkan semua baris dari tabel kanan dengan baris yang cocok dari tabel kiri berdasarkan kondisi join. Jika tidak ada nilai yang cocok dalam tabel kiri, kolom-kolom dari tabel kiri akan memiliki nilai NULL dalam hasil join.
>
> 4. **FULL JOIN** : Menggabungkan semua baris dari kedua tabel, baik dari tabel kiri maupun tabel kanan, berdasarkan kondisi join. Ini akan menghasilkan semua baris dari kedua tabel, dan jika tidak ada nilai yang cocok dalam salah satu tabel, kolom-kolom yang tidak cocok akan memiliki nilai NULL dalam hasil join.
