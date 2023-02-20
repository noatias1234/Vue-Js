<template>
  <div>
    <h2>Computed full name - {{ fullName }}</h2>
    <h2>Computed total - {{ total }}</h2>
    <button @click="changeFullName">Change full name</button>
    <h2 v-for="item in expensiveItems" :key="item.id">
      {{ item.title }} {{ item.price }}</h2>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  data() {
    return {
      firstName: 'Sam',
      lastName: 'David',
      items: [
        {
          id: 1,
          title: 'TV',
          price: 300
        }, {
          id: 2,
          title: 'Phone',
          price: 1000
        },
        {
          id: 1,
          title: 'Laptop',
          price: 500
        },
      ]
    }
  },
  methods: {
    changeFullName() {
      this.fullName = 'Nate Rosen'
    }
  },
  computed: { //Computed properties are automaticly recalculated if their dependencies change , Perfer if we have a big logic 
    fullName: {
      get() {
        return this.firstName + " " + this.lastName
      },
      set(value) {
        const names = value.split(' ');
        this.firstName = names[0];
        this.lastName = names[1];
      }
    },
    total() {
      return this.items.reduce((total, curr) => (total = total + curr.price), 0);
    },
    expensiveItems() {
      return this.items.filter(item => item.price > 400);
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
