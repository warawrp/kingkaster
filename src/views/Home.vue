<template>
  <div id="home" class="container-fluid" style="padding:0;">
      <Navbar />
      <!-- <ImageSlideHeader /> -->
      <Sidebar />
      <FooterHeader/>
      <Recommend />

      <div class="row">
            <div class="col-lg-12 bg-Home">
              <Interest/>
            </div>
      </div>
      <div class="row">
            <div class="col-lg-12 bg-Home">
              <LiveVideo/>
            </div>
      </div>
      
      
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
// import ImageSlideHeader from "@/components/ImageSlideHeader.vue";
import Sidebar from "@/components/Sidebar.vue"
import FooterHeader from "@/components/FooterHeader.vue"
import Recommend from "@/components/Recommend.vue"
import Interest from "@/components/Interest.vue"
import LiveVideo from "@/components/LiveVideo.vue"

export default {
  name: "Home",
  components: {
    Navbar,
    // ImageSlideHeader,
    Sidebar,
    FooterHeader,
    Recommend,
    Interest,
    LiveVideo
  }
};
</script>

