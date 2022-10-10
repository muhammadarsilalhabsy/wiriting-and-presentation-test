# Rangkuman Week 3

&nbsp;

## Array Multidimensional

> &nbsp;&nbsp;&nbsp;&nbsp;Array pada javascript adalah type data non-primitive yang mampu menampung data yang sama maupun yang berbeda. Array multidimensional adalah array yang bersarang yang artinya ada array didalam array.

#### Mengakses array

> ```js
> // array biasa
> let arrayBiasa = [1, 9.8, 3, "ucup", true, false];
>
> // array multidimensional
> let arrayMulti = [
>   ["andy", 21],
>   ["kucing", 19],
> ];
>
> // mengambil berapa banyak data dalam array
> console.info(arrayBiasa.length);
>
> // mengkases value dari array biasa
> console.info(arrayBiasa[3]); // ucup
>
> // mengakses value dari array multidimensional
> console.info(arrayMulti[0][1]); // 21
> ```

#### Menambahkan Array

> ```js
> // array biasa
> let animals = ["lion", "tiger", "leopard"];
>
> // menambahkan value kedalam array animals (dari belakang)
> animals.push("elephant", "octopus");
>
> console.info(animals); // ["lion", "tiger", "leopard", "elephant", "octopus"]
>
> // menambahkan value kedalam array animals (dari depan)
> animals.upshift("zebra");
>
> console.info(animals); // ["zebra", "lion", "tiger", "leopard", "elephant", "octopus"]
> ```

#### Mengubah Array

> ```js
> let fruits = ["mango", "apple", "orange"];
>
> // mengubah array
> let fruits[1] = "bananas";
>
> console.info(fruits); // ["mango", "bananas", "orange"]
>
> // menambahkan array
> // selain menggunakan method .push() kita juga bisa menambahkan dengan manual
> let fruits[3] = "rambutan";
>
> console.info(fruits); // ["mango", "bananas", "orange", "rambutan"]
>
> ```

#### Menghapus Array

> ```js
> let fruits = ["mango", "apple", "orange"];
> fruits.pop();
>
> console.info(fruits); // ["mango", "apple"]
> ```

#### Looping menggunakan forEach dan Map

> &nbsp;&nbsp;&nbsp;&nbsp;Perbedaan antara forEach dan map yaitu: For Each tugasnya hanya akan ngeprint dari suatu perulangan, sedangkan map mampu mengembalikan suatu value dari perlulangan
>
> ```js
> let fruits = ["mango", "apple", "orange"];
>
> fruits.forEach(function (data, index) {
>   console.info(`${index} is ${data}`);
> });
>
> // argument data akan mengembalikan isi dari array fruits,
> // argument index (opsional) akan mengembalikan index dari array fruits
>
> // output
> // 0 is mango
> // 1 is apple
> // 2 is orange
>
> // implementasi map kurang lebih sama dengan forEach
> fruits.map((d, i) => {
>   console.info(d + " : " + i);
> });
>
> // output
> // 0 is mango
> // 1 is apple
> // 2 is orange
> ```

&nbsp;

## Object

> &nbsp;&nbsp;&nbsp;&nbsp;Object dalam Javascript merupakan tipe data non-primitive, object mampu menyimpan data dari berbagai jenis tipe data yang ada di javascipt contoh Number, String, Boolean bahkan object bisa memiliki value object juga. yang berupa key dan value yang disebut dengan property object. berikut syntax pembuatan object `let namaObj = {keyObj : valueObj}`

#### Membuat dan mengakses object

> ```js
> // membuat object yang serupa pada kehidupan nyata, contoh hewan
> let hewan = {
>   nama: "kucing",
>   umur: 3.5,
> };
>
> console.info(hewan.name); // kucing
> // or
> console.info(hewan["nama"]); // kucing
>
> // object yang sedikit kompleks
> let orang = {
>   nama: "arsil",
>   alamat: ["lr kaliwanggu", "baruga"],
>   sayHi: (friends) => {
>     console.info(`hallo, ${friends}`);
>   },
>   hidup: true,
>   hobby: ["dengar musik", "ngoding", "nonton youtube"],
> };
>
> orang.sayHi("ucup"); // hallo, ucup
>
> // mengakses array didalam object
> console.info(orang.hobby[1]); // ngoding
> ```

#### Mengupdate property object

> ```js
> // value dari object hewan dengan key nama akan diubah menjadi lion
> hewan.nama = "lion";
> // or
> hewan["nama"] = "tiger";
> ```

#### Menghapus property object

> ```js
> // property nama akan hilang pada object hewan
> delete hewan.nama = "lion";
> ```

#### Looping object menggunakan for in

