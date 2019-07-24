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
              <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Facilis earum blanditiis pariatur. Alias architecto hic veniam saepe praesentium neque fugit quasi natus at? Officiis aspernatur, dolores doloribus excepturi sint deleniti.</p>
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
            <BlogCard :content="item" />
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import BlogCard from '@/components/BlogCard.vue';
export default {
  components: {
    BlogCard
  },
  data() {
    return {
      articles: [
        { 
          title: 'Artículo 1',
          img: {
            url: 'https://bulma.io/images/placeholders/1280x960.png',
            alt: 'Foto artículo 1'
          },
          tags: ['tag1', 'tag2'], 
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris.',
          date: '11:09 PM - 1 Jan 2016',
          link: 'articulo-1'
        },
        { 
          title: 'Artículo 2',
          img: {
            url: 'https://bulma.io/images/placeholders/1280x960.png',
            alt: 'Foto artículo 2'
          },
          tags: ['tag1', 'tag2', 'tag3'], 
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris.',
          date: '11:09 PM - 1 Jan 2016',
          link: 'articulo-2'
        },
        { 
          title: 'Artículo 3',
          img: {
            url: 'https://bulma.io/images/placeholders/1280x960.png',
            alt: 'Foto artículo 3'
          },
          tags: ['tag1'], 
          content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris.',
          date: '11:09 PM - 1 Jan 2016',
          link: 'articulo-3'
        }
      ]
    }
  }
}
</script>

<style>

</style>
