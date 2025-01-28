<script setup>
import { ref, reactive } from 'vue'
// let a = 1
// let b = 2
// let c = a + b // 3
// console.log(c)
const title = ref('Vue.js Course')
let price = ref(9.99)
console.log(price.value)
function increment() {
  price.value += 1
  // console.log(price)
  instructor.age += 1
  instructor.bio = 'hi'
  instructor.sns.twitter = '@__niseaka__'
}
const info = ref({
  students: 1000,
  rating: 4
})
const instructor = reactive({
  name: 'Yoshipi',
  age: 25,
  sns: {
    twitter: '@__yoshipi__',
    youtube: '@ypshipi',
    a: {}
  }
})
instructor.bio = 'hello'
// console.log(instructor.age)
// console.log(info)
console.log(info.value)
// console.log(instructor)
console.log(instructor.sns)
</script>
<template>
  <h1>Title: {{ title }}</h1>
  <h2>Title: ${{ price - 1 }}</h2>
  <button @click="increment">button</button>
  <h2>Students:{{ info.students }}</h2>
  <h2>instructor age:{{ instructor.age }}</h2>
  <h2>instructor bio:{{ instructor.bio }}</h2>
  <h2>instructor SNS Twitter:{{ instructor.sns.twitter }}</h2>
</template>
<style>
h1 {
  color: red;
}
</style>