# laporan-tugas-UTS-adj-191402066

Nama	: Mhd. Arsya Fikri
NIM	: 191402066
Kom	: C

Laporan penggunaan GNS3 untuk simulasi pada jaringan komputer.

**Connect GNS3 to the Internet (local server)**
https://docs.gns3.com/docs/using-gns3/advanced/connect-gns3-internet/
Berikut adalah langkah-langkah pengerjaannya.
1.	Buka GNS3 dan buat sebuah project baru

![image](https://user-images.githubusercontent.com/62231022/138552215-4fcd9e93-7d8c-42b0-9aa5-df3a3ff1b693.png)

2.	Buka Routers pada Devices Toolbars, dan drag and drop dua buah Router (R1 dan R2) ke dalam workspace.

![image](https://user-images.githubusercontent.com/62231022/138552217-e492fb1e-7db1-4cdf-89d0-eb2879d2c142.png)

3.	Masih pada bagian device toolbars, buka bagian end devices dan drag and drop sebuah cloud (cloud1). Dan apabila muncul pilihan server pilih pada server lokal (PC).

![image](https://user-images.githubusercontent.com/62231022/138552220-39420b1e-94bf-4847-b7eb-827e7c42bc3c.png)

4.	Sebelum memulai, konfigurasi memori dan disk R1 dengan cara klik kanan pada R1, pilih tab Memories and Disk, kemudian atur seperti berikut.

![image](https://user-images.githubusercontent.com/62231022/138552227-e8331039-e4ae-429b-8aaf-1697fdee5c01.png

5.	Pada device toolbars klik menu Add a link dan hubungkan ketiga node tadi dengan konfigurasi sebagai berikut.

![image](https://user-images.githubusercontent.com/62231022/138552232-628714a4-036c-4463-bf70-f7db0a7aa1e7.png)

Koneksi antara interface f0/0 pada R1 dan Ethernet 4 pada Cloud1 dipilih berdasarkan penggunaan jaringan internet pada pc. Saya menggunakan koneksi Ethernet 4.

6.	Selanjutnya, klik start all nodes untuk memulai semua devices.

![image](https://user-images.githubusercontent.com/62231022/138552236-2ca9336c-ea6f-4824-9a14-ff9404af9596.png)

7.	Selanjutnya kita akan melakukan konfigurasi pada R1 terlebih dahulu. Klik kanan pada R1 lalu pilih console.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552240-7217c443-1fad-4e99-97bd-c9ca6cfda183.png)

8.	Konfigurasikan R1 dengan sebuah IP Address yang masih satu subnet dengan koneksi internet PC. Berikut adalah konfigurasi-nya.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552243-9a66b660-2005-4e84-bfd5-ae0b0f3fab24.png)

Konfigurasi sebuah default gateway-nya (sesuai dengan default gateway jaringan yang digunakan pada PC (dalam kasus ini adalah Ethernet 4)).
 
 ![image](https://user-images.githubusercontent.com/62231022/138552249-106d5286-0e38-4602-a934-96a1503b8ccc.png)

9.	Kemudian ping default gateway tadi.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552255-5687ea0e-d231-44d3-8987-9fee288f2673.png)

Hasilnya adalah ping seharunya berhasil.

10.	Pastikan router terkonfigurasi pada DNS server yang benar.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552258-74dfb6e1-b004-4286-acbe-db102786e462.png)

11.	Ping google.com
 
 ![image](https://user-images.githubusercontent.com/62231022/138552260-72643c1d-761c-493e-8153-648e65d8ef5d.png)

Hasilnya adalah ping berhasil.

12.	Kemudian, kita konfigurasikan seluruh jaringan pada GNS3 Workspace kita.
Konfigurasi pada router:
R1:
 
 ![image](https://user-images.githubusercontent.com/62231022/138552264-45a54e44-926b-4a3a-b22f-8a9c2b4d53a4.png)

R2:
 
 ![image](https://user-images.githubusercontent.com/62231022/138552265-8dc6ae16-1464-4a3a-8927-69923d952e30.png)

13.	Konfigurasikan OSPF pada R1 dan R2 dan menyatakan default route.
R1:
 
 ![image](https://user-images.githubusercontent.com/62231022/138552266-6b187ed1-354c-4209-bc7b-64cc47fbfe6e.png)

R2:
 
 ![image](https://user-images.githubusercontent.com/62231022/138552268-fac0e37c-ced9-4016-8099-9cfe5a57cbe9.png)

14.	Konfigurasikan pengaturan DNS pada R2
 
 ![image](https://user-images.githubusercontent.com/62231022/138552270-c7b48d95-971e-47d6-b239-afb6a0e89018.png)

15.	Mengkonfigurasikan NAT pada R1 agar R2 dapat melakukan ping ke internet.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552271-0fa02072-e72f-4631-aca0-d371b7043335.png)

16.	Uji coba konektivitas R2 ke internet.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552276-d5590f24-0142-44bd-afd9-c3b3505d162e.png)

17.	Berhasil mengkonfigurasikan konektivitas internet dari GNS3.




**The NAT node**
https://docs.gns3.com/docs/using-gns3/advanced/the-nat-node/
Untuk langkah-langkah tutorial simulasi jaringan pada GNS3 yang kedua adalah sebagai berikut.
1.	Buka GNS3 dan buatlah sebuah project baru.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552297-f5dc9b91-7635-4eef-bfe0-b59a91000d13.png)

2.	Pada device toolbars, buka kategori end devices dan drag and drop NAT node ke workstation. Untuk servernya sendiri kita pilih GNS3 VM.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552300-19bf5cad-481a-4fc7-a63e-b8708ee4f772.png)

3.	Untuk selanjutnya kita drag and drop webterm docker container pada workstation. Apabila tidak ditemukan webterm, maka dilakukan import terlebih dahulu pada webterm yang didapat dari GNS3 marketplace.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552302-8648bd9b-31cf-4da2-ac54-95595fe419d6.png)

4.	Kemudian kita juga memasukkan Ethernet Switch ke dalam workstation dan pilih server pada GNS3 VM.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552304-f1af0ef4-8672-4a0a-8ad3-784c6a4aa913.png)

5.	Hubungkan semua node dengan topologi seperti berikut.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552308-c7977a7c-61e7-4361-b95c-d20a5f4781a0.png)

6.	Ada dua pilihan pada node webterm yang dapat kita lakukan. Yaitu menggunakan DHCP atau konfigurasikan static IP ke webterm. Caranya adalah klik kanan pada node webterm pada keadaan mati dan pilih Edit Config. Nah, selanjutnya kita akan coba menghidupkan DHCP.

7.	Untuk menghidupkan DHCP uncomment dua baris paling akhir dengan cara menghapus tanda pagar. Kemudian klik Save.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552309-b6697c30-b73c-43e5-809f-2e4f7a903167.png)

8.	Kemudian, start seluruh node dan pada node webterm klik kanan, dan pilih Console maka akan membuka sebuah VNC window. Klik pada tombol restore dan pada bagian hitam klik kiri, kemudian pilih “Terminal”.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552311-02f0e596-4906-42c1-b204-fb3bd4f522b1.png)

