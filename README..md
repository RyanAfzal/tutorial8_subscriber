# Tutorial 8

### Refleksi 
1. AMQP adalah singkatan dari Advanced Message Queuing Protocol. AMQP adalah desain standar pertukaran pesan (messaging) yang mendukung efisiensi penentuan proses pertukaran pesan (messaging) pada aplikasi atau komunikasi data yang sngat beragam saat ini. 

2. Arti guest:guest@localhost:5672. guest:guest menunjukkan username dan password yang digunakan untuk autentikasi atau lebih tepatnya username dan password di set sebagai guest
localhost:5672 menunjukkan address dan port number dari server, localhost biasanya tertuju untuk local machine atau local computer dan .5672 adalah port default untuk AMQP protocol. jadi guest:guest@localhost:5672 adalah string koneksi untuk sebuah server AMQP.


Screenshot RabbitMQ ketika menjalankan slow simulation subscribers yaitu dengan menggunakan thread dan run publisher berkali-kali. Pada komputer saya jumlah queue adalah 25 karena saya run sebanyak 6 kali maka terjadi queue cargo run sebanyak 5 kali yang setiap cargo mengirimkan 5 pesan.
<img width="949" alt="slow simulation subscribers" src="https://github.com/RyanAfzal/tutorial_8_subscriber/assets/137851158/2292131d-7841-42c3-a3d6-d8364290df5b">
