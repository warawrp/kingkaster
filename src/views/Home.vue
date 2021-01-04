<template>
  <div class="home">
    <div class="container-fluid">
      <Navbar />
      <div class="row">
        <div class="col-lg-12">
            <video playsinline autoplay muted loop>
              <source src="../assets/video/Octagon.mp4" type="video/mp4">
            </video>
            <div class="cover-left"></div>
            <div class="cover-right"></div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";

export default {
  name: "Home",
  components: {
    Navbar
  }
};
</script>

<style lang="css">
  video {
  object-fit: cover;
  width: 100vw;
  /* height: 100vh; */
  height: 623px;
  position: fixed;
  top: 0;
  left: 0;
}
</style>
