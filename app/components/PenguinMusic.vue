<template>
  <div class="penguin-music">
    <audio ref="audioPlayer" loop>
      <source src="/audio/love-so-fine.mp3" type="audio/mpeg" />
      Seu navegador não suporta o áudio :(.
    </audio>
    <div>
      <v-icon @click="pauseAudio">mdi-pause</v-icon>
      <v-icon @click="playAudio">mdi-play</v-icon>
    </div>
  </div>
</template>

<script setup lang="ts">
const audioPlayer = ref<HTMLAudioElement | null>(null);

const playAudio = () => {
  console.log('Playing audio', audioPlayer)
  if (audioPlayer.value) {
    audioPlayer.value.play()
  } else {
    console.error('Audio player not found')
  }
}

const pauseAudio = () => {
  if (audioPlayer.value) {
    audioPlayer.value.pause()
  }
}

onMounted(() => {
  playAudio() // it doesn't work for some browsers, because they block autoplay, need an user interaction
})
</script>

<style lang="scss" scoped>
.penguin-music {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.5);
}
</style>
