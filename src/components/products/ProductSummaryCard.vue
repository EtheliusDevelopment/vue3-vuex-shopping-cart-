<template>
  
  <div class="card">
    <h3>{{product.name}}</h3>

    <h5 class="price">Price: {{product.price}} eur</h5>
    <p class="description">Description: {{subString}}</p>
    <p class="text-muted">{{product.category}}</p>
    <button class="view-product-button" @click="$emit('view-product', product)">
        View Product
    </button>
  </div>
  
  
</template>

<script>
export default {
    name: 'ProductSummaryCard',
    props: ['product'],
    computed: {
        subString() {
         return this.product.description.substring(0, 100)
        }
    },
    
}
</script>

<style lang="scss" scoped>
    .card {
        width: 20%;
        margin: 10%;
        padding: 10px;
        border-radius: 5px;
        background-color: rgba(146, 127, 255, 0.295);
        box-shadow: 0 0 5px gray;

    }

    h5.price {
        color: rgb(240, 140, 140);
    }

    p.description {
        font-size: 0.85rem;
    }

    p.text-muted {
        color: rgba(128, 128, 128, 0.74);
    }
    button {
        padding: 0.5rem;
        background-color: aqua;
        border: none;
        color: white;
        font-weight: bold;
        border-radius: 5px;
        font-size: 1.15rem;
        cursor: pointer;


    }

   @media only screen and (max-width: 680px) {
        .card {
        width: 75%;
        }
    }
</style>>

