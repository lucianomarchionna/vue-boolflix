<template>
  <header>
    <h2>BOOLFLIX</h2>
    <div>
      <input type="text" placeholder="Cerca un film">
      <button
        type="submit"
        class="search"
        @click.prevent="$emit('performSearch', inputText)"
      >CERCA</button>
      <button
        type="submit"
        class="reset"
        @click.prevent="$emit('performSearch', inputText)"
      >RESET</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/generals";

header{
  width: 100%;
  height: 8vh;
  background-color: $primary-color;
  display: flex;
  justify-content: space-between;
  align-items: center;

  h2{
    color: $tertiary-color;
    font-size: 20px;
    margin-left: 50px;
  }
  div{
    input{
      padding: 5px 10px;
      font-size: 15px;
    }
    .search{
      background-color: $tertiary-color;
      padding: 7px 10px;
    }
    .reset{
      background-color:white;
      margin-right: 50px;
      padding: 7px 10px;
    }
  }
}
</style>
