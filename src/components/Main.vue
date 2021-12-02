<template>
    <main> 
        <Search @search="searching"/>
        <div class="film-container">
            <FilmSelect
                v-for="film, i in filmList"
                :key="i"
                :details="film"
            />
        </div>
    </main>
</template>

<script>
import FilmSelect from '../components/FilmSelect.vue'
import Search from '../components/Search.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    FilmSelect,
    Search
  },

  data () {
      return {
          apiUrl: "",
          filmList: [],
          searchText: "",
          apiUrlFix: ""
          /* https://api.themoviedb.org/3/search/movie?api_key=aaa18a9ee5586d7e9799e5572ca9d58f&query= */
      };
  },

  created () {
    //   this.getFilm();
  },

  methods: {
      searching (text) {
          this.searchText = text;
        //   console.log(this.searchText);
        this.apiUrl = 'https://api.themoviedb.org/3/search/movie?api_key=aaa18a9ee5586d7e9799e5572ca9d58f&query=' + this.searchText;
        // console.log(this.apiUrl);
        axios
        .get(this.apiUrl)
        .then((object) => {
            this.filmList = object.data.results;
            console.log(this.filmList);
        })
          
          
      }
  },
}
</script>

<style lang="scss">

    main {
        min-height: calc(100vh - 100px);
        background-color: grey;
        .film-container {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
    }
</style>
