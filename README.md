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

1. Context 

- 

# React-Testing
