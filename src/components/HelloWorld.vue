<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="show1=true">button1</button>
    <button @click="show2=true">button2</button>
    <button @click="show3=true">button3</button>

    <hw1 v-if="show1"></hw1>
    <hw2 v-if="show2"></hw2>
    <hw3 v-if="show3"></hw3>
  </div>
</template>

<script>
import hw2 from '../components/HelloWorld2'
import hw3 from '../components/HelloWorld3'
const hw1 = () => import(/* webpackChunkName: "h-w1" */ '../components/HelloWorld1')

export default {
  name: 'HelloWorld',
  components: {
    hw1, hw2, hw3
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      show1: false,
      show2: false,
      show3: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
