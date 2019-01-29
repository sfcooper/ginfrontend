<template>
  <section class="container">
    <div>
      <h1>Gins</h1>
      <form @submit.stop.prevent="addGin">
        <h2>New Gin</h2>
        <p>
            <label for="gin_name" class="input-label">Title:</label>
            <input id="gin_name" v-model="gin_name" type="gin_name" name="gin_name" class="input">
        </p>
        <p>
            <label for="description" class="input-label">Description:</label>
            <input id="description" v-model="description" type="description" name="description" class="input">
        </p>
          <div>
            <label for="distillery" class="input-label">Distillery:</label>
            <multiselect
                v-model="distillery_id"
                track_by="id"
                :options="options"
                :searchable="true"
                placeholder="Choose One Distillery"
                >
            </multiselect>
        </div>
        <p>
            <input type="submit" value="Submit" class="button">
        </p>
      </form>
    </div>
  </section>
</template>
<script>
import axios from 'axios'
import VueNotifications from 'vue-notifications'
import Multiselect from 'vue-multiselect'

export default {

  components: { Multiselect },
  data() {
    return {
      gin_name: '',
      description: '',
      distillery_id: '',
      options: []
    }
  },
  notifications: {
    showSuccessMsg: {
      type: VueNotifications.types.success,
      title: 'Gin Added Successfully',
      message: 'That\'s the success!'
    },
    showInfoMsg: {
      type: VueNotifications.types.info,
      title: 'Hey you',
      message: 'Here is some info for you'
    },
    showWarnMsg: {
      type: VueNotifications.types.warn,
      title: 'Wow, man',
      message: 'That\'s the kind of warning'
    },
    showErrorMsg: {
      type: VueNotifications.types.error,
      title: 'Wow-wow',
      message: 'That\'s the error'
    }
  },
  methods: {

    addGin() {
      axios.post('http://localhost:4000/api/v1/gins', {
        gin_name: this.gin_name, description: this.description
      })
        .then((response) => {})
    },
    getDistilleries(req) {
      axios.get('/api/v1/distilleries')
        .then((res) => {
          this.options = res.data
        })
        .catch((error) => {
          console.log(error)
        })
    }
  }
}
</script>
<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
<style>

</style>
