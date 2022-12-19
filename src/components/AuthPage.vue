<template>
  <div class="wrapper-auth-page">
    <h1 class="auth-title">Hibernia CRM</h1>
    <div id="formContent">
      <form @submit.prevent="login">
        <div class="alert alert-danger" v-show="error">
          <strong>Danger!</strong> {{errors}}
        </div>
        <input type="text"
               id="login"
               placeholder="login"
               v-model.trim="username" >
        <input type="password"
               id="password"
               placeholder="password"
               v-model.trim="password">
        <input type="submit" value="Log In">
      </form>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import router from "@/router";

export default {
  name: "auth-page",
  data() {
    return {
      username : 'danilov',
      password : 'pupil',
      errors: '',
      error : false,
    };
  },

  methods: {

    async login(){
      try{
        const response = await axios.post(import.meta.env.VITE_APP_API + '/login', {
          username: this.username,
          password: this.password
        });
        console.log(response);
        //Получаем ответ по апи, устанавливаем в sessionStorage переменную loggedIn в true,
        // чтобы не отображать header на страницах и переходим на страницу accounting
        this.$store.commit('setLoggedIn', true);
        localStorage.setItem('loggedIn', 'true');
        localStorage.setItem('role', response.data.role);
        localStorage.setItem('username', this.username);
        this.error = false;
        await router.push({name: 'accounting'})

      }catch (response) {
        console.log(response);
        console.log('ERROR LOGIN', response)
        this.errors = response.message;
        this.error = true
        localStorage.clear()
      }
    },

    //Проверка работоспособности API
    async test(){
      const response = await axios.get(import.meta.env.VITE_APP_API + '/status');
      console.log(response.data);
    }
  }
}
</script>

<style>
</style>