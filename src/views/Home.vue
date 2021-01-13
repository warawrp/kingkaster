<template>
  <div id="home" class="container-fluid" style="padding:0;">
      <Navbar />
      <!-- <ImageSlideHeader /> -->
      <Sidebar />
      <FooterHeader/>
      <Recommended />
      
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
// import ImageSlideHeader from "@/components/ImageSlideHeader.vue";
import Sidebar from "@/components/Sidebar.vue"
import FooterHeader from "@/components/FooterHeader.vue"
import Recommended from "@/components/Recommended.vue"

export default {
  name: "Home",
  components: {
    Navbar,
    // ImageSlideHeader,
    Sidebar,
    FooterHeader,
    Recommended
  }
};
</script>

<style lang="css"></style>
