<template>
  <div class="v-cart-item">
     <img class="v-catalog-item-img-cart" :src="cart_item_data.imgURL" :alt="cart_item_data.image">
    <div class="v-cart-item-components">
     
    <div>
      <p> {{ cart_item_data.name }}</p>
      <p> {{ cart_item_data.price }}</p>
      <p> {{ cart_item_data.article }}</p>
    </div>
    <div class="v-cart-item-quantity">
      <p>Quantity</p>
      <span>{{ cart_item_data.quantity }}</span>
    </div>
    <button class="btn" @click="deleteFromCart">Удалить</button>
    </div>
    
  </div>
</template>

<script>
export default {
    name:"v-cart-item",
    props: {
      cart_item_data:{
        tape: Object,
        default(){
          return [];
        }
      }
    },
    data(){
        return {
          
        };
    },
    methods: {
      deleteFromCart () {
        this.$emit('deleteFromCart')
      }
    },
    watch:{},
      mounted() {
      console.log("карта добавлена")
    },
    computed: {},
    

}
</script>

<style>
.v-cart-item {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    flex-basis: 25%;
    align-items: center;
    box-shadow: 0 0 8px 0 gray;
    padding: 20px;
    margin: 20px;
}
.v-catalog-item-img-cart {
  height: 80%;
  width: 80%;
}
.v-cart-item-components {
  display: flex;
    flex-direction: column;
    align-items: center;
    margin-left: 20px;
}

</style>