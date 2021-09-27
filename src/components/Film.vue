<template>
    <div class="single-film">
        <div class="film">
            <img :src="`https://image.tmdb.org/t/p/w342${FilmSearched.poster_path}`" :alt="FilmSearched.title">
            <div class="features">
                <h4><strong>Titolo del film:</strong> {{FilmSearched.title}}</h4>
                <h4><strong>Titolo originale:</strong> {{FilmSearched.original_title}}</h4>
                <h4><strong>Voto:</strong> {{FilmSearched.vote_average}}</h4>
                <h4><strong>Lingua originale:</strong> {{FilmSearched.original_language}}</h4>
            </div>
        </div>
    </div>
</template>
<script>
export default {
  name: 'Film',
  props: ['FilmSearched']
}
</script>

<style lang="scss">
@import "../style/generals";
.single-film{
    width: 200px;
    height: 300px;
    .film{
        width: 100%;
        height: 100%;
        position: relative;
    }
}
</style>
