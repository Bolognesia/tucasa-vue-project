<template>
    <!-- <div class="filter-section">
        <h3>Filter</h3>
        <div class="filter-option">
            <div class="filter-btn">All</div>
            <div class="filter-btn" @click="filteredProducts()">Bedroom</div>
            <div class="filter-btn">Kitchen</div>
            <div class="filter-btn">Outdoor</div>
            <div class="filter-btn">Travel</div>
        </div>
    </div> -->

    <div class="products-section">
        <h3>Sort by:</h3>
        <select name="filter-options" v-model="sorting_method">
            <option value="a-z">Alphabetically: A-Z</option>
            <option value="z-a">Alphabetically: Z-A</option>
            <option value="low-high">Price: Low to high</option>
            <option value="high-low">Price: High to low</option>
        </select>

        <div class="main-products-wrapper">
            <ProductVue 
            v-for="product in sortedProducts"
            :single_product_obj="product"
            />

        </div>

      
    </div>
</template>

<style scoped>
    .main-products-wrapper{
        display: flex;
        flex-wrap: wrap;
    }
    .filter-btn{
        margin: 20px 0;
        padding: 10px 20px;
        border: 2px solid rgba(43, 54, 28, 1);
        border-radius: 5px;
    }

    .filter-btn:hover{
        background-color: rgba(43, 54, 28, 1);
        color: rgba(243, 242, 234, 1);
        cursor: pointer;
    }

    .filterON{
        background-color: rgba(43, 54, 28, 1);
        color: rgba(243, 242, 234, 1);
        
    }

    .products-section{
        margin-left: 100px;
    }

</style>

<script setup>
    import ProductVue from './Product.vue'

    defineProps({
    products_prop_array: { 
        type: Array, 
        required: true
        },
    });
</script>

<script>
    export default {
        data(){
            return{
                sorting_method:'a-z',
            }
        },

        computed: {

            filteredProducts(){
                console.log(this.products_prop_array);
                return this.products_prop_array
                    .filter((product) =>
                    console.log(product.category),
                    product.category == 'Bedroom'
                );
            },

            sortedProducts(){
                //is it a-z
                if(this.sorting_method == 'a-z'){
                    return this.products_prop_array
                        .sort((a,b) =>{
                            const nameA = a.name.toUpperCase();
                            const nameB = b.name.toUpperCase();

                            if(nameA < nameB){
                                return -1;
                            }

                            if (nameA > nameB){
                                return 1;
                            }

                            return 0
                            }
                        )

         
                }
                // is it z-a
                if(this.sorting_method == 'z-a'){
                    return this.products_prop_array
                        .sort((a,b) =>{
                            const nameA = a.name.toUpperCase();
                            const nameB = b.name.toUpperCase();

                            if(nameA < nameB){
                                return 1;
                            }

                            if (nameA > nameB){
                                return -1;
                            }

                            return 0
                            }
                        )
                }
                // is it low-high
                if(this.sorting_method == 'low-high'){
                    return this.products_prop_array
                        .sort((a,b) => a.price-b.price)
                }

                // is it low-high
                if(this.sorting_method == 'high-low'){
                    return this.products_prop_array
                        .sort((a,b) => b.price-a.price)
                }
            },
        },

    }

</script>