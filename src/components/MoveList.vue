<template>
<div class="wrapper">
  <div class="moves">
    <div class="move" v-for="move in moves" :key="move.id">
      <div class="info">
        <h3>{{move.name}}</h3>
        <p>
          <em>{{move.category}}</em><br>
          <strong>{{move.difficulty}}</strong>        
        </p>
        <button class="auto" @click="addMove(move)">+ add to skillset</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MoveList',
  props: {
    moves: Array
  },
  methods: {
    addMove(name) {
      if(!this.$root.$data.skillset.includes(name)) //check if already in array (only allow one of each move)
      this.$root.$data.skillset.push(name);
    }
  }

}
</script>


<style scoped>
/* scoped styles only affect this component */
.wrapper {
  /* max-width: 50em; */
  display: flex;
  align-items: center;
  /* justify-content: center; */
}

.moves {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.move {
  margin: 10px;
  margin-top: 50px;
  /* width: 250px; */
  border: 2px solid #333;
  border-radius: 3px;
}

.info {
  /* background: #F2921D; */
  padding: 22px;
  height: 250px;
}

button {
  height: 25px;
  /* background: #000; */
  /* color: white; */
  border: 2px solid black;
}

.auto {
  margin-left: auto;
}
</style>
