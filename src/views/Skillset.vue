
<template>


    <div class="wrapper">
    <div class="moves">
      <p v-if="this.$root.$data.skillset.length === 0">Skillset is empty. Add some moves!</p>
        <div class="move" v-for="move in skillset" :key="move.id">
     
        
            <img :src="'/images/moves/'+move.image">
        
        <div class="price">
            <h2>{{move.name}} - {{move.difficulty}}</h2>
            <button class="auto" @click="removeMove(move)">Remove</button>
        </div>
        </div>
    </div>
    </div>


</template>

<script>

export default {
  name: 'Home',
  components: {
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    skillset() {
      return this.$root.$data.skillset;
    }
  },
  methods: {
    removeMove(move){
      let index = this.$root.$data.skillset.indexOf(move);
      this.$root.$data.skillset.splice(index, 1);
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

.moves {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.move {
  margin: 1em;
  width: 500px;
}

.move img {
  border: 2px solid #333;
  height: 125px;
  width: 100px;
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