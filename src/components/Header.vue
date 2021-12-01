<template>
  <header>
      <h1>BOOLFLIX</h1>
      <input type="text" placeholder="Inserci Il Titolo Di Un Film">
  </header>
</template>

<script>

export default {
  name: 'App',
  components: {
    
  }
}
</script>

<style lang="scss">
    header {
        height: 100px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: black;
        padding: 0 40px;
        h1 {
            color: red;
            font-weight: 1000;
        }
        input {
            height: 30px;
        }
    }
</style>
