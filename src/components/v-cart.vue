<template>
  <div class="v-cart">

    <keep-alive>
      <router-link :to="{name:'catalog'}">
        <div class="v-catalog-link-to-cart">
          <i class="large material-icons">shopping_cart</i>
           {{ CART.length }}
        </div>
        
          <button class="btn">Назад в каталог</button>
    </router-link>
    </keep-alive>

    

    <p v-if="!CART.length">Ваша корзина пуста</p>
    

    <h2 class="v-cart-h2">Ваши товары</h2> 
    <vCartItem 
    v-for="(item, index) in CART" 
    :key="item.article" 
    :cart_item_data="item"
    @deleteFromCart="deleteFromCart(index)"/>
  </div>
</template>

<script>
import vCartItem from "./v-cart-item.vue";
import { mapActions, mapGetters } from "vuex";


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
    computed: {
      ...mapGetters (["CART"])
    },
    
}
</script>

<style>
.v-cart{
  display: flex;
    flex-wrap: nowrap;
    color: gray;
    font-size: 20px;
    margin-bottom: 100px;
    flex-direction: column;
    align-items: center;
}
.v-cart-h2 {
  text-align: center;
  font-size: 20px;
}
</style>