<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <div class="menu-item">
          <h1><em>break down</em></h1>
        </div>
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item">
          <p>categories</p>
        </div>
      </router-link>
      <router-link to="/skillset">
        <div class="menu-item">
          <p>skillset ({{this.$root.$data.skillset.length}} moves)</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>

<script>


</script>



<style>
* {
  box-sizing: border-box;
}

body {
    font-family: 'Karla', sans-serif;
    background-color: #f5f7fa; /*find a nice tan??*/
    max-width: 50em;
    margin: 2em auto; /*maybe not auto? hmm*/
    line-height:1.4em;
    font-size:18px;
    color: #002639;  /*   an almost black */
    padding:0 10px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "brand side";
  margin-bottom: 50px;
}



#brand {
  grid-area: brand;
  display: flex;
  /* justify-content: center; */
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}



.menu-item {
  display: flex;
  flex-direction: column;
  margin: 1em;
}


</style>
