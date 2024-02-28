<template>
  <table class="results_container">
    <tr class="address1_container">
      <th>都道府県：</th>
      <td>{{results.address1}}</td>
    </tr>
    <tr class="address23_container">
      <th>住　　所：</th>
      <td>{{results.address2}}{{results.address3}}</td>
    </tr>
  </table>
</template>

<script setup>
const props =defineProps({
  results: Object
})
</script>