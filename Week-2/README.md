<div style="text-align: center"><h1>Rangkuman Week 2</h1></div>
<!-- ========================Bagian CLI======================== -->
&nbsp;

## Scope And Function

> &nbsp;&nbsp;&nbsp;&nbsp;Scope adalah batasan atau area akses sebuah data. JavaScript memiliki 2 (dua) buah akses scope yaitu local dan global scope. Data yang ada di global scope dapat dengan mudah diakses oleh local scope, sedangakan local scope sebaliknya data dari local scope tidak bisa diakses oleh global scope. scope biasanya digunakan pada sebuah function dengan tanda kurung kribo.
>
> &nbsp;&nbsp;&nbsp;&nbsp;Function adalah block code yang bertugas dengan tujuan tertentu dan akan berjalan saat kita memanggilnya
>
> Contoh penggunaan scope pada function:
>
> ```
> function namaFunction() {
>   // kode
> }
> ```
>
> Contoh function mendapatkan keliling persegi dan luas persegi panjang
>
> ```js
> function luasPersegi(panjang, lebar) {
>   return panjang * lebar;
> }
>
> function kelilingPersegi(panjang, lebar) {
>   return (panjang + lebar) * 2;
> }
> ```
