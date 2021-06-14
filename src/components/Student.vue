<template>
  <div class="student">
    <p class="name">Name: {{ student.name }}</p>
    <p class="age">Age: {{ student.age }}</p>
    <p class="course">Course: {{ student.course }}</p>
  </div>
</template>

<script>
export default {
  name: "Student",
  props: {
    student: Object,
  },
};
</script>

<style>
.student {
  width: 31.25em;
  padding: 1em;
  border: 2px solid grey;
  margin-bottom: 20px;
  border-radius: 10px;
  font-weight: bold;
}

.name {
  color: goldenrod;
}
.age {
  color: steelblue;
}
.course {
  color: maroon;
}
</style>
