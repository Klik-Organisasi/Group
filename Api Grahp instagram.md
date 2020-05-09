

API Graf
Sinopsis
Menggunakan API Graf
PERTANYAAN UMUM
Reference
Webhooks
Memulai
Sample Apps
Subscriptions Edge
Reference
Lanjutan
Catatan Perubahan
Server-Sent Events
Di Halaman Ini
Webhooks
Dengan webhook, Anda dapat menerima notifikasi HTTP perubahan objek tertentu di Graf Sosial Facebook secara realtime. Misalnya, kami dapat mengirimi Anda notifikasi saat ada pengguna aplikasi Anda mengganti alamat emailnya atau setiap kali dia mengomentari Halaman Facebook Anda. Hal ini mencegah Anda untuk tidak harus mengkueri API Graf untuk perubahan terhadap obyek yang telah atau tidak terjadi, dan membantu Anda menghindari mencapai batas nilai Anda.

Webhook untuk Pembayaran dan Webhook untuk Messenger memiliki langkah konfigurasi yang sedikit berbeda. Kalau Anda menyiapkan Webhook untuk salah satu produk tersebut, baca dokumen masing-masing untuk petunjuk penyiapan.

Objek, Kolom, dan Nilai
Terdapat banyak jenis objek di Graf Sosial Facebook, misalnya objek Pengguna dan objek Halaman, jadi setiap kali Anda mengonfigurasi Webhook, Anda harus memilih jenis objek terlebih dahulu. Karena objek yang berbeda memiliki kolom yang berbeda pula, maka Anda harus berlangganan ke kolom tertentu untuk jenis objek itu. Tiap kali ada perubahan nilai sembarang kolom objek yang Anda telah berlangganan, kami akan mengirimkan notifikasi ke Anda.

Notifikasi dikirimkan ke Anda sebagai permintaan HTTP POST dan berisi payload JSON yang menjelaskan perubahan itu. Misalnya saja, Anda menyiapkan Webhook User dan berlangganan kolom Photos. Kalau salah satu Pengguna aplikasi Anda mengunggah foto, kami akan mengirimi Anda notifikasi seperti ini:

Contoh Notifikasi
{
  "entry": [
    {
      "time": 1520383571,
      "changes": [
        {
          "field": "photos",
          "value": {
            "verb": "update",
            "object_id": "10211885744794461"
          }
        }
      ],
      "id": "10210299214172187",
      "uid": "10210299214172187"
    }
  ],
  "object": "user"
}
Server HTTPS
Webhooks dikirim menggunakan HTTPS, sehingga server Anda harus dapat menerima dan memproses permintaan HTTPS, dan harus diinstali sertifikat TLS/SSL yang valid. Sertifikat yang ditandatangani sendiri tidak didukung.

Tinjauan Aplikasi
Webhooks tidak memerlukan Tinjauan Aplikasi. Akan tetapi, untuk menerima notifikasi Webhooks tentang perubahan pada objek saat aplikasi Anda dalam mode Tayang, aplikasi Anda harus sudah diberi izin yang relevan untuk mengakses objek-objek itu. Lihat Izin di bawah ini.

Izin
Pada umumnya, sebelum suatu aplikasi dapat dipublikasikan, aplikasi tersebut harus melalui Tinjauan Aplikasi. Saat peninjauan, aplikasi dapat meminta persetujuan untuk izin tertentu yang mengontrol jenis data yang dapat diakses oleh aplikasi saat menggunakan API Graf.

Meskipun produk Webhook tidak memerlukan Tinjauan Aplikasi, produk tersebut masih diatur oleh izin. Artinya, meskipun Anda menyiapkan Webhook dan berlangganan kolom tertentu pada sebuah jenis objek, Anda tidak akan menerima notifikasi mengenai perubahan apa pun pada objek dengan jenis tersebut, kecuali:

aplikasi Anda telah disetujui untuk izin yang sesuai dengan jenis data tersebut, dan
objek pemilik data telah memberi izin kepada aplikasi Anda untuk mengakses data tersebut (mis. seorang Pengguna mengizinkan aplikasi Anda untuk mengakses feed-nya)
Mode Pengembangan
Aplikasi dalam mode pengembangan tidak akan menerima notifikasi webhook secara langsung. Selama sebuah aplikasi dalam mode pengembangan, hanya notifikasi pengujian yang dipicu melalui dasbor aplikasi yang akan dikirim.

Harap diingat bahwa perilaku mode pengembangan berbeda untuk Peristiwa Webhooks Messenger. Buka dokumen Webhooks untuk Messenger untuk perinciannya.

Penyiapan
Untuk menggunakan Webhook, Anda harus menyiapkan endpoint di server aman (HTTPS), lalu tambahkan dan konfigurasikan produk Webhook di dasbor aplikasi Anda. Sisa isi dokumen ini menjelaskan cara menyelesaikan kedua langkah ini.

Sudah siap? Mari mulai!


BAHASA

Bahasa IndonesiaEnglish (US)العربية中文(简体)EspañolFrançais (France)日本語한국어Português (Brasil)Deutsch
Produk

Artificial Intelligence
Augmented Reality
Fitur Bisnis
Gaming
Sumber Terbuka
Penerbitan
Integrasi Sosial
Virtual Reality
Program

Developer Circles
F8
Program Perusahaan Rintisan
ThreatExchange
Dukungan

Dukungan Developer
Bug
Status Platform
Grup Komunitas Facebook for Developers
Berita

Blog
Kisah Sukses
Video
Halaman Facebook for Developers
Ikuti kami

Ikuti kami di FacebookIkuti kami di InstagramIkuti kami di TwitterIkuti kami di LinkedInIkuti kami YouTube
Tentang
Buat Iklan
Karier
Kebijakan Platform
Kebijakan Privasi
Cookie
Ketentuan
Facebook © 2020
Apakah dokumen ini membantu ?
YaYa, tapi...Tidak
Hapus
