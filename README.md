### Module 6

#### Reflection 1

Dalam function handle_connection, BufReader akan menyimpan data reference ke stream terkait. BufReader juga bisa melakukan buffering untuk mengatur calls ketika melakukan pembacaan.

http_request yang merupakan vector of String menyimpan baris2 informasi request yang didapatkan dari browser.

Method lines() pada BufReader akan melakukan split terhadap stream data kemudian dilakukan mapping dari result yang telah unwrapped (karena result bisa saja eror).

Setelah itu, data yang telah diolah di koleksi menjadi Vec<_> dengan collect()

Kemudian, dilakukan formatted print display dari http_request.

#### Reflection 2

![Commit 2 screen capture](/assets/images/commit2.png)

Pada function handle_connection yang telah diperbarui, kita menggunakan fs (filesystem) untuk bisa membaca file yang ada pada `hello.html`. Selain menggunakan status_line sebagai informasi response, length juga digunakan untuk memastikan HTTP Response yang dikirim valid. Kemudian, setiap informasi dari status_line, contents, dan juga length disatukan pada response untuk kemudian dikirim ke browser melalui stream.

#### Reflection 3

![Commit 3 screen capture](/assets/images/commit3.png)

Dalam kode yang telah diperbaiki untuk memvalidasi http_request dari browser user. Saya menghandle agar selain request yang berupa `GET / HTTP/1.1` akan ditolak dan di lempar ke halaman error 404.

Refactor sangat diperlukan karena pada fungsi handle_connection terdapat bloaters berupa method yang terlalu panjang yang merupakan duplikasi. Ini diatasi dengan mendekomposisi conditional yang ada.

#### Reflection 4

Pada kode tersebut, kita mensimulasikan kondisi ketika server yang kita punya mengalami load yang cukup banyak hingga menunda tampilan html selama 5 detik. Hal ini menjelaskan ketika thread utama sedang digunakan (sleep) maka tidak bisa melakukan eksekusi lainnya.

#### Reflection 5

Thread pool adalah sekumpulan thread yang sudah siap dan menunggu untuk menyelesaikan suatu task tertentu. Misalnya ketika program menerima task baru, maka salah satu dari thread yang ada pada pool tersebut akan digunakan untuk menyelesaikannya. Thread yang lainnya tetap bisa menjelankan tugas lain meskipun salah satu thread sedang menjalankan suatu proses tertentu. Jika thread sudah selesai menyelesaikan suatu task, ia akan kembali pada pool dan akan menunggu task selanjutnya.