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
}
.splide {
  margin: auto;
}
.splide__arrow {
  border-radius: initial !important;
  background-color: #e1e1e1;
}
</style>
