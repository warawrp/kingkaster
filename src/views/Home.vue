<template>
  <div id="home" class="container-fluid">
      <Navbar />
      <ImageSlide />
      
      <div class="row">
        <div class="col-lg-12">
          
        </div>
      </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import ImageSlide from '@/components/ImageSlide.vue';

export default {
  name: "Home",
  components: {
    Navbar,
    ImageSlide
  }
};
</script>

<style lang="css">
  @media screen and (min-width: 1200px){
    
}
</style>
