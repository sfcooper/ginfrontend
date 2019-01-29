<template>
  <section class="container">
    <h1>{{ distilleries.distillery_name }}</h1>
    <p>{{ distilleries.snippet }}</p>
    <p>{{ distilleries.country }}</p>
    <p>{{ distilleries.website }}</p>
    <br>
  </section>
</template>
<script>
import axios from 'axios'
export default {
  asyncData({ params }) {
    return axios.get(`/api/v1/distilleries/${params.id}`)
      .then((res) => {
        return { distilleries: res.data }
      })
  }
}
</script>
<style>
</style>
