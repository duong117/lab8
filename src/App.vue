<template>
  <div id="app">
    <NewStudentForm v-on:student-added="newStudentAdded"></NewStudentForm>
    <StudentTable v-bind:students="students"></StudentTable>
    <StudentMessage></StudentMessage>
  </div>
</template>

<script>
import NewStudentForm from './components/NewStudentForm.vue'
import StudentTable from'./components/StudentTable.vue'
import StudentMessage from'./components/StudentMessage.vue'


export default {
  name: 'app',
  data(){
    return{
      students:[]
    }
  },
  components: {
    NewStudentForm,
    StudentTable,
    StudentMessage
  },
  methods:{
    newStudentAdded(student){
      this.students.push(student)
      this.students.sort(function (s1,s2) {
        return s1.name.toLowerCase()<s2.name.toUpperCase() ?-1:1
      })
    }
  }
}
</script>

<style>

</style>
