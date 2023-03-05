<template>
    <div class="single-products-wrapper">
        <div class="product-image-wrapper">
            <img class="product-img" :src="single_product_obj.img" alt="">
            <div class="view-more">View More</div>
        </div>
        <div class="product-description-wrapper">
            <h2>{{ single_product_obj.name }}</h2>
            <h3><span>$</span>{{ single_product_obj.price }}</h3>
            <p>{{ single_product_obj.description }}</p>
        </div>
        
    </div>
</template>

<style scoped>
.single-products-wrapper{ 
    width: 300px;
    height: 500px;
    padding: 10px;
    margin: 20px 20px 0 0;
    display: flex;
    flex-direction: column;
    background-color:rgba(244, 239, 238, 0.693);
    border-radius: 10px;
    box-shadow: 0 5px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

.view-more{
        background-color: rgba(158, 73, 79, 1);
        color: rgba(243, 242, 234, 1);
        font-family: 'Lato', sans-serif;
        padding: 15px 40px;
        max-width: 80px;
        text-align: center;
        border-radius: 5px;
        position: absolute;
        bottom: 60px;
        left: 40px;
        font-size: 17px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: clip;
}
.product-description-wrapper{
    max-height: 300px;
}
.product-image-wrapper{
    max-width: 300px;
    max-height: 200px;
    flex: 1;
    position: relative;
}

.product-img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
}



</style>

<script setup>
   defineProps({
    single_product_obj: { 
       type: Object, 
       required: true
     },
   });
</script>