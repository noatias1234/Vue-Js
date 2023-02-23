<template>
  <TemplateRef></TemplateRef>
</template>

<script>
import TemplateRef from "./components/TemplateRef.vue"
export default {
  name: 'App',
  data() {
    return {
      name: '',
    }
  },
  components: {
    TemplateRef
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
