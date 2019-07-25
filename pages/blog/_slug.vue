<template>
  <main>
    <section class="section">
      <div class="container">
        <article class="content">
            <h1>Artículo</h1>
            <p>{{$route.params.slug}}</p>
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
      article: null
    }
  }
}
</script>
