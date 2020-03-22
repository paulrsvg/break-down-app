<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Toprock')" href="#" class="pure-menu-link">Toprock 🕺</a></li>
      <li class="pure-menu-item"><a @click="select('Footwork')" href="#" class="pure-menu-link">Footwork 👟</a></li>
      <li class="pure-menu-item"><a @click="select('Power Moves')" href="#" class="pure-menu-link">Power Moves ⚡</a></li>
      <li class="pure-menu-item"><a @click="select('Freezes')" href="#" class="pure-menu-link">Freezes 🧊</a></li>
      <li class="pure-menu-item"><a @click="select('Drops')" href="#" class="pure-menu-link">Drops 💣</a></li>
    </ul>
  </div>
  <MoveList :moves="moves" />
</div>
</template>

<script>
import MoveList from "../components/MoveList.vue"
export default {
  name: 'Browse',
  components: {
    MoveList
  },
  data() {
    return {
      category: '',
    }
  },
  computed: {
    moves() {
      return this.$root.$data.moves.filter(move => move.category === this.category);
    }
  },
  methods: {
    select(category) {
      this.category = category;
    }
  }
}
</script>

<style scoped>
/* scoped styles only affect this component */
.pure-menu-horizontal ul {
  /* max-width: 50em; */
  
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
}

li a:focus {
  border: 2px solid black;
  border-radius: 5px;
}


</style>