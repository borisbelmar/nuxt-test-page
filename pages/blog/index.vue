<template>
    <main>
        <section class="section">
            <div class="container">
                <div class="columns">
                    <div class="column">
                        <h1 class="title">Blog de prueba</h1>
                    </div>
                </div>
                <div class="columns is-multiline">
                    <div class="column is-6 is-offset-3" v-for="(item, index) of articles" :key="index">
                        <BlogCard :article="item"/>
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
      this.articles = res.data;
    })
  }
}
</script>