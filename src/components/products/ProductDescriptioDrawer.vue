<template>
  <div 
  class="drawer-background" 
  :class="{show: active}"
  @click="$emit('close-product-drawer')"
>
   <div class="drawer" :class="{show: active}">

       <div class="drawer-close"
       @click="$emit('close-product-drawer')"
       >
           X
       </div>

       <div v-if="product" class="product-details">
           <h3 class="text-center">{{product.name}}</h3>
           <p class="description">{{product.description}}</p>
           <h3 class="text-center">{{product.price.toFixed(2)}}</h3>

           <div class="cart-total" v-if="product_total">
               <h3>In Cart</h3>
                <h4>{{product_total}}</h4>
           </div>

           <div class="button-container">
               <button class="remove">
                   Remove
               </button>
               <button class="add">
                   Add
               </button>
           </div>
       </div>
       
   </div>
     
  </div>
</template>

<script>
export default {
    name: 'ProductDescriptioDrawer',
    props: ['product','active'],
    computed: {
        product_total() {
            return 56.29
        }
    },
}
</script>

<style lang="scss" scoped>
.drawer-background {
    width: 100%;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(124, 124, 124, 0.55);
    z-index: 99;
    visibility: hidden;
    opacity: 0;
    transition: opacity .2s;

    &.show {
        visibility: visible;
        opacity: 1;
        
    }

    .drawer {
        width: 95vw;
        height: 100vh;
        background-color: white;
        position: fixed;
        top: 0;
        left: -105vw;
        padding: 15px;
        transition: left .6s;
        z-index: 100;
        overflow-y: scroll;

        &.show {
        left: 0;
        transition: left .6s;
     }
    }

    .drawer-close {
        font-size: 1.5rem;
        padding: 5px;
        border-radius: 5px;
        right: 10px;
        border: 2px solid gray;
        color: gray;
        widows: 15px;
        float: right;
        cursor: pointer;
        transition: background-color .5s;

        &:hover {
            background-color: lightgray;
        }
    }

    .product-details {

        display: flex;
        justify-content: center;
        flex-direction: column;

        p.description {
            padding: 20px;
            line-height: 1.5rem;
        }

        .button-container {

            button {
                width: 150px;
                padding: 0.5rem;
                background-color: aqua;
                border: none;
                color: white;
                font-weight: bold;
                border-radius: 5px;
                font-size: 1.15rem;
                cursor: pointer;
                margin: 1rem;

            }
        }


    }

}

 @media only screen and (max-width: 680px) {
    .drawer {
        width: 80vw !important;
    }
}
</style>>

