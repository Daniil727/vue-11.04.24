<template>
  <div class="v-catalog-item">
    <img class="v-catalog-item-img" :src="product_data.imgURL" :alt="product_data.image">
    <p class="v-catalog-item-name">{{product_data.name}}</p>
    <p class="v-catalog-item-price">{{product_data.price}}</p>
    <p class="v-catalog-item-article">{{product_data.article}}</p>
    <button class="v-catalog-item-btn" @click="addToCart">click mi</button>

  </div>
</template>

<script>
export default {
    name:"v-catalog-item",
    props: {
        product_data: {
            type: Object,
            default() {
                return{};
            },
        },
    },
    data(){
        return {};
    },
    computed: {},
    methods: {
        addToCart(){
            this.$emit("addToCart",this.product_data)
        }

    }
    

}
</script>


<style lang.scss>
.v-catalog-item{
    flex-basis: 40%;
    box-shadow: 0 0 8px 0 gray;
    padding: 20px;
    margin: 20px;
    
}
.v-catalog-item-img {
height:  100%;
width:  100%;
display: block;
margin: 0 auto;
}
</style>
