<template>
    <div class="single-products-wrapper">
        <h2>{{ single_product_obj.name }}</h2>
        <div class="product-image-wrapper">
            <img :src="single_product_obj.img" alt="">
        </div>
        <h3><span>$</span>{{ single_product_obj.price }}</h3>
        <p>{{ single_product_obj.description }}</p>
    </div>
</template>

<style scoped>

</style>

<script setup>
   defineProps({
    single_product_obj: { 
       type: Object, 
       required: true
     },
   });
</script>