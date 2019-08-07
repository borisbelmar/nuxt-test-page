<template>
  <main>
    <section class="section">
      <div class="container">
        <article class="content">
          <div class="columns">
            <div class="column is-8 is-offset-2">
              <h1 class="title">{{article.title}}</h1>
              <h4 class="subtitle">{{article.description}}</h4>
              <p>
                  <small>Publicado en: {{article.date}}</small>
              </p>
              <div class="tags">
                  <a v-for="(tag, index) of article.tags" :key="index" class="tag is-light" href="#">{{tag}}</a>
              </div>
              <figure class="image is-16by9">
                  <img :src="article.img.url" :alt="article.img.alt">
              </figure>
              <p>{{article.content}}</p>
            </div>
          </div>
        </article>
      </div>
    </section>
  </main>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      article: {
        img: {
          url: "",
          alt: ""
        }
      }
    }
  },
  async created() {
    const articles = await axios.get('../articles.json');
    const element = articles.data.filter(item => item.slug === this.$route.params.slug)[0];
    if(element == null) {
      $nuxt.error({ statusCode: 404, message: 'Lo que estabas buscando no está aquí'});
    } else {
      this.article = element;
    }
  },
  head () {
    return {
      title: this.article.title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: this.article.description }
      ]
    }
  },
}
</script>
