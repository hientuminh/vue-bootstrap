<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <students></students>
  </div>
</template>

<script>
import Students from '@/components/Students'
export default {
  name: 'Home',
  data () {
    return {
      msg: 'Welcome to Your Vue.js Home App'
    }
  },
  components: {
    'students': Students
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  margin-top: 20px;
}
h1, h2 {
  font-weight: normal;
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
