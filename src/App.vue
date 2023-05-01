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
              /* background-color: blue; */
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
            name:'Galaxy 1000GSM Microfibre Mattress TopperGalaxy 1000GSM',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1098416/1098416_default_1.jpg/CatalogContentDetails-768615-600-600-75-0,0',
            category: 'Bedding',
            price: 80,
            description: 'The ultimate in microfibre comfort. For a cloud like nights sleep this topper will not disappoint with its lofty cushion of comfort that will leave you waking refreshed in the morning.',
          },

          {
            name:'Hampton & Mason Impact Pro 3Pce Saucepan Set',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1055433_00/1055433_00_default_1.jpg/CatalogContentDetails-125521-600-600-75-0,0',
            category: 'Kitchen',
            price: 99,
            description: 'Made from 18/4 Stainless Steel the Hampton & Mason Impact Pro Saucepan Set has vented tempered glass lids, soft rubberised cool touch handle & knob for easy handling and is suitable for all cooktops including induction.',
          },

          {
            name:'Nespresso Pop Blue Bundle Coffee Machine ENV90AAE',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1105837_prod_default_1.jpg/CatalogContentDetails-1410925-600-600-75-0,0',
            category: 'Kitchen',
            price: 389,
            description: 'Standing at 25 cm, Vertuo Pop makes a big statement by going small. One button is enough to activate the best in every cup. Each capsule is analysed thanks to a code to finely adjust brewing parameters. The centrifusion extraction system then enhance the aromas of each blend. Espresso, double espresso, gran lungo, mug… Get ready to be spoiled for choice.',
          },

          {
            name:'Outdoor Creations Eiffel Outdoor Setting 3 Piece',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1104209_00/1104209_00_default_1.jpg/CatalogContentDetails-1243886-600-600-75-0,0',
            category: 'Outdoor',
            price: '1999',
            description: 'Aluminium 3Pce Bistro Setting from Outdoor Creations. Luxurious finish with high quality 200g Olefin fabric for extra comfort & durability. Powder coated alumiun construction. Polyester fibre fill with chair 10cm thick padding & back rest 15cm thick Wicker Rope sides. Chairs 81cm H x 66cm x 76cm. Side table 46cm x 46cm x 48cm H. Arm rests and slat table top made of wood look resin which wont fade crack or split. Comes in one carton 68 x 64 x 76cm. Grosss weight 24kg. Comes ready to assemble. Always remove cushions and store in a dry area out of the sun when not in use. Wash frame with mild soap and water and rise thoroughly and dry completely. Do not use bleach, acid or other solvents.',
          },

          {
            name:'Milano Outdoor 3 Meter Hanging and Folding Umbrella Beige',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1106103_00/1106103_00_default_1.jpg/CatalogContentDetails-1365080-600-600-75-0,0',
            category: 'Outdoor',
            price: '299',
            description: 'Deck out your outdoor space in style with the Outdoor 3-Metre Umbrella with Bonus Protective Cover, designed by Milano Decor!The umbrella features a durable 160GSM polyester fabric cover that extends to a maximum of 3 metres in diameter and 2.5 metres in height.It utilises a cantilevered side-post design which ensures the maximum useable space in the shade and eliminates the concept of a traditional central pole.The fabric cover is both UV and weather resistant. The umbrella’s frame is constructed from steel that is powder-coated to ensure longevity.',
          },

          {
            name:'Char-Broil Professional TRU-Infrared 4-Burner BBQ 4400B',
            img: 'https://www.briscoes.co.nz/globalassets/productimages/briscoes/1096911_00/1096911_00_default_1.jpg/CatalogContentDetails-1366262-600-600-75-0,0',
            category: 'Outdoor',
            price: '1399',
            description: '4 burner gas BBQ.TRU-Infrared™ cooking technology with five key benefits: up to 50% juicier food, 100% even heat distribution, no flare-ups, easy cleaning, up to 30% more economical fuel consumption.Black double-skinned ‘cold-rolled’ vitreous enamel roasting hood with pressed steel end caps for maximum heat retention.',
          },

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
