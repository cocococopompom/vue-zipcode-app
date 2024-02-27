<template>
  <div class="results_container">
    <label>都道府県：</label>
      <input type="text" v-model="results.address1"><br>
    <label>市区町村：</label>
      <input type="text" v-model="results.address2"><br>
    <label>町　　域：</label>
      <input type="text" v-model="results.address3">
  </div>
</template>

<script setup>
const props =defineProps({
  results: Object
})
</script>