# REFLECTION

## 1.2 Understanding how it works
- <a href="https://ibb.co/C7nk0Z0"><img src="https://i.ibb.co/yy8ws1s/Screenshot-2024-05-05-181546.png" alt="Screenshot-2024-05-05-181546" border="0"></a>

fungsi async tidak tergantung pada eksekusi fungsi utama yang memanggilnya. Dikarenakan sifatnya yang asinkron, urutan output dari program dapat berubah. Maka dari itu, Pada saat saya melakukan cargo run, "hey hey" bisa muncul sebelum "howdy!" dan "done!". Ini dikarenakn println!("hey hey"); terletak di luar fungsi async, yang berarti akan dijalankan secara independen dari eksekusi fungsi async.

## 1.3 Multiple Spawn and removing drop

- <a href="https://ibb.co/VqsgpN7"><img src="https://i.ibb.co/QK4Pjc2/Screenshot-2024-05-05-182525.png" alt="Screenshot-2024-05-05-182525" border="0"></a>

Peningkatan jumlah tugas dieksekusi terjadi karena adanya lebih banyak spawner yang menyebabkan penambahan tugas dalam antrian pesan. Ketika spawner dihapus dengan drop(spawner), program dapat terus berjalan tanpa henti karena asumsi adanya transmisi data dari spawner. Fungsi spawn yang dipanggil oleh spawner menghasilkan tugas baru yang dikirimkan ke dalam antrian oleh pengirim tugas. Eksekutor menjalankan satu tugas dari antrian setiap kali dipanggil, sehingga menjalankan tugas-tugas tersebut hingga selesai. Penghapusan spawner dengan drop(spawner) menandakan akhir interaksi, seperti juga ketika semua tugas telah selesai dieksekusi dan spawner di-drop, menandakan bahwa interaksi telah selesai.