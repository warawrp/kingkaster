<template>
  <div id="home" class="container-fluid">
    <!-- <div class="container-fluid"> -->
      <Navbar />
      <div class="row">
        <div class="col-lg-12">
            <video playsinline autoplay muted loop>
              <source src="../assets/video/Octagon.mp4" type="video/mp4">
            </video>
            <div class="cover-top"></div>
            <div class="cover-left"></div>
            <div class="cover-right"></div>
            <div class="cover-bottom"></div>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-12">
          <div>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum repudiandae vel esse vitae mollitia nobis obcaecati, magni quibusdam temporibus fugit iusto repellat ducimus praesentium consequuntur alias. Odio tenetur debitis eligendi!</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum repudiandae vel esse vitae mollitia nobis obcaecati, magni quibusdam temporibus fugit iusto repellat ducimus praesentium consequuntur alias. Odio tenetur debitis eligendi!</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum repudiandae vel esse vitae mollitia nobis obcaecati, magni quibusdam temporibus fugit iusto repellat ducimus praesentium consequuntur alias. Odio tenetur debitis eligendi!</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Illum repudiandae vel esse vitae mollitia nobis obcaecati, magni quibusdam temporibus fugit iusto repellat ducimus praesentium consequuntur alias. Odio tenetur debitis eligendi!</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
        </div>
      </div>
    <!-- </div> -->
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
  width: 100%;
  /* height: 100vh; */
  height: 623px;
}
</style>
