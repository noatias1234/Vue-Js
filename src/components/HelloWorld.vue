<template>
  <div>
    <div>
      <h2>Volume tracker (0-20)</h2>
      <h3>Current volume - {{ volume }}</h3>
      <button @click="this.volume += 2">Increase volume</button>

    </div>
    <div>
      <input type="text" v-model="movie" />
      <input type="text" v-model="movieInfo.title" />
      <input type="text" v-model="movieInfo.actor" />
    </div>
    <div>
      <button @click="moviesList.push('Wonderwoman')">Movie</button>
    </div>


  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  data() {
    return {
      volume: 0,
      movie: '',
      movieInfo: {
        title: '',
        actor: ''
      },
      moviesList: []
    }
  },
  methods: {},
  computed: {},
  watch: { // watch for a change in value , in this way we can react to data changes 
    volume(newValue, oldValue) {
      if (oldValue < newValue && newValue === 16)
        alert("Listening to a high volume for a long time may damage your hearing");
    },
    movie: {
      handler(newValue) {
        console.log('Calling API with movie name = ', { newValue })
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(`Calling API with movie title = ${newValue.title} an actor = ${newValue.actor}`)
      },
      deep: true
    },
    moviesList: {
      handler(newValue) {
        console.log(`update list ${newValue}`);
      },
      deep: true
    }
  }
}
</script>


<style scoped>
h3 {
  margin: 40px;
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
