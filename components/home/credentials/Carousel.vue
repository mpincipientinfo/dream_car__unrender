<template>
  <div class="carousel-wrapper">
    <client-only>
      <splide :options="options">
        <splide-slide v-for="(credential, index) in credentials" :key="index">
          <Credential :prop="credential" />
        </splide-slide>
      </splide>
    </client-only>
  </div>
</template>
<script>
import Credential from "./Credential";
export default {
  props: ["prop"],
  components: {
    Credential
  },
  computed: {
    credentials() {
      return this.prop;
    }
  },
  data() {
    return {
      options: {
        infinite: false,
        type: "slide",
        perPage: 3,
        dots: false,
        perMove: 1,
        pagination: false,
        width: "100%"
      }
    };
  }
};
</script>
<style>
.splide__track {
  margin-right: 55px;
  margin-left: 55px;
  padding: 10px 18px;
}
.splide {
  margin: auto;
}
.splide__arrow {
  border-radius: initial !important;
  background-color: #acacac;
  opacity: 0.35;
}
.splide__arrow:hover {
  opacity: 0.35;
}
.splide__arrow svg {
  width: 1em;
  height: 1em;
  fill: #fff;
}
button.splide__arrow.splide__arrow--prev {
  position: absolute;
  left: -50px;
  z-index: 50000000;
  top: 50%;
  transform: translateY(-50%);
}
button.splide__arrow.splide__arrow--next {
  position: absolute;
  right: -80px;
  top: 50%;
  transform: translateY(-50%);
}
.splide__arrow {
  width: 27px;
  height: 27px;
}
.credential_card {
  box-shadow: 0 10px 40px 0 rgb(24 37 64 / 10%);
  border-radius: 5px;
}
</style>
