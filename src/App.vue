<template>
  <Parent></Parent>
  <Childs></Childs>
</template>

<script>
import Childs from './components/Childs.vue';
import Parent from './components/Parent.vue';
export default {
  name: 'App',
  data() {
    return {
      name: '',
    }
  },
  components: {
    Childs,
    Parent
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

div {
  margin: 20px;
  padding: 3px;
  background-color: aliceblue;

}
</style>
