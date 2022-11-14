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

Jest adalah test runner pada JavaScript yang memungkinkan untuk mengakses DOM melalui jsdom. Untuk setiap pengujian, Umumnya kita me-render ke sebuah elemen DOM yang terhubung dengan document, agar pengujian dapat menerima event DOM. Setelah pengujian selesai, kita harus melakukan "pembersihan". Cara yang umum dilakukan adalah menggunakan pasangan blok beforeEach dan afterEach agar mereka terus berjalan dan memisahkan efek-efek dari sebuah pengujian hanya kepada pengujian tersebut. Install Jest:


                npm i jest --save-dev

Untuk menjalankan tes, tambahkan ini ke package.json:


                "scripts": {
                 "test": "jest"
                }                
  

                
