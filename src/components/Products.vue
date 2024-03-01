<script>
import axiosInstance from "../../services/axios.js";
import Product from "@/components/Product.vue";
export default {
  name: "Products",
  components:{
    Product,
  },
  data(){
    return{
    products:[],
    }
  },
  methods:{
    getProducts(){
      axiosInstance.get('/products')
          .then(response => {
            this.products = response.data;
          })
          .catch(error=>{
            console.log(error)
          })
    }
    },
  mounted() {
      this.getProducts()
  }
}
</script>

<template>
<v-container>
  <v-row>
    <v-col v-for="product in products" :key ="product.id">
      <Product :products="product"/>
    </v-col>
  </v-row>
</v-container>
</template>

<style scoped>

</style>