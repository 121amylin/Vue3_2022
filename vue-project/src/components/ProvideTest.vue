<script setup>
import { inject } from 'vue'
const user = inject('user')
</script>
<template>
  {{user}}
</template>