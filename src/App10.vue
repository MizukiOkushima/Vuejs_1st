<script setup>
import { ref, watchEffect, watch } from 'vue'
const count1 = ref(0)
const count2 = ref(0)
const count3 = ref({
    a: 0
})
// watch 第一引数はrefオブジェクト等を直接入れること
// watch(count1, (newValue, oldValue) => {
//     console.log('watch')
//     // setTimeout(() => {
//     //     console.log(count1.value, count2.value, count3.value)
//     // }, 1000)
//     // console.log(count1.value, count2.value, count3.value)
//     console.log('newValue', newValue)
//     console.log('oldValue', oldValue)
// })
watch(
    () => {
        console.log('watch first argument')
        return count1.value + count2.value
        // watchのnewValueとoldValueが同じ値である場合第二引数の処理は実行されない
        // 値が変更された場合のみ実行される
        // count1.value
        // return 0
    },
    (newValue, oldValue) => {
        console.log('watch')
        console.log('newValue', newValue)
        console.log('oldValue', oldValue)
    }
)
// 配列で変数を宣言する場合
// newValueやoldValueも配列で格納される
watch([count1, count2], (newValue, oldValue) => {
    console.log('watch')
    console.log('newValue', newValue)
    console.log('oldValue', oldValue)
})
watch([count1, () => count2.value], (newValue, oldValue) => {
    console.log('watch')
    console.log('newValue', newValue)
    console.log('oldValue', oldValue)
})
// リアクティブオブジェクトのプロパティを監視したい場合、()を使用した関数で宣言する必要がある
watch(
    () => {
        console.log('watch first argument')
        return count3.value.a
    },
    (newValue, oldValue) => {
        console.log('watch')
        console.log('newValue', newValue)
        console.log('oldValue', oldValue)
    },
    {
        immediate: true
    }
)

// watchEffect(() => {
//     console.log('watchEffect')
//     console.log(count1.value, count2.value, count3.value)
//     // console.log(count.value)
//     // setTimeout(() => {
//     //     console.log('after 1 second')
//     // }, 1000)
//     // count.value = 'hello'
// })
</script>
<template>
    <p>{{ count1 }}(count1)</p>
    <p>{{ count2 }}(count2)</p>
    <p>{{ count3 }}(count3)</p>
    <button @click="count1++">count1++</button>
    <button @click="count2++">count1++</button>
    <button @click="count3.a++">count1++</button>
</template>