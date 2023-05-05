<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
      <h2>{{ description }}</h2>
      <h3>Student: <span ref="studentName">{{ student.name }}</span></h3>
      <h4>Semester: {{ student.semester }} {{ student.year }}</h4>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
    data() {
      return {
          description: "This is a VueJS application",
          student: {
              name: "Bakyt Tursunbekov",
              semester: "Spring semester",
              year: "2023"
          }
      }
    },
    created() {
      document.title = this.msg
      let colors = ["red", "blue", "black", "green", "cyan"];
      let i = 0;
      setInterval(() => {
          this.$refs.studentName.style.color = colors[i];
          if (i === (colors.length - 1))
              i = 0;
          else
              i++;
      }, 500)
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
