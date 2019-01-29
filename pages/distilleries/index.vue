<template>
  <section class="container">
    <h1>Gins</h1>
    <div v-for="distillery in distilleries" v-bind:key="distillery.id">
      <h3><nuxt-link :to="{ name: 'distilleries-id', params: {id : distillery.id} }">{{ distillery.distillery_name }}</nuxt-link></h3>
      <p>{{ distillery.snippet }}</p>
      <p>{{ distillery.description }}</p>
      <p>{{ distillery.country }}</p>
      <br>
    </div>
  </section>
</template>
<script>
import axios from 'axios'
export default {
  asyncData({ req }) {
    return axios.get('/api/v1/distilleries')
      .then((res) => {
        return { distilleries: res.data }
      })
  }
}
</script>
<style>
</style>
