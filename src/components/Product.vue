<script>
export default {
    props: {
        productList: {
            type: [{}], 
            required: true, 
        },
       
    }
}
</script>

<template>
  <div v-for="(product,index) in productList" :key="index">
    {{product.name}},
    ${{product.price}},
  </div>
</template>





