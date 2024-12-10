<template>
  <v-card color="white" class="mb-5 text-black">
    <v-card-title class="display-1 font-weight-bold">
      No gelo da vida, dois pinguins caminham lado a lado. ❄️❤️
    </v-card-title>

    <section>
      <v-card-subtitle class="mt-5">
        Amamos pegar uma praia
      </v-card-subtitle>
      <v-carousel cycle>
        <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
        >
          <v-sheet
              :color="colors[i]"
              height="100%"
          >
            <div class="d-flex fill-height justify-center align-center">
              <div class="text-h2">
                {{ slide }} Slide
              </div>
            </div>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </section>

    <section>
      <v-card-subtitle class="mt-5">
        Amamos pegar uma praia
      </v-card-subtitle>
      <v-carousel cycle>
        <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
        >
          <v-sheet
              :color="colors[i]"
              height="100%"
          >
            <div class="d-flex fill-height justify-center align-center">
              <div class="text-h2">
                {{ slide }} Slide
              </div>
            </div>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </section>

    <section>
      <v-card-subtitle class="mt-5">
        Amamos pegar uma praia
      </v-card-subtitle>
      <v-carousel cycle>
        <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
        >
          <v-sheet
              :color="colors[i]"
              height="100%"
          >
            <div class="d-flex fill-height justify-center align-center">
              <div class="text-h2">
                {{ slide }} Slide
              </div>
            </div>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </section>
  </v-card>
</template>

<script setup lang="ts">
const colors = [
  'indigo',
  'warning',
  'pink darken-2',
  'red lighten-1',
  'deep-purple accent-4'
]

const slides = [
  'First',
  'Second',
  'Third',
  'Fourth',
  'Fifth'
]
</script>
