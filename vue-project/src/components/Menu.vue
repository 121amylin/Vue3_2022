<script setup>
import { defineProps } from 'vue'
const props = defineProps({
    isOpen: {
        type: Boolean,
        default: false
    },
    toggleMenuOpen: {
        type: Function,
        default: () => { }
    }
})
</script>
<template>
    <button class="menu_btn" @click="toggleMenuOpen">{{isOpen?'close':'menu'}}</button>
</template>

<style scoped>
.menu_btn {
    margin-bottom: 20px;
}
</style>