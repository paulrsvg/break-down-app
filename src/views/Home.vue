

<template>
<div>
  <span class = "wrapper">Search for dance moves to add to your skillset below:</span><br>
  <div class="wrapper">
    
    <div class="search">
      <form class="pure-form">
        <i class="fas fa-search search-icon"></i><input v-model="searchText" />
      </form>
    </div>
  </div>
  <MoveList :moves="moves" />
</div>
</template>

<script>
import MoveList from "../components/MoveList.vue"

export default {
  name: 'Home',
  components: {
    MoveList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    moves() {
      return this.$root.$data.moves.filter(move => move.name.toLowerCase().search(this.searchText) >= 0);
    }
  },
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

.search-icon {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>