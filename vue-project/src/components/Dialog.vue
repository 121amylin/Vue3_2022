<script setup>
import { ref } from 'vue'
const dialogIsopen = ref(false)

const toggleDialogIsopen = () => {
    console.log(123)
    dialogIsopen.value = !dialogIsopen.value
}
</script>

<template>
    <button @click="toggleDialogIsopen">顯示彈出</button>
    <dialog :open="dialogIsopen">
        <button @click="toggleDialogIsopen">X</button>
        <p>Greetings, one and all!</p>
        <form method="dialog">
            <button>OK</button>
        </form>
    </dialog>
</template>

<style scoped>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

dialog {
    background-color: #ccc;
    border-radius: 20px;
}
</style>
