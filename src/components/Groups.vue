<template>
  <div class="layout-content">
    <h1>Groups</h1>
    <div class="groups-content">
      <div class="groups-list" v-for="group in groups" key="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "groups"
}
</script>

<style>
.groups-content {
  border: 0.5rem solid black;
  border-radius: 1rem;
  background-color: #71c351;
  color: #181818;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>