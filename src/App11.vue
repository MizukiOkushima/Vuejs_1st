<script setup>
import { ref } from 'vue'
const isRed = ref(true)
const isBgBlue = ref(true)
const className = ref('red')
function toggleClass() {
    isRed.value = !isRed.value
    isBgBlue.value = !isBgBlue.value
    // className.value = 'bg-blue'
}
</script>
<template>
    <!-- <div class="red bg-blue">Hello</div> -->
    <!-- <div :class="{ red: false, 'bg-blue': true }">Hello</div> -->
    <!-- <div :class="{ red: isRed, 'bg-blue': isBgBlue }">Hello</div> -->
    <!-- <div :class="[className, 'bg-blue']">Hello</div> -->
    <!--  -->
    <div class="border" :class="[className, { 'bg-blue': isBgBlue }]">Hello</div>
    <button @click="toggleClass">toggle</button>
</template>
<style>
.red {
    color: red
}

.bg-blue {
    background-color: blue;
}

.border {
    border: 1px solid red
}
</style>