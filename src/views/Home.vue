<template>
  <div id="home" class="container-fluid" style="padding:0;">
      <Navbar />
      <ImageSlideHeader />
      <Sidebar />
      
      <div class="row">
        <div class="col-lg-12">
          <div class="footerHeader"></div>
        </div>
      </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import ImageSlideHeader from "@/components/ImageSlideHeader.vue";
import Sidebar from "@/components/Sidebar.vue"

export default {
  name: "Home",
  components: {
    Navbar,
    ImageSlideHeader,
    Sidebar
  }
};
</script>

<style lang="css">
  @media screen and (min-width: 1200px){
    .footerHeader {
        width: 100%;
        height: 141px;
        background-color: #202433;
        margin: 510px 0 0 0;
      }
}
</style>
