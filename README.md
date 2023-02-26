# 05 - Function as First Class Citizen

# Penjelasan Singkat Tentang Function as First Class Citizen

Dalam berbagai literature dikatakan bahwa Javascript adalah bahasa pemograman yang mendukung first-class function. Sebenarnya apa sih first-class function itu? Dalam ilmu computer, Bahasa pemograman dapat dikatakan mendukung first-class function apabila memberlakukan function sebagai first-class object. First-class object itu sendiri adalah sebuah entitas (bisa berbentuk function, atau variable) yang dapat dioperasikan dengan cara yang sama seperti entitas lain. Operasi tersebut biasanya mencakup passing entitas sebagai argument, return entitas dari sebuah function, dan assign entitas kedalam variable, object atau array. Apabila dikaitkan dengan javascript, intinya function pada javascript adalah first-class object, Yang berarti function tersebut dapat:

- Di assign ke dalam variable, object, atau array
- Di passing sebagai argument pada function lain
- Di return dari sebuah function

# Assign a function
```
// 1. Assign ke dalam variable : 
let fn = function doSomething() {
  console.log('Hallo')
}
fn() // Hallo

// 2. Assign ke dalam object : 
let obj = { 
  doSomething : function doSomething()
  {
    console.log('Hallo')
  }
}
obj.doSomething() // Hallo

//3. Assign ke dalam array : 
let arr = []
arr.push(function doSomething() 
  {
    console.log('Hallo')     
  }
)
arr[0]() // Hallo
```    
Kita bisa assign anonymous function (function tanpa nama) kedalam variabel, object atau array dimana isi function tersebut dapat di return apabila ditambahkan tanda kurung () di bagian akhir sewaktu proses invocation (pemanggilan).

Apabila function di beri nama seperti contoh diatas, sebenarnya tidak ada masalah, akan tetapi kalian hanya bisa menggunakan nama variabel untuk melakukan proses invocation, bukan menggunakan nama function. Sebagian programmer memberi nama sebuah function pada contoh diatas untuk mempermudah ketika men-debug kode.

# Pass a function as an argument
```
function sayHello() {
  return "Hello, ";
}
function greeting(helloMessage, name) {
  console.log(helloMessage() + name);
}
// Pass `sayHello` as an argument to `greeting` function
greeting(sayHello, "JavaScript!");
// Hello, Javascript!
```
Disini kita mempassing function sayHello() kedalam function greeting() sebagai argument. ini menjelaskan bagaimana kita memberlakukan function sayHello() tersebut sebagai value dari function greeting().

# Return a function as results
```
function sayHello() {
  return function() {
  console.log("Hello!");
  }
}

sayHello()();
// Hello
```
Di contoh ini, kita me-return sebuah function dari function lain. Function yang me-return function lain dinamakan Higher-Order Function. Apabila dikaitkan dengan contoh diatas, maka function sayHello() itu dinamakan Higher-Order Function atau function yang memiliki kedudukan tertinggi karena bisa me-return function lain.

# Contoh Lain Untuk Code
```
// Mendefinisikan sebuah fungsi sebagai variabel
const add = function(a, b) {
  return a + b;
}

// Menyimpan sebuah fungsi sebagai nilai properti dalam objek
const person = {
  name: "John",
  age: 30,
  getGreeting: function() {
    return `Hello, my name is ${this.name} and I'm ${this.age} years old.`;
  }
};

// Mengirim sebuah fungsi sebagai argumen ke dalam fungsi lainnya
function doOperation(a, b, operation) {
  return operation(a, b);
}
const sum = doOperation(2, 3, add); // Memanggil fungsi "add" dari dalam fungsi "doOperation"

// Mengembalikan sebuah fungsi dari dalam sebuah fungsi
function createAdder(x) {
  return function(y) {
    return x + y;
  }
}
const addFive = createAdder(5);
const result = addFive(10); // Menghasilkan nilai 15
```
