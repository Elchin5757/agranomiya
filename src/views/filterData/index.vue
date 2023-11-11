<script setup lang="ts">
import { ref } from "vue";
const region = ref("");
const regions = [
  "Andijon",
  "Namangan",
  "Buxoro",
  "Samarqand",
  "Xorazm",
  "Surxandaryo",
  "Sirdaryo",
];
</script>

<template>
  <div class="filter-container">
    <div class="filter-item">
      <span>Viloyatni tanlang</span>
      <q-select v-model="region" :options="regions" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.filter-container {
  width: 100%;
  display: flex;
  align-items: center;
}

.filter-item {
  display: flex;
  align-items: center;
}
</style>
