<template>
  <section class="container">
    <h1>Gins</h1>
    <div v-for="gin in gins" v-bind:key="gin.id">
      <h3><nuxt-link :to="{ name: 'gins-id', params: {id : gin.id} }">{{ gin.gin_name }}</nuxt-link></h3>
      <p>{{ gin.snippet }}</p>
      <p>{{ gin.description }}</p>
      <p>{{ gin.abv }}</p>
      <br>
    </div>
  </section>
</template>
<script>
import axios from 'axios'
export default {
  asyncData({ req }) {
    return axios.get('/api/v1/gins')
      .then((res) => {
        return { gins: res.data }
      })
  }
}
</script>
<style>
</style>
