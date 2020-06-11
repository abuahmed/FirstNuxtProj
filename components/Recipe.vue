<template>
<nuxt-link :to="'/recipes/' + id">
    <article class="post-preview">
        <div class="post-preview-thumbnail" 
        :style="{backgroundImage: 'url(' +  thumbnail + ')'}">
        </div>
        <div class="post-preview-content">
        <h1>{{ title }}</h1>
        <p>{{ previewText }}</p>
        </div>
    </article>
</nuxt-link>
</template>

<script>
export default {
    props:["title","thumbnail","previewText","id"]
    
}
</script>

<style  scoped>
a{
    text-decoration: none;
    color: black;
}
.post-preview{
    /* box-sizing: border-box; */
    width: 90%;
    /* padding: 8px; */
    /* border: 1px solid #ccc; */
    /* box-shadow: 0 2px 2px #aaa; */
    margin: 1rem;
    height: 20rem;
    border-radius: 3px;
    box-shadow: 1px 1px 5px 1px rgba(0,0,0,0.5);
}

.post-preview-thumbnail{
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 10rem;
}
.post-preview-content{
    text-align: center;
    padding:1rem;
}
@media (min-width: 35rem) {
    .post-preview{
        width: 25rem;
    }
}
</style>