<template>
    <main>
        <h2>FILM</h2>
        <div class="container">
            <div v-for="(film, index) in films" :key="index" class="filmSelected">
                <Film :key="index"  :filmSelected="film" />
            </div>
        </div>
    </main>
</template>

<script>
import Film from "./Film.vue"
export default {
    name: 'Main',
    props: ["films"],
    components:{
        Film,
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/generals";
main{
    width: 100%;
    height: 100%;
    min-height: 92vh;
    background-color: $secondary-color;

    h2{
        color: red;
    }

    .container{
        width: 90%;
        height: 100%;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
}
</style>