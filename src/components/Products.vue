<template>
  <ul class="products-listing">
    <li v-for="product in allProducts" :key="product.id">
      {{product.title}} | {{product.price | currency}}
      <button @click="deleteProduct(product.id)">❌</button>
    </li>
  </ul>
</template>

<script>
import { mapGetters, mapActions } from 'vuex'
export default {
  name: 'Products-Page',
  filters:{
    currency: function(value){
      return "₹ " + parseFloat(value).toFixed(2);
    }
  },
  methods:{
    ...mapActions(["getProducts","deleteProduct"])
  },
  computed: mapGetters(["allProducts"]),
  created(){
    this.getProducts()
  }
}
</script>
<style scoped>

</style>>

