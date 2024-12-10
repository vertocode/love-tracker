<template>
  <v-card color="white" class="mb-5 text-black">
    <v-card-title class="display-1 font-weight-bold">
      No gelo da vida, dois pinguins caminham lado a lado. ❄️❤️
    </v-card-title>

    <section v-for="(slide, idx) in slides" :key="`slide-${idx}`">
      <v-card-subtitle class="subtitle">
        {{ slide.title }}
      </v-card-subtitle>
      <v-carousel class="carousel" cycle>
        <v-carousel-item
            v-for="(_, imageIdx) in new Array(slide.number)"
            :key="`img-${imageIdx}`"
        >
          <v-img
              :src="`/carousel/${slide.folder}/${imageIdx + 1}.jpg`"
              alt="imagem"
              class="image"
          />
        </v-carousel-item>
      </v-carousel>
    </section>
  </v-card>
</template>

<script setup lang="ts">
const slides = [
  {
    title: 'Amamos pegar uma 🌊',
    folder: 'beach',
    number: 4
  },
  {
    title: 'Tantos momentos incríveis juntos! 🎉',
    folder: 'moments',
    number: 10
  },
  {
    title: 'Lembra do início? 🥰',
    folder: 'beginning',
    number: 3
  }
]
</script>

<style lang="scss" scoped>
.image {
  object-fit: cover;
  display: flex;
  height: 100%;
  align-items: center;
}

.subtitle {
  margin-top: 24px;
  font-size: 2rem;
  text-wrap: wrap;
}

.carousel {
  background-color: rgba(128, 128, 128, 0.2);
}

:deep(.v-responsive__content) {
  display: flex !important;
}
</style>
