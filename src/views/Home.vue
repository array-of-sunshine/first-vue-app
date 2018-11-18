<template>
  <div class="home">
    <h4>this is what shows up in chrome</h4>
    <h1>{{ message }}</h1>
    <p>{{ secondMessage }}</p>
    <p>{{ name }}</p>
    <!-- <p>reviewer: {{ reviews[0].reviewer }} rating: {{ reviews[0].rating }} text: {{ reviews[0].text }}</p> -->
    <!-- <h3 v-for="review in reviews">{{ review }}</h3> -->
    <ol>
      <li v-for="review in reviews">reviewer: {{ review.reviewer }} rating: {{ review.rating }} text: {{ review.text }}</li>
    </ol>

    someone message:<input type="text" v-model="reviews[2].text">
    <p><button v-on:click="addReview()">click here to add a review to the screen</button></p>
  </div>
</template>

<style>
</style>

<script>

export default {
  data: function() {
    return {
      message: "Goodbye to Vue.js!",
      secondMessage: "i am the second message",
      name: "jamie",
      reviews: [
        {rating: 5, reviewer: "billybob", text: "that sure was some good pancakes"},
        {rating: 3, reviewer: "betsy-sue", text: "darn tootin coffee"},
        {rating: 5, reviewer: "sherman", text: "what excellent tea, especially green tea"}
      ]
    };
  },
  created: function() {},
  methods: {
    addReview: function() {
      console.log('adding the review...');
      var newReview = {rating: 1, reviewer: "jethro", text: "darn tootin"};
      this.reviews.push(newReview);
    }
  },
  computed: {}
};
// user clicks a button
// runs a function
// function takes some data
// puts the data in the array
</script>
