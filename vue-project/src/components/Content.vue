<script setup>
import { defineProps } from "vue"
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
    <div :class="[props.isOpen?'open':'']" class="content">123</div>
</template>

<style scoped>
.content {
    width: 200px;
    height: 600px;
    background-color: aqua;
    transform: translateX(-100%);
    opacity: 0;
    transition: transform .3s, opacity .3s;

}

.content.open {
    transform: translateX(0);
    opacity: 1;
}
</style>