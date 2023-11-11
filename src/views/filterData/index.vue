<script setup lang="ts">
import { ref } from "vue";
const region = ref("");
const destrict = ref("");
const station = ref("");
const product = ref("");
const pest = ref("");

const regions = [
  "Andijon",
  "Namangan",
  "Buxoro",
  "Samarqand",
  "Xorazm",
  "Surxandaryo",
  "Sirdaryo",
];

const districts = [
  "Yuqori chirchiq",
  "Quyi chirchiq",
  "Orta chirchiq",
  "Chirchiq",
  "Boka",
  "Qorasuv",
  "Ortasaroy",
];

const stations = [
  "station 1",
  "station 2",
  "station 3",
  "station 4",
  "station 5",
  "station 6",
];

const products = ["Paxta", "Sholi"];

const pests = ["G'ovak qurti", "Chuvalchang"];

const rows = [
  {
    name: "Frozen Yogurt",
    damp: 17,
    usefulDamp: 50,
    dagree: 134,
  },
  {
    name: "Something 1",
    damp: 17,
    usefulDamp: 50,
    dagree: 134,
  },
  {
    name: "Something 2",
    damp: 17,
    usefulDamp: 50,
    dagree: 134,
  },
  {
    name: "Something 2",
    damp: 17,
    usefulDamp: 50,
    dagree: 134,
  },
  {
    name: "Something 3",
    damp: 17,
    usefulDamp: 50,
    dagree: 134,
  },
  {
    name: "Something 4",
    damp: 17,
    usefulDamp: 50,
    dagree: 134,
  },
  {
    name: "Something 5",
    damp: 17,
    usefulDamp: 50,
    dagree: 134,
  },
];

const columns: any = [
  {
    name: "name",
    field: "name",
    label: "Maxusol nomi",
    align: "left",
  },
  {
    name: "damp",
    field: "damp",
    align: "center",
    label: "Namligi",
  },
  {
    name: "usefulDamp",
    field: "usefulDamp",
    align: "center",
    label: "Foydali namligi",
  },
  {
    name: "dagree",
    field: "dagree",
    align: "center",
    label: "Hozirgacha bolgan namligi",
  },
];
</script>

<template>
  <div class="filter-container">
    <q-select
      color="white"
      dark
      v-model="region"
      :options="regions"
      label="Viloyatni tanlang"
      outlined
      square
    />
    <q-select
      color="white"
      dark
      :disable="!region"
      v-model="destrict"
      :options="districts"
      label="Tumanni tanlang"
      outlined
      square
    />
    <q-select
      color="white"
      dark
      :disable="!destrict"
      v-model="station"
      :options="stations"
      label="Stantsiyani tanlang"
      outlined
      square
    />
    <q-select
      color="white"
      dark
      :disable="!station"
      v-model="product"
      :options="products"
      label="Maxsulot nomini tanlang"
      outlined
      square
    />
    <q-select
      color="white"
      dark
      :disable="!product"
      v-model="pest"
      :options="pests"
      label="Zararkunanda nomini tanlang"
      outlined
      square
    />
  </div>
  <div class="statistic-container">
    <q-table
      dark
      :rows="rows"
      :columns="columns"
      row-key="name"
      rows-per-page-label="Har bir sahifadagi qatorlar:"
    />
    <div class="statistic-cards">
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">Umumiy havf</span>
        <div class="statistic-cards__card--value">35%</div>
      </div>
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">Faoydali harorat</span>
        <div class="statistic-cards__card--value">618 C</div>
      </div>
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">Rivojlanish kuni</span>
        <div class="statistic-cards__card--value">80 kun</div>
      </div>
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">Avlodlar soni</span>
        <div class="statistic-cards__card--value">2 avlod</div>
      </div>
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">Tuhumdan chiqi...</span>
        <div class="statistic-cards__card--value">100 %</div>
      </div>
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">G'umbakka aylan...</span>
        <div class="statistic-cards__card--value">100%</div>
      </div>
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">G'umbakdan chi...</span>
        <div class="statistic-cards__card--value">53%</div>
      </div>
      <div class="statistic-cards__card">
        <span class="statistic-cards__card--title">Yetuk zotga ayl...</span>
        <div class="statistic-cards__card--value">0 %</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.filter-container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 25px;
  margin-bottom: 15px;
}

.statistic-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
  // max-height: ;
}

.statistic-cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: 2;
  gap: 5px;

  &__card {
    width: 100%;
    height: 100%;
    background-color: #000;
    color: white;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    justify-content: start;
    align-items: center;
    padding: 10px 10px 20px 10px;
    border: 1px solid $primary;

    &--title {
      font-size: 14px;
      font-weight: 500;
    }
    &--value {
      font-size: 28px;
      font-weight: 600;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;
      color: $positive;
    }
  }
}
</style>
