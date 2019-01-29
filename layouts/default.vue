<template>
  <div>
    <navbar></navbar>
    <nuxt />
    <mainfooter></mainfooter>
  </div>
</template>

<script>
import navbar from '../components/navbar'
import mainfooter from '../components/mainfooter'

export default {
  components: {
    navbar,
    mainfooter
  }
}
</script>

<style>

</style>
