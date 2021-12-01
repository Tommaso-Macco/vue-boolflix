<template>
    <main>
        <div>
            MAIN
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
import axios from 'axios'

export default {
  name: 'App',
  components: {
    FilmSelect
  },

  data () {
      return {
          apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=aaa18a9ee5586d7e9799e5572ca9d58f&query=ritorno+al+futuro",
          filmList: []
      }
  },

  created () {
      this.getFilm();
  },

  methods: {
      getFilm() {
          axios
          .get(this.apiUrl)
          .then((item) => {
              this.filmList = item.data.results,
              console.log(this.filmList);
          })
      },
  },
}
</script>

<style lang="scss">
    main {
        min-height: calc(100vh - 100px);
        background-color: grey;
    }
</style>
