<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h2>Name:</h2>
    <input v-model="name" type="text" />
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'home',
  components: {
    HelloWorld,
  },
  computed: {
    name: {
      set(value) {
        this.$store.dispatch('updateName', value);
      },
      get() {
        return this.$store.state.name;
      },
    },
  },
};
</script>
