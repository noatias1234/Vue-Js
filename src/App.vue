<template>
  <button @click="activeTab = 'TabA'">TAB A</button>
  <button @click="activeTab = 'TabB'">TAB B</button>
  <button @click="activeTab = 'TabC'">TAB C</button>


  <!-- Instead of that 
  <TabA v-if="activeTab === 'TabA'" />
  <TabB v-if="activeTab === 'TabB'" />
  <TabC v-if="activeTab === 'TabC'" /> -->

  <!-- Do That -->
  <component :is="activeTab" />
</template>

<script>

import TabA from "./components/TabA.vue"
import TabB from "./components/TabB.vue"
import TabC from "./components/TabC.vue"

export default {
  name: 'App',
  data() {
    return {
      name: '',
      activeTab: 'TabA'
    }
  },
  components: {
    TabA,
    TabB,
    TabC
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
