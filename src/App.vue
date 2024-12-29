<template>
  <RouterView />
  <a-button>我是按钮</a-button>
  <a-input v-model:value="value" placeholder="Basic usage" />
</template>
<script setup lang="ts">
import { ref } from 'vue'
const value = ref('')
</script>
<style scoped></style>
