<template>
  <div class="hello">
    <h1>{{ message }}</h1>
    <button @click="changeStatus">Click</button>
    <app-landing></app-landing>
  </div>
</template>

<script>

import Landing from './LandingComponent.vue';

export default {
  name: "HelloWorld",
  components: {
    'app-landing': Landing
  },
  data: function() {
    return {
      message: 0
    }
  },
  methods: {
    changeStatus: function() {
      this.message++;
    }
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
