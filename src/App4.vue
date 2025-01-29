<script setup>
import { ref } from 'vue'
const vueURL = ref('https://vuejs.org')
const id = ref('vue-link')
</script>
<template>
    <a v-bind:id="id" v-bind:href="vueURL">Vue.js</a><br>
    <a :id="id" :href="vueURL">Vue.js</a><br>
    <a :id :href="vueURL">Vue.js</a><br>
    <a :id="undefined" :href="false">Vue.js</a><br>
    <button :disabled="false">button</button><br>
    <button :disabled="true">button</button><br>
    <a v-bind="{ id: id, href: vueURL }">Vue.js</a><br>
</template>