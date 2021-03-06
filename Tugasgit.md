# Tugasgit1

git config --global user.name "Eva Roliza"

git config --global user.email "evaroliza@gmail.com"




Perintah ADD dan COMMIT: Perubahan yang diajukan atau file tambahan akan ditambahkan ke index dengan menggunakan perintah add. Untuk menambahkan file, perintah sederhananya adalah:
git add <file_name>
Jika Anda cukup yakin untuk melakukan perubahan langsung di HEAD, Anda langsung gunakan perintah commit. Contohnya:

git commit –m “Tambahkan catatan untuk commit Anda”
Catatan: Bila perintah commit telah dijalankan (dari direktori kerja), file akan di-commit ke HEAD, namun belum terkirim ke remote repository.

Mengirim perubahan: Setelah Anda melakukan commit perubahan (dan sudah yakin siap dikirim ke repository asli), Anda bisa menggunakan perintah push.Setelah git push origin master dijalankan dari direktori kerja, perubahan yang ada di HEAD akan dikirim ke remote repository. Seperti yang telah disebutkan sebelumnya, master bisa diganti  menjadi nama branch dimana perubahan ingin Anda commit.Jika repository yang ada saat ini belum di-clone dan Anda ingin membuat sambungan antara repository dan remote server, maka jalankanlah perintah ini:
git remote add origin <server>
Catatan: Ganti <server> dengan alamat remote server.

Setelah di-clone, perubahan yang telah dibuat akan dikirim ke server.

Branches: Fitur keren lainnya dari GIT adalah kemampuannya untuk memungkinkan developer dan project manager untuk membuat branch independen yang berbeda dalam 1 project. Tujuan utama branch adalah untuk membuat fitur namun tetap mengisolasinya dari yang lain. Branche default di project adalah master branch. Karena banyak branch yang dibutuhkan bisa dibuat dan digabungkan dengan master branch.Branch baru bisa dibuat dengan menggunakan perintah berikut ini:
git checkout -b feature_n *
Catatan: feature_n adalah nama branch-nya.

Jika Anda ingin kembali ke master branch utama, jalankan perintah ini:

git checkout master
Branch bisa dihapus dengan menggunakan perintah ini:

git checkout -b feature_n
Untuk membuat branch bisa digunakan oleh pengguna lain, Anda harus mengirimkannya ke remote repository melalui perintah ini:

git push origin feature_n
Update & Merging: Jika Anda ingin meng-update direktori kerja lokal Anda saat ini ke yang paling baru dari remote repository, jalankan perintah git pull.Untuk menggabungkan branch lain ke yang sudah aktif, gunakan:
git merge feature_n
Jika Anda melakukan pull atau merge, GIT akan selalu mencoba menangani conflict  sendiri, namun kadang-kadang juga gagal. Jika terjadi kegagalan karena conflict, maka pengguna harus melakukan resolve conflict secara manual. Setelah Anda meng-edit file (untuk menghapus conflict), tandai sebagai merged dengan perintah:

git add <nama_file>
Jika setelah merging Anda ingin melihat perubahan, jalan perintah:

git diff <nama_sumber_branch> <nama_target_branch>
Tagging: Sebelum merilis update/perubahan apapun, sangat disarankan untuk membuat tag. Untuk melakukannya di GIT, gunakan perintah:
git tag 1.1.0 1c2d2d56fa
1c2d2d56fa adalah perintah yang terkait dengan 10 karakter pertama dari commit-id, yang dijadikan sebagai tag. Commit ID bisa ditemukan di log.

Log: Catatan history dari repository bisa dipelajari dari log. Perintah git log yang menampilkannya. Untuk menampilkan commit yang dibuat oleh seorang pengguna, Anda bisa menggunakan perintah:
git log --author =Bambang
Log yang terkompresi (1 commit per baris) bisa dilihat dengan:

git log --pretty=oneline
Untuk hanya melihat file yang berubah:

git log --name-status
 

Mengganti perubahan di lokal: Jika Anda tidak sengaja membuat kesalahan dan ingin kembali ke perubahan normal yang sebelumnya, gunakan perintah:

git checkout -- <filename>
Dengan melakukan hal tersebut, akan mengganti perubahan di direktori kerja dengan yang terakhir ada di HEAD. Perubahan apapun yang ditambahkan ke index tidak akan terkena dampak.

Sebaliknya, jika semua perubahan/commit di-drop dan master branch lokal dibutuhkan untuk menunjukkan history terakhir dari server, jalankan perintah:

git fetch origin

git reset --hard origin/master
