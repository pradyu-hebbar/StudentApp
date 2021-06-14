<template>
  <div class="search">
    <input
      type="text"
      v-model="search"
      id="search"
      placeholder="Search for students"
    />
    <i class="fas fa-search"></i>
  </div>
  <div v-if="filteredStudents.length > 0">
    <Students :students="filteredStudents" />
  </div>
  <div v-else class="err">No Results Found!</div>
</template>

<script>
import Students from "./components/Students.vue";
export default {
  name: "App",
  components: { Students },
  data() {
    return {
      students: [
        {
          name: "Karthik",
          age: 19,
          course: "maths, science, english",
          id: 1,
        },
        {
          name: "Suman",
          age: 16,
          course: "maths, science, english, sanskrit",
          id: 2,
        },
        {
          name: "Janhavi",
          age: 20,
          course: "maths, science, kannada",
          id: 3,
        },
        {
          name: "Raghu",
          age: 22,
          course: "maths, english, hindi",
          id: 4,
        },
      ],
      search: "",
    };
  },
  computed: {
    filteredStudents() {
      const filteredStudents = this.students.filter((student) =>
        student.name.toLowerCase().includes(this.search.toLowerCase())
      );

      return filteredStudents;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap");

#app {
  font-family: "Poppins", sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-direction: column;
}

#search {
  padding: 1em;
  font-family: inherit;
  width: 200px;
  margin-bottom: 30px;
}

::placeholder {
  font-size: 1rem;
}

.search {
  display: flex;
  justify-content: space-between;
}

i {
  font-size: 1.3rem;
  position: relative;
  top: 14.5px;
  right: 1.25em;
}
.err {
  color: red;
  font-size: 1.3rem;
}
</style>
