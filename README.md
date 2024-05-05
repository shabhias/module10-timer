# REFLECTION

## 1.2 Understanding how it works
- <a href="https://ibb.co/C7nk0Z0"><img src="https://i.ibb.co/yy8ws1s/Screenshot-2024-05-05-181546.png" alt="Screenshot-2024-05-05-181546" border="0"></a>

fungsi async tidak tergantung pada eksekusi fungsi utama yang memanggilnya. Dikarenakan sifatnya yang asinkron, urutan output dari program dapat berubah. Maka dari itu, Pada saat saya melakukan cargo run, "hey hey" bisa muncul sebelum "howdy!" dan "done!". Ini dikarenakn println!("hey hey"); terletak di luar fungsi async, yang berarti akan dijalankan secara independen dari eksekusi fungsi async.

