<template>
  <div id="app">
    <h1>Student directory</h1>
    <StudentForm on-add:student="addStudent"/>
    <StudentTable v-bind:students="students"/>
  </div>
</template>

<script>
import StudentTable from './components/StudentTable.vue'
import StudentForm from './components/StudentsForm.vue'

export default {
  name: 'app',
  components: {
    StudentTable,
    StudentForm
  },
  data() {
    return {
      students: [
        {
        id: 1,
        name: 'Donatas',
        email: 'donatas@gmail.com'
        },
        {
        id: 2,
        name: 'Augustinas',
        email: 'augis@gmail.com'
        }
      ]
    }
  },
  methods: {
    addStudent(student) {
      let lastId = this.students[this.students.length -1].id;
      let id = lastId +1;
      let newStudent =  {... student, id}
      this.students.push(newStudent);
    }
  }
}
</script>

<style>
body {
    background-image: url('assets/BG2.jpg');
    background-size: cover;
}
h1 {
  color: white;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 800px;
  margin: 0 auto;
}
</style>
