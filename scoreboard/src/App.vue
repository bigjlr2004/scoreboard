<script setup>
import { ref } from 'vue'
import MatchupTitle from './components/MatchupTitle.vue'
import ScoreCard from './components/ScoreCard.vue'
const team1 = ref({
  name: 'Cavs',
  score: '0'
})
const team2 = ref({
  name: 'Raiders',
  score: '0'
})

const add = (team) => {
  team.score++
}
const subtract = (team) => {
  if (team.score > 0) {
    team.score--
  }
}
</script>

<template>
  <div>
    <MatchupTitle :team1="team1" :team2="team2" />
  </div>
  <div>
    <ScoreCard :score="team1.score" @add="add(team1)" @subtract="subtract(team1)" />
  </div>
  <div>
    <ScoreCard :score="team2.score" @add="add(team2)" @subtract="subtract(team2)" />
  </div>
</template>

<style scoped></style>
