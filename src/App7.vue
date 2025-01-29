<script setup>
import { ref } from 'vue'
const count = ref(0)
const eventName = 'keyup'
</script>
<template>
    <p>{{ count }}</p>
    <input type="text" @keyup="count++" /> 
    <input type="text" @keyup.space="count++" /> 
    <input type="text" @keyup.space.delete="count++" /> 
    <input type="text" @[eventName].space.delete="count++" /> 
    <input type="text" v-on:[eventName].space.delete="count++" /> 
    <!-- <input type="text" v-bind:[eventName].space.delete="count++" />  -->
</template>