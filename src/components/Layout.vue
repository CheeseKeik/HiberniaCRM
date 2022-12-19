<template>
  <div class="layout">
    <header-content v-if="loggedIn"/>
    <main class="layout-content">
      <!--TODO доделать компоненты-->
      <router-view/>
    </main>
    <footer-content/>
  </div>
</template>

<script>
import HeaderContent from "@/components/HeaderContent.vue";
import FooterContent from "@/components/FooterContent.vue";
import store from "@/vuex-store";

export default {
  name: "layout",
  components: {FooterContent, HeaderContent},
  //TODO: Добавить проверку на авторизацию и корректное отображение компонентов
  data() {
    return {
    }
  },
  computed:{
    loggedIn(){
      return store.state.loggedIn
    }
  },
}
</script>