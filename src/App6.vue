<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>
<template>
    <!-- preventDefault() デフォルトの動きを防ぐ -->
    <button @click="$event.preventDefault()">button</button><br>
    <a href="https://vuejs.org" @click="$event.preventDefault()">Vue.js</a><br>
    <!-- stopProgagation() 伝播を防ぐ-->
    <p>{{ count }}</p>
    <div @click="count++"><br>
        <button @click="$event.stopPropagation()">button</button><br>
        <button @click.stop="count = 30">button</button><br>
    </div>
    <a href="https://vuejs.org" @click.prevent="">Vue.js</a>
    <a href="https://vuejs.org" @click.prevent.stop="">Vue.js</a>
</template>