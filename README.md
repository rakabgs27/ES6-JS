# 01 - let

# APA ITU "let" di JavaScript

Di JavaScript, let adalah kata kunci yang digunakan untuk mendeklarasikan variabel dengan lingkup blok. Ketika Anda menggunakan let untuk mendeklarasikan variabel, variabel tersebut hanya dapat diakses di dalam blok di mana variabel tersebut dideklarasikan. Sebuah blok adalah setiap rangkaian pernyataan yang terdapat dalam kurung kurawal {}. Berikut adalah contohnya: <br>
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
