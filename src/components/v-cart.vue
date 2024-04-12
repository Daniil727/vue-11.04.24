<template>
  <div class="v-cart">
    <h2 class="v-cart-h2">cart</h2> 
    <vCartItem 
    v-for="(item, index) in cart_data" 
    :key="item.article" 
    :cart_item_data="item"
    @deleteFromCart="deleteFromCart(index)"/>
  </div>
</template>

<script>
import vCartItem from "./v-cart-item.vue";
import { mapActions } from "vuex";


export default {
    name:"v-cart",
    components:{
      vCartItem
      },
    props: {
      cart_data: {
        type: Array,
        default(){
          return []
        }

      }
    },
    data(){
        return {
           
        };
    },
    methods: {
      ...mapActions(["DELETE_FROM_CART"]),
      deleteFromCart(index){
        this.DELETE_FROM_CART(index)
      },
    },
    computed: {},
    
}
</script>

<style>
.v-cart{
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  color: blue;
  font-size: 20px;
  margin-bottom: 50px;
}
.v-cart-h2 {
  text-align: center;
  font-size: 20px;
}
</style>