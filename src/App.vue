<template>
  <Card>
    <template v-slot:header>
      <h3>HEADER</h3>
    </template>

    <template v-slot:default>
      <img src="https://picsum.photos/200">
    </template>

    <template v-slot:footer>
      <button>BUTTON</button>
    </template>
  </Card>
</template>

<script>
import Card from "./components/Card.vue"

export default {
  name: 'App',
  data() {
    return {
      name: '',
    }
  },
  components: {
    Card
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
</style>
