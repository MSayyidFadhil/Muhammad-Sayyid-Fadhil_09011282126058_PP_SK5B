Untuk menginstal WordPress menggunakan server web Apache di Ubuntu, Anda dapat mengikuti langkah-langkah berikut:


*Catatan*: Pastikan Anda sudah memiliki server Ubuntu yang diperbarui dan telah masuk sebagai pengguna dengan hak akses superuser (sudo).

# 1. *Instal Apache*:

   Untuk menginstal server web Apache, jalankan perintah berikut:

   bash
   
  ### sudo apt update
   
  ### sudo apt install apache2
   

   Setelah instalasi selesai, aktifkan dan mulai Apache:

   bash
   
  ### sudo systemctl start apache2
   
  ### sudo systemctl enable apache2
   

# 2. *Instal PHP dan Modulnya*:

   Instal PHP dan modul yang diperlukan untuk berjalan bersama Apache:

   bash
   
  ### sudo apt install php libapache2-mod-php php-mysql
   

   Setelah instalasi, pastikan PHP bekerja dengan Apache dengan baik:

   bash
   
  ### sudo systemctl restart apache2
   

# 3. **Instal Database Server (MySQL atau MariaDB)**:

   Anda dapat memilih antara MySQL atau MariaDB sebagai server database. Berikut contoh penggunaan MariaDB:

   Untuk Mysql:

   bash
   
  ### sudo apt install mysql-server
   

   Setelah instalasi selesai, amankan instalasi MariaDB:

   bash
   
  ### sudo mysql_secure_installation
   

# 4. *Buat Database dan Pengguna Database*:

   Log masuk ke MariaDB sebagai root:

   bash

   ### sudo mysql
   

   Buat database baru dan pengguna database untuk WordPress. Gantilah nama_database, nama_pengguna, dan password_pengguna sesuai kebutuhan Anda:

![image](https://github.com/MSayyidFadhil/Muhammad-Sayyid-Fadhil_09011282126058_PP_SK5B/assets/118714480/d0c171cd-6640-412f-b3ac-3d3200c2fec2)

# 5. *Instal WordPress*:

   Unduh dan ekstrak arsip WordPress ke direktori web root. Gantilah nama_folder dengan nama folder yang Anda inginkan:

   bash
   
  ### cd /var/www/html
   
  ### sudo wget https://wordpress.org/latest.tar.gz
   
  ### sudo tar -xzvf latest.tar.gz
   
  ### sudo mv wordpress nama_folder
   

# 6. *Konfigurasi WordPress*:

   Buat salinan file konfigurasi WordPress:

   bash
   
 ### sudo cp /var/www/html/nama_folder/wp-config-sample.php /var/www/html/nama_folder/wp-config.php
   

   Selanjutnya, edit file wp-config.php:

   bash
   
  ### sudo nano /var/www/html/nama_folder/wp-config.php
   

   Ganti konfigurasi database dengan informasi yang sesuai yang telah Anda buat sebelumnya:

   ![image](https://github.com/MSayyidFadhil/Muhammad-Sayyid-Fadhil_09011282126058_PP_SK5B/assets/118714480/25ea3165-b6ed-450a-937a-e5d9c27391f4)

   Simpan dan keluar dari editor teks.

# 7. *Setel Hak Akses*:

   Pastikan Apache memiliki hak akses yang tepat ke folder WordPress:

   bash
   
  ### sudo chown -R www-data:www-data /var/www/html/nama_folder
   

# 8. *Konfigurasi Web Server*:

   Buat konfigurasi server web Apache untuk mengarahkan permintaan ke WordPress. Buat file konfigurasi baru:

   bash
   
  ### sudo nano /etc/apache2/sites-available/nama_domain.conf
   

   Isi konfigurasi server web:

   ![image](https://github.com/MSayyidFadhil/Muhammad-Sayyid-Fadhil_09011282126058_PP_SK5B/assets/118714480/403e61df-f4b5-4e5b-9bc0-42175e788b6b)

   Simpan dan keluar dari editor teks.

# 9. *Aktifkan Konfigurasi dan Restart Apache*:

   Aktifkan konfigurasi situs dan restart Apache:

   bash
   
  ### sudo a2ensite nama_domain.conf
  
  ### sudo systemctl restart apache2
   

# 10. *Selesaikan Instalasi WordPress*:

Buka web browser Anda dan akses alamat domain atau alamat IP server Ubuntu Anda. Anda akan diarahkan ke halaman penginstalan WordPress. Ikuti petunjuk yang muncul di layar Anda untuk menyelesaikan penginstalan WordPress, termasuk pengaturan bahasa, informasi database, dan akun administrator.

Sekarang Anda sudah menginstal WordPress menggunakan server web Apache di server Ubuntu Anda. Selamat menggunakan!
