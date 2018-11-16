<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <p>{{ secondMessage }}</p>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Goodbye to Vue.js!",
      secondMessage: "i am the second message"
    };
  },
  created: function() {},
  methods: {},
  computed: {}
};
</script>
