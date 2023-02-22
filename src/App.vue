<template>
  <NamesList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NamesList>
</template>

<script>

import NamesList from './components/NamesList.vue';
export default {
  name: 'App',
  data() {
    return {
      name: '',
    }
  },
  components: {
    NamesList
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
