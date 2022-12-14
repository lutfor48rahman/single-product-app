<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/> -->
  <div class="navHead">
    <p class="name"> Single Product</p>
   </div>
   <AboutProductVue></AboutProductVue>
   <OurProductVue></OurProductVue>
   <BenefitOurProduct></BenefitOurProduct>
   <PhotoGalleryVue />
   <FeedbackVue />
   <FAQVue />
   <CustomerInfoVue />
</template>

<script>
import AboutProductVue from './views/AboutProduct.vue';
import OurProductVue from './views/OurProduct.vue';
import BenefitOurProduct from './views/BenefitOurProduct.vue';
import PhotoGalleryVue from './views/PhotoGallery.vue';
import FeedbackVue from './views/Feedback.vue';
import FAQVue from './views/FAQ.vue';
import CustomerInfoVue from './views/CustomerInfo.vue';
export default {
  components:{AboutProductVue,OurProductVue,BenefitOurProduct,PhotoGalleryVue,FeedbackVue,FAQVue,CustomerInfoVue},
}
</script>

<style>
.navHead{
  height: 70px;
  width: 100%;
  background: gray;
  display: flex;
  justify-content: center;
  align-items: center;
}
.navHead .name{
  font-size: 30px;
}
</style>
