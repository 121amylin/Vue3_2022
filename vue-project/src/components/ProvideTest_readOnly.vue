<script setup>
// import { ref, provide } from 'vue'
import { inject } from 'vue'
const user = inject('user')
function text() {
  user.value[1].name = '123'
}
</script>
<template>
  <p> {{user}}</p>
  <button @click="text">revise</button>

</template>