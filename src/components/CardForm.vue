<template>
  <div class="card-form">
    <h2>Kartu Rencana Studi</h2>
    <input type="text" v-model="courseName" placeholder="Masukkan nama mata kuliah">
    <button @click="addCourse">Tambah Mata Kuliah</button>
    <div v-if="courses.length > 0">
      <h3>Daftar Mata Kuliah:</h3>
      <ul>
        <li v-for="(course, index) in courses" :key="index">{{ course }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      courseName: '',
      courses: []
    };
  },
  methods: {
    addCourse() {
      if (this.courseName.trim() !== '') {
        this.courses.push(this.courseName);
        this.courseName = '';
      }
    }
  }
};
</script>

<style scoped>
.card-form {
  width: 300px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

input[type="text"] {
  width: calc(100% - 20px);
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  width: 100%;
  padding: 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin-bottom: 5px;
}
</style>
