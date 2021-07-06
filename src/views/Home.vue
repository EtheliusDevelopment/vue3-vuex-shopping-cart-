<template>
  <div class="home">
    

    <div class="product-cards-container">
      <ProductSummaryCard 
      v-for="product in items"
      :key="product.id"
      :product="product"
      @view-product="viewProduct"
      />
    </div>
    <ProductDescriptioDrawer 
      :product="product"
      :active="active.product_drawer"
      @close-product-drawer="closeDrawer"
    />
  </div>
</template>

<script>
// @ is an alias to /src

import items from '../data/items';
import ProductSummaryCard from '../components/products/ProductSummaryCard.vue'
import ProductDescriptioDrawer from '../components/products/ProductDescriptioDrawer.vue'

export default {
  name: 'Home',
  components: {
   ProductSummaryCard,
   ProductDescriptioDrawer
  },
  data() {
    return {
      items: items,
      product: null,
      active: {
        product_drawer: false
      } 
    }
  },
  methods: {
    viewProduct(product) {
      this.product = product;
      this.active.product_drawer=true; 
      console.log(this.product);
    },
    closeDrawer() {
      this.active.product_drawer=false; 
    }
  },
}
</script>

<style lang="scss" scoped>
.product-cards-container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
