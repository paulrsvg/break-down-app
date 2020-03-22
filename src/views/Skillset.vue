
<template>


    <div class="wrapper">
    <div class="moves">
      <p v-if="this.$root.$data.skillset.length === 0">Skillset is empty. Add some moves!</p>
        <div class="move" v-for="move in skillset" :key="move.id">
        
        <div class="info">
          <p>{{move.name}} - <em>{{move.category}}</em> | <strong>{{move.difficulty}}</strong></p>
        
            <button class="auto" @click="removeMove(move)">- remove</button>
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
  border: 2px solid #333;
}



.info {
  /* background: #F2921D;
  color: #000; */
  padding: 5px;
  /* height: 90px; */
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}




button {
  height: 30px;
  /* background: #000;
  color: white; */
  border: 2px solid black;
}

.auto {
  margin-left: auto;
}
</style>