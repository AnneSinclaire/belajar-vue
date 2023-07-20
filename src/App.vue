<script setup>
let mgs = "Hallo Dunia";
let headName = "<h1> Nama Saya Ahmad </h1>";

let number = 1;

let ok = "YES"

let seen = true;



import { ref, onMounted } from 'vue'

//reactive state
const count = ref(0)

function increment() {
  count.value++
}

onMounted(() => {
  console.log(`the initial count is ${count.value}.`)
})


let message = ref("Hai vue js")
function balikpesan() {
  message.value = message.value.split('').reverse().join('')
}

// pengulangan
let todos = [
  { teks: 'Belajar JavaScript' },
  { teks: 'Belajar Vue' },
  { teks: 'Buat proyek keren' }
]

// Input
let pesan = ref("Hai Vue");

</script>



<template>
  <div>
    <span>{{ mgs }}</span><br>
    <span style="color: pink;">Ini warna pink</span><br>
    <span v-html="headName"></span> <br>

    <a href="https://vuejs.org/guide/essentials/template-syntax.html#using-javascript-expressions"></a> <button v-bind:link="Dynamiclink"> Tombol</button>
    </div>
    <div v-bind:id="headName"></div><br>

    <button @click="increment">Klik : {{ count }}</button> <br>

    {{ number + 1 }} <br>

    {{ ok ? 'YES' : 'NO' }} <br>

    {{ mgs.split('').reverse().join('') }} <br>

    <p v-if="seen">Sekarang Anda bisa melihatku</p>

    <!-- split button -->
    <p>{{ message }}</p>
    <button v-on:click="balikpesan">Balikan Pessan</button>

    <!-- for -->
    <br> pengulangan
    <ol>
      <li v-for="todo in todos">
          {{ todo.teks }}
      </li>
    </ol>

    <!-- Input -->
    <p>{{ pesan }}</p>
    <input v-model ="pesan">

</template>



