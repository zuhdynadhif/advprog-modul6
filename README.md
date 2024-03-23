#### Module 6

## Reflection 1

Dalam function handle_connection, BufReader akan menyimpan data reference ke stream terkait. BufReader juga bisa melakukan buffering untuk mengatur calls ketika melakukan pembacaan.

http_request yang merupakan vector of String menyimpan baris2 informasi request yang didapatkan dari browser.

Method lines() pada BufReader akan melakukan split terhadap stream data kemudian dilakukan mapping dari result yang telah unwrapped (karena result bisa saja eror).

Setelah itu, data yang telah diolah di koleksi menjadi Vec<_> dengan collect()

Kemudian, dilakukan formatted print display dari http_request.