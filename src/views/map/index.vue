<script setup lang="ts">
import { ref } from "vue";

const tab = ref("weather");
</script>

<template>
  <div class="map-container">
    <q-tab-panels
      v-model="tab"
      transition-prev="none"
      transition-next="none"
      class="bg-primary tab-panels overflow-hidden"
    >
      <q-tab-panel
        name="weather"
        dark
        class="q-pa-none"
        style="position: relative"
      >
        <iframe
          style="
            position: absolute;
            left: 0;
            bottom: 0;
            right: 0;
            height: 100%;
            border: none;
            top: 0;
          "
          src="https://www.ventusky.com/ru"
          width="100%"
        />
      </q-tab-panel>
    </q-tab-panels>
    <q-tabs
      v-model="tab"
      inline-label
      class="bg-secondary text-white shadow-2 tabs"
      indicator-color="transparent"
      active-color="positive"
    >
      <q-tab name="soilAnalysis" label="Tuproq tahlili" />
      <q-tab name="weather" label="Ob havo" />
      <q-tab name="farmers" label="Fermerlar" />
      <q-tab name="stations" label="Stantsiyalar" />
    </q-tabs>
  </div>
</template>

<style>
.map-container {
  position: relative;
}
.tab-panels {
  height: calc(100vh - 70px);
}

.tabs {
  position: absolute;
  bottom: 20px;
  left: 50%;
  bottom: 0;
  transform: translate(-50%, -50%);
  max-width: max-content;
  border-radius: 10px;
}
</style>
