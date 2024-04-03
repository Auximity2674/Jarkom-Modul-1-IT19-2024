# Praktikum Jarkom Modul 1 Kelompok IT19

## Anggota kelompok
| Nama | NRP |
|------|-----|
| Hafiz Akmaldi Santosa | 5027221061 |
| Arsyad Rizantha Maulana Salim | 5027221049 |

## Write Up

1. *Creds*
   
   Pada soal ini kami diharuskan untuk menemukan kredensial dari server FTP yang dibuat oleh attacker. Disini kami menggunakan tools Wireshark.
   
   ![Gambar 1](/images/image9.png)
   
   Pertama kami membuka attachment yang diberikan berupa file evidence.pcap dan melakukan pencarian dengan kata kunci FTP melalui `display filter`. Berdasarkan hasil yang didapatkan, kami melihat dari hasil yang didapatkan yang kemungkinan terdapat informasi kredensial yang digunakan untuk login. kami mencoba melakukan follow terhadap salah satu stream dan mendapatkan informasi sebagai berikut:
   
   ![Gambar 2](/images/creds2.png)
   
   Sehingga telah didapatkan kredensial dari server FTP yang dibuat oleh attacker:
   
   Username: `h3ngk3rTzy`
   
   Password: `S!l3ncE`
   
   Kemudian kita memasukan jawaban melalui terminal dengan `ncat 10.15.40.20 10007` untuk mendapatkan flag.

   ![Gambar 3](/images/credsflag.png)

2. *malwleowleo*
   
   Dengan attachment yang sama dengan soal sebelumnya, kami diminta untuk menemukan file malware yang dikirim oleh attacker melalui FTP. Disini kami menggunakan tools filezilla client untuk masuk dengan kredensial attacker dan melakukan transfer file yang dikirim oleh attacker ke laptop kami.

   ![Gambar 4](/images/image11.png)

   Disini kami menemukan 2 file yang dikirimkan oleh attacker yaitu `mirza.jpg` dan `m4L1c10us_W4re.c` sehingga dapat menjawab soal ini dan mendapatkan flag.

   ![Gambar 5](/images/malwleoflag.png)

3. *secret*
   
   Masih dengan attachment yang sama dengan soal sebelumnya, kali ini kami diminta untuk menemukan pesan rahasia dari attacker. Disini kami mencoba membuka salah satu file yang berhasil kami transfer dari attacker yaitu `mirza.jpg`, kemudian didapatkan pesan rahasia sebagai berikut:

   ![Gambar 6](/images/mirza.jpg)

   Sehingga kami dapat memasukan jawaban dan mendapatkan flag.

   ![Gambar 7](/images/mirzaflag.png)

4. *whoami*
   
   Kembali dengan attachment yang sama, kali ini kami diminta untuk menemukan siapa identitas attacker. Kami melihat ke dalam file `m4L1c10us_W4re.c` dan mendapatkan pesan comment yang di-enkripsi.

   ![Gambar 8](/images/mencurigakan.png)

   Kami memasukan pesan yang ter-enkripsi tersebut ke salah satu tools yang digunakan untuk dianalisa jenis enkripsi dan melakukan decode. Kami menggunakan website `www.decode.fr` dan mendapatkan hasil sebagai berikut:

   ![Gambar 9](/images/dekrip.png)

   Didapatkan pesan rahasia yang berhasil di decode yaitu `Hello my name is Paul Atreides`. Sehingga kami mendapatkan jawaban dan flag.

   ![Gambar 10](images/whoamiflag.png)

5. *ATM or ATP or FTP?🤔*

   Sekarang kami diminta untuk menganalisis sebuah server FTP dimana telah terjadi suatu bruteforce login oleh seorang attacker. Kami diberikan sebuah file attachment berupa ftp.pcap lalu kita lakukan display filter FTP server. Kemudian kami mencari stream dimana attacker berhasil login.

   ![Gambar 11](/images/image13.png)

   Didapatkan kredensial login yang digunakan attacker:

   User: `adminJarkom`
   Pass: `m4y_th3_Kn!fe_ch1p_&_sh4tter`

   Sehingga dapat menjawab pertanyaan dan mendapatkan flag.

   ![Gambar 12](/images/ftpflag.png)

6. *How Many packets?*

   Masih dengan attachment yang sama dengan soal sebelumnya, kali ini kita diminta untuk menghitung berapa kali attacker melakukan percobaan bruteforce untuk login. Disini kami menggunakan cara manual yaitu menghitung masing-masing stream dan berapa kali percobaan dalam tiap stream tersebut. Kami menemukan pola sebagai berikut:

   ![Gambar 13](/images/image12.png)
   <center>Pada stream 1-304 terjadi 3 kali percobaan login</center>

   ![Gambar 14](/images/image3.png)
   <center>Pada stream 305-311 terjadi 2 kali percobaan login</center>

   ![Gambar 14](/images/image2.png)
   <center>Pada stream 312-319 terjadi 1 kali percobaan login</center>

   Sehingga didapatkan total percobaan bruteforce login yaitu sebanyak 934 kali. Setelah memasukan jawaban yang benar kami berhasil mendapatkan flag.

   ![Gambar 14](/images/image4.png)

7. *Trace him*

   Kembali dengan attachment yang sama, kali ini kami diminta untuk mencari IP sang attacker. Kami kembali menganalisa packet dimana attacker berhasil login. Pada kolom destination terdapat IP dimana packet terkirim.

   ![Gambar 15](/images/ipattack.png)

   Didapatkan IP attacker yaitu `10.30.3.4` sehingga kami dapat memasukan jawaban tersebut dan mendapatkan flag.
   
   ![Gambar 15](/images/ipattack.png)

8. *Evidence*
