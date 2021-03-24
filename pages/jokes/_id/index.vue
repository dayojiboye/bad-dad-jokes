<template>
  <div>
    <nuxt-link to="/jokes">Back To Jokes</nuxt-link>

    <h2 v-if="!joke">Loading...</h2>

    <h2 v-if="joke">{{ joke }}</h2>

    <hr>

    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: null
    };
  },

  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );

      this.joke = res.data.joke;
    } catch (err) {
      console.log(err);
    }
  }
};
</script>

<style></style>
