<script setup>
import { ref } from 'vue'
import MatchupTitle from './components/MatchupTitle.vue'
import ScoreCard from './components/ScoreCard.vue'
import GameStatus from './components/GameStatus.vue'
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
  <div class="main">
    <div class="is-flex is-flex-direction-column">
      <div class="panel-block">
        <MatchupTitle :team1="team1" :team2="team2" />
      </div>
      <div class="m-3 is-flex is-justify-content-center">
        <GameStatus :team1="team1" :team2="team2" />
      </div>
      <div class="panel-block is-flex is-justify-content-space-around">
        <div>
          <ScoreCard :team="team1" @add="add(team1)" @subtract="subtract(team1)" />
        </div>
        <div>
          <ScoreCard :team="team2" @add="add(team2)" @subtract="subtract(team2)" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.main {
  width: 400px;
  margin: auto;
}
</style>
