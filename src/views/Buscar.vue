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