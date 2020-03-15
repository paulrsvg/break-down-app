
<template>


    <div class="wrapper">
    <div class="products">
      <p v-if="this.$root.$data.cart.length === 0">Cart is empty. Add some items!</p>
        <div class="product" v-for="product in cart" :key="product.id">
     
        
            <img :src="'/images/products/'+product.image">
        
        <div class="price">
            <h2>{{product.name}} - {{product.price}}</h2>
            <button class="auto" @click="removeProduct(product)">Remove</button>
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
    cart() {
      return this.$root.$data.cart;
    }
  },
  methods: {
    removeProduct(product){
      let index = this.$root.$data.cart.indexOf(product);
      this.$root.$data.cart.splice(index, 1);
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

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 1em;
  width: 500px;
}

.product img {
  border: 2px solid #333;
  height: 125px;
  width: 100px;
  object-fit: cover;
}

.product .image {
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