<script setup>
const props = defineProps(['team'])
const emit = defineEmits(['add', 'subtract'])
</script>

<template>
  <div class="is-flex is-align-text-center">
    <div>
      <div class="is-size-2 is-align-self-center">{{ props.team.name }}</div>
      <div class="is-size-3 is-flex is-justify-content-center">
        {{ props.team.score }}
      </div>
      <div class="is-flex is-justify-content-center">
        <button class="button is-success is-small" @click="emit('add')">+</button>
        <button class="button is-danger is-small" @click="emit('subtract')">-</button>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
