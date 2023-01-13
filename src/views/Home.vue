<template>
   <div id="home">
      <!-- Page Wrapper -->
      <div id="background-div" class="page-holder bg-cover shadow-lg">
         <div class="container py-5">
            <header class="text-left text-white py-5">
               <h3 class="mb-4 rounded">
                  <a
                     href="#start-shopping"
                     class="bg-dark px-2 py-2 text-white rounded"
                     id="heading"
                     >Start Shopping</a
                  >
               </h3>
               <p id="content" class="lead mb-0 bg-dark p-1 rounded">
                  Believers Market is for educational purposes only. It can be
                  used by developers to learn about developing an ecommerce
                  application complete with backend and frontend for Web and
                  Android
               </p>
            </header>
         </div>
      </div>

      <div id="start-shopping" class="container">
         <div class="row">
            <div class="col-12 text-left">
               <h2 class="pt-3">Top Categories</h2>
            </div>
         </div>
         <div class="row">
            <div
               v-for="index in this.category_size"
               :key="index"
               class="col-md-6 col-xl-4 col-12 pt-3  justify-content-around d-flex"
            >
               <CategoryBox :category="categories[index - 1]"> </CategoryBox>
            </div>
         </div>
      </div>

      <hr />
      <div class="container">
         <div class="row">
            <div class="col-12 text-left">
               <h2 class="pt-3">Top Products</h2>
            </div>
         </div>
         <div class="row">
            <div
               v-for="index in this.product_size"
               :key="index"
               class="col-md-6 col-xl-4 col-12 pt-3  justify-content-around d-flex"
            >
               <ProductBox :product="products[index - 1]"> </ProductBox>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
import ProductBox from '../components/Product/ProductBox';
import CategoryBox from '../components/Category/CategoryBox';
export default {
   name: 'Home',
   components: { ProductBox, CategoryBox },
   props: ['baseURL', 'products', 'categories'],
   data() {
      return {
         category_size: 0,
         product_size: 0,
      };
   },
   mounted() {
      this.category_size = 3;
      // this.category_size = Math.min(6, this.category_size);

      this.product_size = 9;
      // this.product_size = Math.min(8, this.product_size);
   },
};
</script>

<style>
.page-holder {
   min-height: 600px;
}

.bg-cover {
   background-size: cover !important;
   background-position: center !important;
   background-repeat: no-repeat !important;
}

#background-div {
   background: url(../assets/gameboy.jpg);
}

#heading {
   text-decoration: none;
   font-family: 'Roboto', sans-serif;
   font-weight: 400;
   opacity: 0.8;
   font-family: 'Josefin Sans', sans-serif;
}

#content {
   opacity: 0.8;
}

h2 {
   font-family: 'Josefin Sans', sans-serif;
}
</style>
