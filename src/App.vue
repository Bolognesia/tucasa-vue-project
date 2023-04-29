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

    <div class="main-shop-section">
      <MainVue 
      :products_prop_array="products_array"
      />
    </div>

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

.main-shop-section{
  display: flex;
  
}

  @media (max-width: 1000px){
          .categories-flex{
              display: flex;
              flex-direction: column;
              background-color: blue;
          }
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
            name:'June & Jupiter Belle Quilted Duvet Cover Set',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1103657001/1103657001_default_1.jpg/CatalogContentDetails-1282347-600-600-75-0,0',
            category: 'Bedding',
            price: 165,
            description: 'The Belle Quilted Duvet Cover Set by June & Jupiter showcases a beautiful flora design on stonewashed cotton. This Duvet Cover Set features both functionality and beauty. Evoking feelings of warmth and comfort, this duvet cover will effortlessly bring a peaceful style to your bedroom.',
          },

          {
            name:'KAS Ramao Light Duvet Cover Set',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1099571/1099571_default_1.jpg/CatalogContentDetails-1015417-600-600-75-0,0',
            category: 'Bedding',
            price: 130,
            description: 'Eye catching abstract leaves extend over the Ramao Duvet Cover Set. Featuring watercolour brush strokes of lush colour hand painted by KAS artists in their Sydney studio. The rich palette of colours combines harmoniously with the coordinating plain dyed reverse. ',
          },

          {
            name:'Galaxy 1000GSM Microfibre Mattress Topper',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1098416/1098416_default_1.jpg/CatalogContentDetails-768615-600-600-75-0,0',
            category: 'Bedding',
            price: 80,
            description: 'The ultimate in microfibre comfort. For a cloud like nights sleep this topper will not disappoint with its lofty cushion of comfort that will leave you waking refreshed in the morning.',
          },

          // {
          //   name:'',
          //   img: '',
          //   category: '',
          //   price: '',
          //   description: '',
          // },

          // {
          //   name:'',
          //   img: '',
          //   category: '',
          //   price: '',
          //   description: '',
          // },

          // {
          //   name:'',
          //   img: '',
          //   category: '',
          //   price: '',
          //   description: '',
          // },

          // {
          //   name:'',
          //   img: '',
          //   category: '',
          //   price: '',
          //   description: '',
          // },

          // {
          //   name:'',
          //   img: '',
          //   category: '',
          //   price: '',
          //   description: '',
          // },

          // {
          //   name:'',
          //   img: '',
          //   category: '',
          //   price: '',
          //   description: '',
          // }

        ],
      }
    },
  }
  
</script>
