<template>
  <div :key="student.id" class="students" v-for="student in students">
    <Student :student="student" />
  </div>
</template>

<script>
import Student from "./Student.vue";
export default {
  name: "Students",
  props: {
    students: Array,
  },
  components: {
    Student,
  },
};
</script>

<style></style>
