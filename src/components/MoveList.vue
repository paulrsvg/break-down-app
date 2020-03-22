<template>
<div class="wrapper">
  <div class="moves">
    <div class="move" v-for="move in moves" :key="move.id">
      <div class="info">
        <h1>{{move.name}}</h1>
        <p>{{move.category}}</p>
      </div>
      <div class="image">
        <img :src="'/images/moves/'+move.image">
      </div>
      <div class="price">
        <h2>{{move.price}}</h2>
        <button class="auto" @click="addMove(move)">Add to Cart</button>
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
      this.$root.$data.cart.push(name);
    }
  }

}
</script>


<style scoped>
/* scoped styles only affect this component */
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
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
  width: 200px;
}

.move img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.move .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #F2921D;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
