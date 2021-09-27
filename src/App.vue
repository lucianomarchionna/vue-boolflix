<template>
  <div id="app">
    <Header @showSearch="searchFilm"/>
    <Main :films="films"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from "axios"

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
        return{
            films: [],
            APIUrl: "https://api.themoviedb.org/3/search/",
            APiKey: "4c19bac9940068072a0fc53f656cdaac",
            input: "",
        } 
    },
    methods: {
        takeFilms(){
            axios.get(this.APIUrl + "movie?api_key=" + this.APiKey + "&query=" + this.input)
            .then((res) =>{
                this.films = res.data.results;
            })
            .catch((error) =>{
                console.log(error);
            });
        },
        searchFilm(inputText){
            this.input = inputText;
            if(this.input!=""){
                this.takeFilms();
            }
        },
        created(){
            this.takeFilms();
        }
    }
}
</script>

<style lang="scss">
@import "style/generals";

</style>
