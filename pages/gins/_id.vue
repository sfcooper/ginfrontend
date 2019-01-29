<template>
  <section class="container">
    <h1>{{ gins.gin_name }}</h1>
    <p>{{ gins.snippet }}</p>
    <p>{{ gins.abv }}</p>
    <br>
  </section>
</template>
<script>
import axios from 'axios'
export default {
  asyncData({ params }) {
    return axios.get(`/api/v1/gins/${params.id}`)
      .then((res) => {
        return { gins: res.data }
      })
  }
}
</script>
<style>
</style>
