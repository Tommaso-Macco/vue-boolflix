<template>
  <div class="film-box">
      <h1>{{details.title}}</h1>
      <h5>{{details.original_title}}</h5>
      <!-- <h5>{{details.original_language}}</h5> -->
      <div v-if="details.original_language === 'it'"> 
          <img src="./../assets/italy.png" alt="">
      </div>
      <div v-else>
          <img src="./../assets/english.png" alt="">
      </div>
      <h5>{{details.vote_average}}</h5>
  </div>
</template>

<script>


export default {
  name: 'App',
  props: {
      details: Object,
  }
}
</script>

<style lang="scss">

  .film-box {
    background-color: red;
    margin: 20px;
    width: calc(100% / 5);
  }

</style>
