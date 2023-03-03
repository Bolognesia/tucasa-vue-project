<script setup>
  import HeaderVue from './components/Header.vue'
  import MainVue from './components/Main.vue'
  import CategoriesVue from './components/Categories.vue'

 //importing images
  import bedroom_image from './assets/bedroom.jpeg'
  import bathroom_image from './assets/bathroom.jpeg'
  import living_room_image from './assets/living.jpeg'
</script>

<template>
  
  <HeaderVue class="header"/>

  <div class="main-padding">

    <div class="title">
      <h1>Latest Offers</h1>
      <hr>
      <br>
    </div>
    
    
    <div class="categories-flex">
      <CategoriesVue
      v-for="single_category in main_categories"
      :single_category_obj="single_category"
      />
    </div>

    <div class="title">
      <h1>Shop</h1>
      <hr>
      <br>
    </div>

    <MainVue />
  </div>
  
</template>

<style scoped>

.title{
  color: rgba(43, 54, 28, 1);
}
.main-padding{
  padding:30px 95px;
}

.categories-flex{
  display: flex;
}

hr{
  border: 1px solid rgba(158, 73, 79, 1);
}







</style>

<script>
  
  export default {
    data(){
      return{
        
        main_categories:[
          {
            category_name: 'Bedroom',
            category_img: bedroom_image
          },
          {
            category_name: 'Living Room',
            category_img: living_room_image 
          },
          {
            category_name: 'Bathroom',
            category_img: bathroom_image
          }
        ],

        products_array:[
          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          },

          {
            name:'',
            img: '',
            category: '',
            price: '',
            description: '',
          }

        ],
      }
    },
  }
  
</script>
