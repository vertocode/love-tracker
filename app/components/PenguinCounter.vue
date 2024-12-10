<template>
  <v-container class="text-center">
    <v-card color="primary" class="mb-5 text-white">
      <v-card-title class="display-1 font-weight-bold">
        No gelo da vida, dois pinguins caminham lado a lado. ❄️❤️
      </v-card-title>
    </v-card>

    <v-card color="secondary" class="py-4 text-white">
      <v-card-title class="display-3 font-weight-bold">
        {{ difference.years }} anos, {{ difference.months }} {{ difference.months === 1 ? 'mês' : 'meses' }}, {{ difference.days }} {{ difference.days === 1 ? 'dia' : 'dias' }},
        {{ difference.hours }} {{ difference.hours === 1 ? 'hora' : 'horas' }}, {{ difference.minutes }} {{ difference.minutes === 1 ? 'minuto' : 'minutos' }},
        e {{ difference.seconds?.toFixed(0) }} {{ Number(difference.seconds?.toFixed(0)) === 1 ? 'segundo' : 'segundos' }} juntinhos
      </v-card-title>
    </v-card>
  </v-container>
</template>

<script setup lang="ts">
import { DateTime } from 'luxon'

const timer = ref<number | null>(null)
const secondsPassed = ref(0)
const difference = ref({
  years: 0,
  months: 0,
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0
})

onMounted(() => {
  timer.value = window.setInterval(() => {
    const relationshipDate = DateTime.fromISO("2021-11-12")
    difference.value = DateTime.now().diff(relationshipDate, ['years', 'months', 'days', 'hours', 'minutes', 'seconds']).plus({ seconds: secondsPassed.value })
  }, 1000)
})
onBeforeUnmount(() => {
  if (timer.value) clearInterval(timer.value)
})
</script>

<style scoped>
.text-center {
  text-align: center;
}
</style>