> ```js
> // property nama akan hilang pada object hewan
> const manusia = {
>   name: "ucup",
>   age: 21,
>   status: "jomblo",
> };
>
> // kita dibolehkan memberikan variable const pada object,
> // dan kita diizinkan untuk mengubah ubah value didalamnya,
> // dengan syarat tidak mengubah keseluruhan property pada
> // object yang sudah di set sebelumnya
>
> for (value in manusia) {
>   console.info(value + " => " + manusia[value]);
> }
>
> // output:
>
> // name => ucup
> // age => 21
> // status => jomblo
> ```

&nbsp;

## Modules

> &nbsp;&nbsp;&nbsp;&nbsp;Module System merupakan cara yang bisa dilakukan di javascript untuk menerapkan isolasi kode dari satu file terhadap file lain, serta memudahkan untuk menyertakan kode dari file lain ke dalam file yang membutuhkannya dengan menggunakan key import dan export, semua hal bisa di export oleh key export ini contohnya variable, function, object, array dan lain sebagainya. Untuk menambahkan module pada html harus menambahkan `<script src="main.js" type="modules"></script>`

#### export

> ```js
> // export array, object, dan function
> export let arrFruits = ["Manggo", "Bananas", "Orange"];
> export let human = {
>   name: "ucup",
>   age: 21,
> };
> export function sayHai() {
>   console.info("hallo");
> }
>
> // atau juga bisa setiap vvariable dimasukan kedalam list
> export { arrFruits, human, sayHai };
> ```

#### Import

> ```js
> // export array, object, dan function
> import { arrFruits as buah, human } from "fromFileExport.js";
>
> console.info(buah);
>
> // output:
> // ["Manggo", "Bananas", "Orange"]
> ```

&nbsp;

## Recursive function

> &nbsp;&nbsp;&nbsp;&nbsp;Recursive adalah salah salah satu metode yang digunakan untuk menyelesaikan masalah yang complex dengan cara yang sederhana

#### Recursive vs Looping

> ```js
> // menggunakan looping biasa
> function usingLoop(factorial) {
>   let temp = 1;
>   for (let i = 1; i <= factorial; i++) {
>     temp *= i;
>   }
>   return temp;
> }
>
> // menggunakan recursive function
> function recursiveFactorial(factorial) {
>   // recursive harus memiliki kondisi yang mengakhiri pemanggilan diri sendiri
>   if (factorial == 1) {
>     return 1;
>   } else {
>     return factorial * recursiveFactorial(factorial - 1);
>   }
> }
> ```

&nbsp;

## Asynchronous Javascript

> &nbsp;&nbsp;&nbsp;&nbsp;Sebelum mengetahui apa itu Asynchronous Javascript, kita harus mengetahui bagaimana kode program itu dieksekusi. Defaultnya setiap kode pemrogramman itu di eksekusi atau jalankan secara sequential atau terurut dari atas sampai bawah saling menunggu satu sama lain untuk menunggu giliran dieksekusi, perilaku ini disebut sebagai Synchronous atau Blocking. Sedangkan Asynchronous adalah kebalikan dari Synchronous yang dimana kode program tidak akan saling tunggu menunggu satu sama lain untuk di jalankan, proses ini juga disebut dengan Non-blocking
> JavaScript Asynchronous sendiri terdiri dari 3 bagian:
>
> - callback
> - promise
> - async wait.
> - fetch
>
> > "callback adalah function yang menjadi argument untuk function lain dan akan dieksekusi pada poin tertentu"
>
> berikut pemhaman saya terhadap promise dan callback
>
> ```js
> let gasMobileLegen = new Promise((resolve, reject) =>
>
>   reject("gak dulu deh!");
>   resolve("hayyuuu!");
>   // function resoleve dan reject ini juga bisa disebut callback
>   // yang akan dikirim ke dalam then
> );
> gasMobileLegen.then(result => {
>   console.info(result);
> });
> ```

&nbsp;

## Web Storage

> &nbsp;&nbsp;&nbsp;&nbsp;Web storage adalah salah satu Web API yang dapat menyimpan data secara sementara di lokal komputer pada sisi user. Data yang disimpan di `web storange` akan hilang jika terjadi reload atau pergantian URL pada browser. Penggunaan `web storage` lebih baik dari pada penggunaan Cookie, `web storage` lebih intuitive dibandingkan `cookie`, selain itu juga daya penyimpanannya `web storage` lebih besar dibandingkan `cookie`
>
> Web storage mampu menyimpan
>
> - setting
> - preferensi
> - score
> - posisi video
> - dan lain lain
>
> web storage menyediakan 2 cara untuk menyimpan data ke local dari sisi user:
>
> `window.localStorage` - menyimpan data tanpa ada batasan waktu
> `window.sessionStorage` - menyimpan data sementara di sesi tertentu dan akan berubah ketika berpindah atau di refresh
