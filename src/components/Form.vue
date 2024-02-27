<template>
  <form @submit.prevent="submitForm">
    <label for="postal_code">郵便番号：</label>
      <input type="text" id="postal_code" v-model="zipcode">
      <button type="submit">住所を検索</button>
  </form>
</template>

<script setup>
import { ref } from "vue"

const zipcode = ref("")

const submitForm =() => {
  emits("submit-form", zipcode.value)
}

const emits = defineEmits([
  "submit-form"
])
</script>
