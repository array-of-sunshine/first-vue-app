<template>
  <div class="home">
    <h4>this is what shows up in chrome</h4>
    <h1>{{ message }}</h1>
    <p>{{ secondMessage }}</p>
    <p>{{ name }}</p>
    <!-- <p>reviewer: {{ reviews[0].reviewer }} rating: {{ reviews[0].rating }} text: {{ reviews[0].text }}</p> -->
    <!-- <h3 v-for="review in reviews">{{ review }}</h3> -->
    <ol>
      <li v-for="review in reviews" v-on:click="removeReview(review)" v-if="isPositive(review)">reviewer: {{ review.reviewer }} rating: {{ review.rating }} text: {{ review.text }}</li>
    </ol>

    <!-- someone message:<input type="text" v-model="reviews[2].text"> -->
    <p>rating:<input type="text" v-model="newReview.rating"></p>
    <p>reviewer:<input type="text" v-model="newReview.reviewer"></p>
    <p>text:<input type="text" v-model="newReview.text"></p>
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
      ],
      newReview: {rating: "", reviewer: "", text: ""}
    };
  },
  created: function() {},
  methods: {
    addReview: function() {
      console.log('adding the review...');
      if (this.newReview.text) {
        this.reviews.push(this.newReview);
        // reset newReview to it's original state
        this.newReview = {rating: "", reviewer: "", text: ""};
      }
    },
    removeReview: function(inputReview) {
      console.log('removng the the review');
      console.log(inputReview);
      // find the index of inputReview
      var index = this.reviews.indexOf(inputReview);
      // splice something something
      this.reviews.splice(index, 1);
    },
    isPositive: function(inputReview) {
      console.log('checking to see if the review is positive');
      // how can i tell if a review is positive?
      // check and see if the review's text has the string 'bad' in it
      return !inputReview.text.includes('bad');
      // if (inputReview.text.includes('bad')) {
      //   // don't show it
      //   return false;
      // } else {
      //   // do show it
      //   return true;
      // }
    }
  },
  computed: {}
};
// user clicks a button
// runs a function
// function takes some data
// puts the data in the array


// to complete task
// click on a particular task which runs a function
// somehow figure out which task the user clicked on
// remove that element from the array
</script>
