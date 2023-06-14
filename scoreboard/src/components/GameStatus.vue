<script setup>
import { computed } from 'vue'
const props = defineProps(['team1', 'team2'])

const isGameTied = computed(() => props.team1.score === props.team2.score)

const gameLeaderDisplay = computed(() => {
  const leadingTeam = props.team1.score > props.team2.score ? props.team1 : props.team2
  const lead = Math.abs(props.team1.score - props.team2.score)
  const points = lead === 1 ? 'point' : 'points'

  return `The ${leadingTeam.name} are leading by ${lead} ${points}.`
})
</script>

<template>
  <div class="is-flex is-justify-content-center is-flex-direction-column">
    <div>Game Status:</div>
    <p v-if="isGameTied">The game is tied.</p>
    <p v-else>{{ gameLeaderDisplay }}</p>
  </div>
</template>

<style scoped></style>
