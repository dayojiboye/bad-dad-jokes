<template>
  <nuxt-link :to="'jokes/' + id">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: "Joke",
  props: {
    joke: String,
    id: String
  }
};
</script>

<style>
.joke {
  padding: 16px;
  border: 1px dotted #ccc;
  margin: 16px 0;
  cursor: pointer;
}
</style>
