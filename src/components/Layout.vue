<template>
  <div class="layout">
    <header-content/>
    <main class="layout-content">
      <div id="box"></div>
      <h1>Content</h1>
      <router-view/>
    </main>
    <footer-content/>
  </div>
</template>

<script>
import HeaderContent from "@/components/HeaderContent.vue";
import FooterContent from "@/components/FooterContent.vue";

export default {
  name: "layout",
  components: {FooterContent, HeaderContent}
}
</script>