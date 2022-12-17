<template>
  <header class="header">
    <div class="header-content">
      <div class="header-logo">
        <a href="https://www.hiberniadance.ru/">
          <img class="logo" src="@/assets/HiberniaLogo.png" alt="logo"/>
        </a>
      <h2 class="header-title"
          style="margin: 1rem">
        Hibernia CRM</h2>
      </div>
      <div class="topnav-links">
        <router-link to="/accounting">Учет занятий</router-link>
        <router-link to="/groups">Группы</router-link>
        <router-link to="/concerts">Концерты</router-link>
        <router-link to="/costumes">Костюмы</router-link>
      </div>
      <div class="topnav-icons">
        <a href="#"><i class="fas fa-user"></i></a>
        <a href="#"><i class="fas fa-sign-out-alt"></i></a>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "header-content"
}
</script>