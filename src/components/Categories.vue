<template>
    <div class="categories">
        <div class="categories-wrapper">
            <div class="category-img-wrapper">
                <img :src="single_category_obj.category_img" alt="" class="category_img">
                
            </div>
            <div class="shop-now-btn">Shop Now</div>
            <h2 class="single-category-h2">{{ single_category_obj.category_name }}</h2>
        </div>
    </div>
</template>

<style scoped>
    .shop-now-btn{
        background-color: rgba(158, 73, 79, 1);
        color: rgba(243, 242, 234, 1);
        font-family: 'Lato', sans-serif;
        padding: 15px 30px;
        max-width: 80px;
        text-align: center;
        border-radius: 5px;
        position: absolute;
        bottom: 80px;
        left: 40px;
        font-size: 17px;
        
    }

    .shop-now-btn:hover{
        background-color: rgba(243, 242, 234, 1);
        color: rgba(158, 73, 79, 1);
        border: 2px solid rgba(158, 73, 79, 1);
    }
    .categories-wrapper{
        display: flex;
        flex-direction: column;
        position: relative; 
    }

    .single-category-h2{
        margin: auto;
        color: rgba(43, 54, 28, 1)
    }
    .category-img-wrapper{
        max-width: 700px;
        max-height: 700px;
        margin: 10px;
        overflow: hidden;
        border-radius: 10px;
    }

    .category_img{
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform .5s, filter .5s ease-out;
    }

    .category-img-wrapper:hover img{
        transform: scale(1.25);
        filter: opacity(60%);
        cursor: pointer;
        
    }
</style>
    
<script setup>
   defineProps({
    single_category_obj: { 
       type: Object, 
       required: true
     },
   });
</script>

