<template>
  <form @submit.prevent="onSubmit" class="seaarch-form">
    <input type="text" v-model="text" placeholder="Search Jokes..." />
    <input type="submit" value="Search Jokes" />
  </form>
</template>

<script>
export default {
  name: "SearchJokes",

  data() {
    return {
      text: ""
    };
  },

  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    }
  }
};
</script>

<style lang="scss" scoped>
.seaarch-form {
  width: 100%;

  input[type="text"] {
    border: 1px solid #ccc;
    padding: 7px;
    -webkit-appearance: none;
    appearance: none;
    outline: none;
    background: #fff;

    &:focus {
      border: 1px solid #000;
    }
  }

  input[type="submit"] {
    background: #000;
    border: 0;
    padding: 7px;
    color: #fff;
    margin-top: 10px;
    cursor: pointer;
    outline: none;
  }
}
</style>
