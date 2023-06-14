<script setup>
const props = defineProps(['team1', 'team2'])
</script>

<template>
  <div class="is-size-1 is-bold">
    <div class="is-flex panel-block is-flex is-justify-content-space-around">
      <div :class="{ winning: props.team1.score > props.team2.score }">
        {{ props.team1.name }}
      </div>
      <div class="m-5">vs</div>
      <div :class="{ winning: props.team2.score > props.team1.score }">
        {{ props.team2.name }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.winning {
  color: goldenrod;
}
</style>
