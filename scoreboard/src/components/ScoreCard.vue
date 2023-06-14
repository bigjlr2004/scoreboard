<script setup>
const props = defineProps(['score'])
const emit = defineEmits(['add', 'subtract'])
</script>

<template>
  <h1>{{ props.score }}</h1>
  <button class="button is-danger is-light is-small" @click="emit('add')">+</button>
  <button class="button is-danger is-light is-small" @click="emit('subtract')">-</button>
</template>

<style scoped></style>
