<template>
    <div class="card">
        <div class="card-image">
            <figure class="image is-16by9">
                <img :src="content.img.url" :alt="content.img.alt">
            </figure>
        </div>
        <div class="card-content">
            <div class="content">
                <h3 class="title">{{content.title}}</h3>
                <p>{{content.content}}</p>
                <div class="tags">
                    <a v-for="(tag, index) of content.tags" :key="index" class="tag is-primary" href="#">{{tag}}</a>
                </div>
                <p>
                    <small>{{content.date}}</small>
                </p>
                <a :href="content.link">
                    <button class="button is-primary is-fullwidth">Ir al artículo</button>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BlogCard',
    props: {
        content: Object
    }
}
</script>

<style>

</style>
