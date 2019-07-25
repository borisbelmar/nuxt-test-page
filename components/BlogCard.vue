<template>
    <div class="card">
        <div class="card-image">
            <figure class="image is-16by9">
                <img :src="article.img.url" :alt="article.img.alt">
            </figure>
        </div>
        <div class="card-content">
            <div class="content">
                <h3 class="title">{{article.title}}</h3>
                <p v-if="description">{{article.description.slice(0,140)}}</p>
                <div class="tags" v-if="tags">
                    <a v-for="(tag, index) of article.tags" :key="index" class="tag is-light" href="#">{{tag}}</a>
                </div>
                <p v-if="date">
                    <small>{{article.date}}</small>
                </p>
                <nuxt-link :to="`blog/${article.slug}`">
                    <button class="button is-primary is-fullwidth">Ir al artículo</button>
                </nuxt-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BlogCard',
    props: {
        article: {
            type: Object,
            default: {
                title: 'Título del artículo',
                description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris.',
                img: {
                    url: 'https://picsum.photos/1280/960?random=20',
                    alt: 'Foto artículo'
                }, 
                tags: [],
                content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris.',
                date: "11: 09 PM - 1 Jan 2016",
                slug: "placeholder"
            } 
        },
        tags: {
            type: Boolean,
            default: true
        },
        description: {
            type: Boolean,
            default: true
        },
        date: {
            type: Boolean,
            default: true
        }
    }
}
</script>

<style>

</style>
