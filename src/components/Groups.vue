<template>
  <div class="layout-content">
    <h1>Groups</h1>
    <div class="alert alert-danger">
      <strong>Danger!</strong> Indicates a dangerous or potentially negative action.
    </div>
    <div class="alert alert-success">
      <strong>Success!</strong> You should <a href="#" class="alert-link">read this message</a>.
    </div>
  </div>
</template>

<script>
export default {
  name: "groups"
}
</script>

<style scoped>
.alert-danger {
  color: #721c24;
  background-color: #f8d7da;
  border-color: #f5c6cb;
}
</style>