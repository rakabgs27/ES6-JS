# 01 - let

# Apa itu "let" di JavaScript

Di JavaScript, let adalah kata kunci yang digunakan untuk mendeklarasikan variabel dengan lingkup blok. Ketika Anda menggunakan let untuk mendeklarasikan variabel, variabel tersebut hanya dapat diakses di dalam blok di mana variabel tersebut dideklarasikan. Sebuah blok adalah setiap rangkaian pernyataan yang terdapat dalam kurung kurawal {}. Berikut adalah contohnya:
```
function foo() {
    let x = 10; // x hanya dapat diakses dalam blok ini
    if (true) {
        let y = 20; // y hanya dapat diakses dalam blok ini
        console.log(x); // 10
        console.log(y); // 20
    }
    console.log(x); // 10
    console.log(y); // ReferenceError: y tidak didefinisikan
}
    foo();
```    
Pada contoh ini, variabel x dideklarasikan dengan let di dalam blok fungsi dan dapat diakses dalam seluruh fungsi. Variabel y juga dideklarasikan dengan let, tetapi di dalam blok if, sehingga hanya dapat diakses dalam blok tersebut. Jika Anda mencoba mengakses y di luar blok di mana variabel itu dideklarasikan, maka akan muncul ReferenceError.

# Bagaimana cara menggunakan Let yang benar?
Untuk menggunakan let dengan benar di JavaScript, ikuti langkah-langkah berikut:

1. Deklarasikan variabel dengan kata kunci let, diikuti dengan nama variabel yang diinginkan, dan berikan nilai awal jika diperlukan. "let myVariable = 10;"
2. Gunakan variabel tersebut sesuai kebutuhan di dalam blok yang sesuai. Pastikan untuk menghindari penggunaan variabel yang sama di luar blok.
```
function myFunction() {
    let myVariable = 20;
    console.log(myVariable); // Output: 20
}
```
3.Jangan mendeklarasikan variabel yang sama dengan nama yang sama di dalam blok yang sama atau blok yang lebih dalam.
```
function myFunction() {
    let myVariable = 20;
    if (true) {
        let myVariable = 30; // Ini merupakan variabel yang berbeda dari yang di atas.
        console.log(myVariable); // Output: 30
    }
    console.log(myVariable); // Output: 20
}
```
4.Hindari penggunaan variabel tanpa deklarasi atau variabel yang dideklarasikan dengan let yang sama di dalam blok.
```
function myFunction() {
    myVariable = 20; // Ini akan membuat variabel global, hindari penggunaan variabel tanpa deklarasi.
    let myVariable = 30; // Ini akan menghasilkan ReferenceError, hindari penggunaan variabel yang sama di dalam blok.
}
```
Dengan mengikuti langkah-langkah di atas, Anda dapat menggunakan let dengan benar di JavaScript. Hal ini akan membantu Anda menghindari kesalahan dalam penggunaan variabel dan memastikan bahwa variabel Anda memiliki lingkup blok yang sesuai.
