<template>
  <header class="header">
    <div class="header-content">
      <div class="header-logo">
      <img class="logo" src="@/assets/HiberniaLogo.png" alt="logo"/>
      <h2 class="header-title"
          style="margin: 1rem">
        Hibernia CRM</h2>
      </div>
      <div class="topnav-links">
        <a class="topnav-links-btn" href="#">Учет занятий</a>
        <a class="topnav-links-btn" href="#">Группы</a>
        <a class="topnav-links-btn" href="#">Концерты</a>
        <a class="topnav-links-btn" href="#">Костюмы</a>
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