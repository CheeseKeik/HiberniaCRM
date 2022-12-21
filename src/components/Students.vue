<template>
  <div class="layout-content">
    <div class="student-header-container">
      <h1>Список студентов</h1>
      <div>
        <button id="student-list-add" @click="addStudent">Добавить студента</button>
      </div>
    </div>
    <hr>
    <div class="default-content-box">
      <div class="default-content-list" v-for="value in students" key="">
        <h2 class="default-content-header">{{value.full_name}}</h2>
        <hr class="default-content-hr">
        <p>Возраст: {{value.age}}</p>
        <p>Пол: {{value.sex}}</p>
        <p>Статус: {{value.status}}</p>
        <p>Название группы: {{value.group_name}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "students",
  data() {
    return {
      students: [],
    }
  },
  methods: {
    getStudents() {
      axios.get(import.meta.env.VITE_APP_API + "/user/list", {
        headers: {
          Authorization: "Bearer " + localStorage.getItem("token")
        }
      }).then(r => {
        r.data.forEach((element) => {
          this.reformatStudentsArray(element)
        })
      })
          .catch(e => console.log(e))
    },
    reformatStudentsArray(element) {
      const studentItem = {
        full_name: element['full_name'],
        age: element['age'],
        sex: element['sex'],
        status: element['status'],
        group_name: element['group_name'],
      }
      this.students.push(studentItem)
    },
    addStudent() {
      return;
      axios.post(import.meta.env.VITE_APP_API + "/user/new", {
      }, {
        headers: {
          Authorization: "Bearer " + localStorage.getItem("token")
        }
      }).then(r => {
        console.log(r.data)
      })
          .catch(e => console.log(e))
    }
  },
  beforeMount() {
    this.getStudents()
  }
}
</script>