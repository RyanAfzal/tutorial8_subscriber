# Tutorial 8

### Refleksi 
1. AMQP adalah singkatan dari Advanced Message Queuing Protocol. AMQP adalah desain standar pertukaran pesan (messaging) yang mendukung efisiensi penentuan proses pertukaran pesan (messaging) pada aplikasi atau komunikasi data yang sngat beragam saat ini. 

2. Arti guest:guest@localhost:5672. guest:guest menunjukkan username dan password yang digunakan untuk autentikasi atau lebih tepatnya username dan password di set sebagai guest
localhost:5672 menunjukkan address dan port number dari server, localhost biasanya tertuju untuk local machine atau local computer dan .5672 adalah port default untuk AMQP protocol. jadi guest:guest@localhost:5672 adalah string koneksi untuk sebuah server AMQP.


Screenshot RabbitMQ ketika menjalankan slow simulation subscribers yaitu dengan menggunakan thread dan run publisher berkali-kali. Pada komputer saya jumlah queue adalah 25 karena saya run sebanyak 6 kali maka terjadi queue cargo run sebanyak 5 kali yang setiap cargo mengirimkan 5 pesan.
<img width="949" alt="slow simulation subscribers" src="https://github.com/RyanAfzal/tutorial_8_subscriber/assets/137851158/2292131d-7841-42c3-a3d6-d8364290df5b">

Screenshot RabbitMQ ketika menjalankan publisher sebanyak 4 kali dengan cargo run, tetapi kali ini subscribers dipisah pada 3 console. Dan spike berkurang artinya proses message lebih cepat karena request yang diterima queue dipisah pada 3 subscribers.
<img width="941" alt="run 3 subscribers" src="https://github.com/RyanAfzal/tutorial_8_subscriber/assets/137851158/05d007ea-7923-4709-a97c-89995e2db0a7"> <br>
<img width="663" alt="ss publisher untuk run 3 subscribers" src="https://github.com/RyanAfzal/tutorial_8_subscriber/assets/137851158/d341479b-093d-47d7-8629-120da9cd2d7e"> <br>
<img width="663" alt="ss subscriber pertama (3 subs)" src="https://github.com/RyanAfzal/tutorial_8_subscriber/assets/137851158/67b638aa-c9cc-42f1-b181-74a493d27aaa"> <br>
<img width="664" alt="ss subscriber kedua (3 subs)" src="https://github.com/RyanAfzal/tutorial_8_subscriber/assets/137851158/abd9cb92-4017-4f0d-8ee4-d4b01253cb85"> <br>
<img width="662" alt="ss subscriber ketiga (3 subs)" src="https://github.com/RyanAfzal/tutorial_8_subscriber/assets/137851158/871d801e-8b49-4eda-a729-90e3697e26fc"> <br>

Pada code publisher dan subscriber yang harus diimprove adalah 
1. <code>unwrap()</code> karena dapat menyebabkan program panic jika Result adalah Err. Dapat diganti dengan menggunakan <code>match</code> atau <code>if let</code>. <br>
2. Gunakan konstanta untuk string yang diulang karena jika kita memiliki string yang digunakan beberapa kali (seperti <code>amqp://guest:guest@localhost:5672</code>) akan membuat code kurang estetik dan lebih sulit dipahami, lebih baik mendefinisikannya sebagai konstanta di bagian atas file.




