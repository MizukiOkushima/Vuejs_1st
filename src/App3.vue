<script setup>
import { ref } from 'vue'
const message = ref('<h1>Hello</h1>')
</script>
<template>
    <!-- <div>{{ message }}</div> -->
    <div v-html="message"></div>
</template>