9.	Pada terminal, ketik perintah ‘ifconfig’ yang akan menampilkan DHCP yang berjalan pada node NAT yang memberikan webterm address 192.168.122.13.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552315-ab9cf62b-5c21-489b-aa43-e08b8742f146.png)

10.	Balik ke browser, lalu coba buka sebuah url.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552317-364333e1-ffee-4db8-87cd-99dd35aedb5c.png)

11.	Untuk selanjutnya kita akan mencoba untuk meng-assign sebuah IP address pada webterm. Caranya masih sama, buka “Edit Config” pada node webterm yang sedang berhenti.

12.	Comment pada dua baris di bawah yang kita uncomment sebelumnya, dan uncomment pada Static IP section seperti berikut. Kemudian Save.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552319-0a7b5f78-6f78-448e-8f57-cda94acda333.png)

13.	Start node container lagi, kemudian buka console. Masih dengan cara yang sama, pada terminal ketikkan command ‘ifconfig’.
 
 ![image](https://user-images.githubusercontent.com/62231022/138552328-98d4908c-eab4-4d8e-a821-d1255071663d.png)

Nah, pada terminal kita dapat melihat IP Address yang kita assignt ke node webterm.

14.	Kembali ke Firefox, maka buka kembali sebuah url.

![image](https://user-images.githubusercontent.com/62231022/138552331-e0651d2a-9bbc-4531-8b48-1549676cbb6e.png)
