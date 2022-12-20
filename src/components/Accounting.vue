<template>
<!--  Как пример можно будет заменить на гифку загрузки -->
  <div class="layout-content" v-if="!loading">
    <h1>Accounting</h1>
  </div>
</template>

<script>
import axios from "axios";

// noinspection JSUnusedGlobalSymbols
export default {
  name: "accounting",
  data() {
    return {
      loading: true,
    }
  },
  methods: {},
  beforeMount() {
    const year = new Date(Date.now()).getFullYear()
    // По идее можно будет Authorization header установить в axios.defaults.headers.common['Authorization'] = localStorage.getItem('token')
    axios.get(import.meta.env.VITE_APP_API + `/visits?start_year=${year}&start_month=1`, {
      headers: {
        Authorization: "Bearer " + localStorage.getItem("token")
      }
    }).then(r => {
      // Я ж говорил, что через .then работает :)
      console.log(r.data)
      this.$data.loading = false
    })
      .catch(e => console.log(e))
  }

}
</script>

<style scoped>

</style>