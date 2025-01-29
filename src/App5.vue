<script setup>
import { ref } from 'vue'
const count = ref(0)
function countUp(event) {
    console.log(event)
    count.value = event.clientX
}
function countUpSecond(event, times) {
    count.value = event.clientX * times
}
</script>
<template>
    <p>{{ count }}</p>
    <button v-on:click="count++">button</button>
    <!-- インラインハンドラー -->
    <button @click="count++">button</button>
    <button @click="count = $event.clientX">button</button>
    <!-- メソッドハンドラー -->
    <button @click="countUp">button</button>
    <button @click="countUpSecond($event, 5)">button</button>
</template>