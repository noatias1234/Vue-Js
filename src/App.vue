<template>
  <Demo1 />
  <Demo2 />
</template>

<script>
import Demo1 from './CompositionApi/components/Demo1.vue';
import Demo2 from './CompositionApi/components/Demo2.vue';
export default {
  name: 'App',
  data() {
    return {
      name: '',
    }
  },
  components: {
    Demo1,
    Demo2
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
