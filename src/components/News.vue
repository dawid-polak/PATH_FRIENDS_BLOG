<template>
    <div class="news--content">
        <div class="news--content-title">
            <h1>Nowości:</h1>
        </div>
        <div class="news--content-block">

            <router-link to="about">

                <IconBlogPost/>
            </router-link>
            
        </div>
    </div>
</template>
<script>
import IconBlogPost from './IconBlogPost.vue'

export default {
    data() {
        return {};
    },
    components: {
        IconBlogPost
    }
}

</script>
<style scoped lang="scss">



.news--content-title {
    width: 80vw;
    margin: auto;
    margin-top: 75px;
}

.news--content-block {
    width: 80vw;
    margin: auto;
    display: flex;
    flex-flow: row wrap;
    gap: 30px;
    justify-content: space-around;
}

</style>