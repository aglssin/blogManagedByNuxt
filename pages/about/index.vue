<template>
    <section id="about-page">
        <h1>{{title}}</h1>
        <p>{{content}}</p>
    </section>
</template>
<script>
export default {
    asyncData(context) {
        return context.app.$storyapi.get('cdn/stories/about',{
            version: 'draft',
    }).then(res=>{
        return{
            title: res.data.story.content.title,
            content: res.data.story.content.content
        }
    })
    }
}
</script>
<style>
    #about-page{
        width: 500px;
        margin: auto;
        max-width: 80%;
    }
    #about-page p{
        white-space: pre-line;
    }
</style>
