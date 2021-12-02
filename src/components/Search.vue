<template>
    <div class="search-container">
        <input placeholder="Inserisci un Titolo" v-model.trim="inputText" type="text">
        <button @click.prevent="$emit('search', inputText)">INVIA</button>  
    </div>
</template>

<script>

export default {
  name: 'Search',
  data () {
      return {
          inputText: "",
      }
  }

}
</script>

<style lang="scss">
    .search-container {
        padding: 20px;
        display: flex;
        justify-content: flex-end;
        input {
            height: 30px;
        }
    }
</style>
