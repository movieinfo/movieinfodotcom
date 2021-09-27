<template>
  <div>
    <Header></Header>
    <div class="container">
      <form v-on:submit.prevent="search">
        
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
            
          />
        </div>
        <br />

        <input type="submit" class="fadeIn fourth" value="Buscar" />
      </form>
      <br />
      <br />
    </div>

    <div class="container col-md-10" >
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
          <tr >
            <td>
              <img
                
                height="200"
                width="150"
              />
            </td>
            <td>titulo </td>
            <td>sinopsis </td>
            <td>lanzamiento </td>
            <td>
              <button >
                Trailer
              </button>
            </td>
            
          </tr>
        </tbody>
      </table>
    </div>
   
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
export default {
  components: {
    Header,
    Footer
  },
};
</script>