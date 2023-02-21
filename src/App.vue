<template>
  <div>
    <button @click="showpopUp = true">Show pop up</button>
    <popUp v-show="showpopUp" @close="CloseEvent"></popUp>

    <Input v-model="name" />
  </div>
</template>

<script>
import popUp from './components/pop-up.vue';
import Input from './components/Input.vue';

export default {
  name: 'App',
  data() {
    return {
      name: '',
      showpopUp: false,
    }
  },
  provide() {
    return {
      username: this.name
    }
  },
  components: {
    popUp,
    Input
  },
  methods: {
    CloseEvent(title) {
      this.showpopUp = false,
        console.log(title);
    }
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
