<template>
  <div>
    <SearchJokes v-on:search-text="searchText" />

    <div v-if="!jokes.length" style="margin-top: 16px;">Loading...</div>

    <Joke
      v-for="joke in jokes"
      :key="joke.id"
      :id="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>

<script>
import axios from "axios";
import Joke from "@/components/joke";
import SearchJokes from "@/components/searchJokes";

export default {
  components: {
    Joke,
    SearchJokes
  },

  data() {
    return {
      jokes: []
    };
  },

  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res = await axios.get("https://icanhazdadjoke.com/search", config);

      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  },

  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: "application/json"
        }
      };

      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        );

        this.jokes = res.data.results;
      } catch (err) {
        console.log(err);
      }
    }
  },

  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes"
        }
      ]
    };
  }
};
</script>
