<template>
  <div>
    <Header></Header>
    <br />

    <div
      name="example"
      v-if="isVisible"
      style="
        top: 200px;
        left: 320px;
        width: 800px;
        height: 600px;
        position: -webkit-sticky;
        position: sticky;
        top: 20px;
      "
    >
      <div>
        <iframe
          width="800"
          height="600"
          v-bind:src="trailerLink"
          frameborder="0"
          allowfullscreen
        ></iframe>
      </div>
      <div>
        <button
          @click.prevent="toggleModal()"
          class="btn btn-primary btn-block"
        >
          Close
        </button>
      </div>
    </div>

    <div class="container">
      <form v-on:submit.prevent="search">
        <img src="../assets/buscar.jpg" alt="" width="20%" />
        <br />
        <br />
        <div class="form-group">
          <label>Busca tu pelicula favorita</label>
          <br />
          <br />

          <input
            type="text"
            class="form-control"
            id="exampleInputEmail1"
            aria-describedby="emailHelp"
            placeholder="Nombre de la pelicula"
            v-model="title"
          />
        </div>
        <br />

        <input type="submit" class="fadeIn fourth" value="Buscar" />
      </form>
      <br />
      <br />
    </div>

   
    <div class="container col-md-10" v-if="movies.length > 0">
      <table class="table table-bordered">
        <thead>
          <tr>
            <th>Poster</th>
            <th>Película</th>
            <th>Sinopsis</th>
            <th>Fecha Estreno</th>
            <th>Trailer</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="peli of movies" :key="peli.id">
            <td>
              <img
                v-bind:src="`https://image.tmdb.org/t/p/w500/${peli.poster_path}`"
                height="200"
                width="150"
              />
            </td>
            <td>{{ peli.title }}</td>
            <td>{{ peli.overview }}</td>
            <td>{{ peli.release_date }}</td>
            <td>
              <button v-on:click="watchTrailer(peli.id)" class="btn btn-primary">
                Trailer
              </button>
            </td>
            <!-- <td>
              <button v-on:click="getOneTask(peli.id)" class="btn btn-primary">
                Edit
              </button>
            </td> -->
          </tr>
        </tbody>
      </table>
    </div>
    <br />
    <br />
    <br />
    <br />

    <Footer></Footer>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
//import axios from "axios";

class Movie {
  constructor(
    adult,
    backdrop_path,
    genre_ids,
    id,
    original_language,
    original_title,
    overview,
    popularity,
    poster_path,
    release_date,
    title,
    video,
    vote_average,
    vote_count
  ) {
    this.adult = adult;
    this.backdrop_path = backdrop_path;
    this.genre_ids = genre_ids;
    this.id = id;
    this.original_language = original_language;
    this.original_title = original_title;
    this.overview = overview;
    this.popularity = popularity;
    this.poster_path = poster_path;
    this.release_date = release_date;
    this.title = title;
    this.video = video;
    this.vote_average = vote_average;
    this.vote_count = vote_count;
  }
}

class Trailer {
  constructor(id, results) {
    this.id = id;
    this.results = results;
    this.movieId = "";
  }
}

export default {
  name: "Buscar",
  data() {
    return {
      title: "",
      movie: new Movie(),
      movies: [],
      isVisible: false,

      trailers: new Trailer(),
      trailerLink: "",
    };
  },
  components: {
    Footer,
    Header,
  },
  methods: {
    
    mounted: function () {},
  },
};
</script>

<style lang="postcss" scoped>
.overlay {
  display: flex;
  position: fixed;
  z-index: 1;
  width: 100%;
  height: 100%;
  position: absolute;
  left: 25%;
  top: 25%;
  margin-left: -150px;
  margin-top: -150px;
  background-color: rgb(0, 0, 0);
  background-color: rgba(0, 0, 0, 0.4);
}
</style>