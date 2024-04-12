<template>
  <div class="v-catalog">
    <div class="v-catalog-list">
         <vCatalogItem v-for="product in PRODUCTS" 
    :key="product.article" 
    :product_data ='product' 
    @addToCart ="addToCart" />
    </div>
   
  </div>
</template>

<script>
import vCatalogItem from "./v-catalog-item.vue";
import { mapActions, mapGetters } from "vuex";

export default {
    name:"v-catalog",
    components:{
        vCatalogItem
        },
    props: {},
    data(){
        return {
         
        };
    },
    computed: {
        ...mapGetters([
            "PRODUCTS"
        ])

        
    },

    methods: {
        ...mapActions([
            "GET_PRODUCTS_FROM_API", "ADD_TO_CART"
        ]),

        addToCart(data){
            this.ADD_TO_CART(data)
        },
        
    },
    mounted(){
            this.GET_PRODUCTS_FROM_API()
            .then((response) =>{
                if(response.data){
                    console.log("что-то пришло")
                }
            })
        }

}
</script>

<style>
.v-catalog{
   display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: center; 
}
.v-catalog-list{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    
}
  
</style>