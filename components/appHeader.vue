<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>

    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>

      <li>
        <nuxt-link to="/jokes">Jokes</nuxt-link>
      </li>

      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "AppHeader"
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
  padding-bottom: 16px;
  border-bottom: 1px dotted #ccc;

  @media (max-width: 600px) {
    flex-direction: column;
  }

  .title {
    font-size: 3rem;
    color: #526488;
  }

  ul {
    display: flex;
    align-items: center;

    @media (max-width: 600px) {
      margin-top: 10px;
    }
  }

  a {
    display: inline-block;
    background: #333;
    color: #fff;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
  }
}
</style>
