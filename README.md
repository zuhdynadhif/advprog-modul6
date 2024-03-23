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