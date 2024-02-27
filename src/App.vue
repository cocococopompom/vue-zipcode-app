<template>
  <div class="wrapper">
    <div class="container">
      <Title />
      <Form @submit-form="getAddress"/>
      <Results :results="results" v-if="!loading"/>
      <Loading v-if="loading"/>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue"
import axios from "axios"
import Title from "./components/Title.vue"
import Form from "./components/Form.vue"
import Results from "./components/Results.vue"
import Loading from "./components/Loading.vue"
import "./assets/base.css"

const loading = ref(false)

const results = reactive({
  address1: "",
  address2: "",
  address3: ""
})


const getAddress = (zipcode) => {
  loading.value = true
  axios.get(`http://zipcloud.ibsnet.co.jp/api/search?zipcode=${zipcode}`)
    .then(res => {
      results.address1 = res.data.results[0].address1,
      results.address2 = res.data.results[0].address2,
      results.address3 = res.data.results[0].address3

      loading.value = false
    })
}

</script>

<style></style>
