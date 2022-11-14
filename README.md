# writing-week3-frontend-bootcamp

# React-Context

Context merupakan sebuah cara untuk membuat global state yang nanti bisa digunakan di semua level komponen tanpa harus mengirim props ke lower level component secara manual. Context ini merupakan alternatif dari props drilling, props drilling sendiri adalah cara mempassing props dari grandparent ke parent ke child ke grandchild dan seterusnya, Context adalah state management built in React.

![context](https://storage.googleapis.com/kotakode-prod-public/images/cfe2535c-4002-49d7-8f9f-3a8921a0f0a4-Context-API-vs-Props-Drilling.png)

Pada Context, state dapat dikirim dari root component(App) langsung ke component D. Sebaliknya, pada metode Props Drilling, state dikirimkan via props secara bertahap dari root component menuju component A, C dan barulah sampai di component D. Context memiliki Provider dan Consumer. Provider dan Consumer merupakan property dari object context API. Provider sendiri berfungsi sebagai tempat menampung value sedangkan Consumer berfungsi untuk menggunakan nilai dari value tersebut.
1. Membuat context

        const Context = createContext(MockData);

2. Membuat Provider pada context

        const Parent = () => {
             return (
                <Context.Provider value={initialValue}>
                <Children/>
                </Context.Provider>
            )
        }

3. Mengimpor context


        import { createContext } from "react"

### Perbedaan Redux dan Context

Untuk state management dalam react, dalam arti secara keseluruhan, tidak ada hal yang benar benar berbeda antara Redux dengan Context. Satu hal yang mungkin berbeda adalah Context merupakan state management built in React, sedangkan Redux adalah third party library yang dapat digunakan dengan React. Akan tetapi, kedua hal tersebut (Context dan Redux) mempunyai tujuan yang sama, yaitu untuk mengatur state management. 


# React-Testing

Adalah seperangkat helpers yang memungkinkan Anda mengetes komponen pada React tanpa bergantung pada detail implementasinya. Ada banyak jenis testing yang terbagi dalam tiga kategori utama yaitu :

1. unit testing
2. integration testing
3. UI testing

Berikut adalah tampilan alur pengujian/testing :

1. impor fungsi untuk menguji
2. berikan masukan ke fungsi
3. tentukan apa yang diharapkan sebagai output
4. periksa apakah fungsi menghasilkan output yang diharapkan

 Alasan unit testing itu penting :
 
1. Membantu memperbaiki bug di awal pada siklus software development dan menghemat biaya
2. Membantu developer untuk memahami basis kode dan memungkinkan mereka membuat perubahan dengan cepat
3. Berfungsi sebagai dokumentasi proyek
4. Membantu reusability code pada projek baru

Unit testing memiliki tiga teknik yang disebut black box testing, white box testing dan gray box testing.

Black box testing adalah sebuah pengujian yang tidak perlu melihat dan memahami suatu software lebih dalam, pengujiannya melalui user interface, input dan output

2. White Box Testing

White box testing bersifat transparan jadi kita bisa melihat suatu sistem dari awal sampai akhir untuk dilakukan testing. Untuk testingnya dilakukan untuk menguji struktur internal, desain, fungsi dan detail implementasi dari sebuah aplikasi

3. Grey Box Testing

Grey box testing ini merupakan sebuah perpaduan antara black box testing dan white box testing. Pengujiannya ini digunakan untuk eksekusi test, resiko dan metode penilaian

Jest adalah test runner pada JavaScript yang memungkinkan untuk mengakses DOM melalui jsdom. Untuk setiap pengujian, Umumnya kita me-render ke sebuah elemen DOM yang terhubung dengan document, agar pengujian dapat menerima event DOM. Setelah pengujian selesai, kita harus melakukan "pembersihan". Cara yang umum dilakukan adalah menggunakan pasangan blok beforeEach dan afterEach agar mereka terus berjalan dan memisahkan efek-efek dari sebuah pengujian hanya kepada pengujian tersebut. Install Jest:


                npm i jest --save-dev

Untuk menjalankan tes, tambahkan ini ke package.json:


                "scripts": {
                 "test": "jest"
                }                
                
 ### Menggunakan Test Coverage
 
Pada sebuah proyek, ada baiknya kita melakukan sebuah testing terhadap semua komponen yang kita buat. Hal ini bertujuan untuk memastikan bahwa setiap komponen berfungsi semestinya. Namun terkadang kita lupa untuk membuat test untuk suatu komponen. Disinilah peran Test Coverage sangat berarti. Test Coverage berfungsi untuk melihat komponen mana saja yang sudah memiliki test dan komponen yang belum memiliki test. Untuk menjalankan test ini kita hanya perlu mengetikan perintah npm test — -coverage pada terminal, dan akan muncul daftar komponen mana saja yang sudah dan belum memiliki test. Berikut contoh hasil dari perintah npm test — -coverage.

### Fungsi Mock Dengan Menggunakan Jest

Seperti artinya kita akan membuat tiruan/mock dari suatu fungsi dan membuat balikannya secara manual, sehingga tidak peduli apakah fungsi tersebut bekerja, fungsi akan mengembalikan nilai sesuai yang kita definisikan. Kita akan mencoba membuat mock dari fungsi fungsiTambah yang kita buat sebelumnya. 

### Snapshot Testing

Snapshot testing merupakan fitur pada Jest yang memungkinkan kita membandingkan hasil render dari suatu komponen. Hasil render ini akan dibaca dalam bentuk JSON kedalam suatu file tersendiri yang secara otomatis akan terbentuk saat kita menjalankan snapshot testing. 

                
