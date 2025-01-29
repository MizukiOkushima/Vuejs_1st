<script setup>
import { ref, computed } from 'vue'
const score = ref(0)
const count = ref(0)
// const evaluation = score.value > 3 ? 'Good' : 'Bad'
// const evaluation = ref(score.value > 3 ? 'Good' : 'Bad')
function tmp() {
    // console.log('tmp')
    return score.value > 3 ? 'Good' : 'Bad'
}
const evaluation = computed(() => {
    console.log('computed')
    // score.value = 0
    // setTimeout(() => { }, 1000)
    return score.value > 3 ? 'Good' : 'Bad'
    // return tmp()
})
// evaluation.value = 'hello'
console.log(evaluation)
console.log(evaluation.value)
const parentComp = computed(() => {
    console.log('parent computed')
    return evaluation.value
})
function getEvaluation() {
    console.log(evaluation.value)
}
</script>
<template>
    <p>{{ score > 3 ? 'Good' : 'Bad' }}</p>
    <!-- <p>{{ evaluation }}</p> -->
    <p>{{ tmp() }}</p>
    <p>{{ parentComp }}</p>
    <p>score: {{ score }}</p>
    <p>count: {{ count }}</p>
    <button @click="score++">+1 score</button>
    <button @click="count++">+1 count</button>
    <button @click="getEvaluation">get Evaluation</button>
</template>