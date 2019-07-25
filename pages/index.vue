<template>
  <main>
    <section class="hero is-primary is-medium">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">Bienvenido al Sitio NuxtJS de prueba</h1>
          <h2 class="subtitle">Un pequeño sitio para hacer pruebas</h2>
        </div>
      </div>
    </section>
    <section class="section">
      <div class="container">
        <div class="columns">
          <div class="column has-text-centered">
            <div class="content is-large">
              <p>
                "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Facilis earum blanditiis pariatur. 
                Alias architecto hic veniam saepe praesentium neque fugit quasi natus at? Officiis aspernatur, 
                dolores doloribus excepturi sint deleniti."
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="section">
      <div class="container">
        <div class="columns">
          <div class="column">
            <h1 class="title">Artículos del blog</h1>
          </div>
        </div>
        <div class="columns">
          <div class="column" v-for="(item, index) of articles" :key="index">
            <BlogCard :article="item" :description="false" :tags="false" :date="false"/>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import BlogCard from '@/components/BlogCard.vue';
import axios from 'axios';
export default {
  components: {
    BlogCard
  },
  data() {
    return {
      articles: []
    }
  },
  async mounted() {
    await axios.get('./articles.json')
    .then(res => {
      this.articles = res.data.slice(0,3);
    })
  },
  head () {
    return {
      title: 'Sitio web de prueba con NuxtJS',
      meta: [
        { hid: 'description', name: 'description', content: 'Descripción para que mi sitio se rankee en google' }
      ]
    }
  }
}
</script>

<style>

</style>
