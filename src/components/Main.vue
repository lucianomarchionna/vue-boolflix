<template>
    <main>
        <Film/>
    </main>
</template>

<script>
import axios from "axios"
import Film from "./Film.vue"
export default {
    name: 'Main',
    components:{
        Film,
    },
    data(){
        return{
            films: [],
            APIUrl: "https://api.themoviedb.org/3/movie/550?api_key=4c19bac9940068072a0fc53f656cdaac",
        }
    },
    methods(){
        axios.get(this.APIUrl)
        .then((res) =>{
            this.films = res.data.response;
        })
        .catch((error) =>{
            console.log(error);
        });
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
}
</style>