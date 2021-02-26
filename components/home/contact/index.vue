<template>
  <div
    class="background_image"
    :style="{ backgroundImage: `url(${backgroundImageUrl})` }"
  >
    <b-container
      class="bv-example-row d-flex flex-column align-items-left pt-5 h-100 container"
    >
      <div class="text-sm-left text-center mt-5 pt-5">
        <h2 class="text-light title mb-3 mt-3">
          {{ title }}
        </h2>
        <div>
          <a href="#" class="btn-red button btn btn-red-expand">{{ button }}</a>
        </div>
      </div>
    </b-container>
  </div>
</template>
<script>
export default {
  props: ["sectionContact"],
  computed: {
    backgroundImageUrl() {
      return this.sectionContact.background_image.url;
    },
    title() {
      return this.sectionContact.title;
    },
    button() {
      return this.sectionContact.button;
    }
  }
};
</script>
<style scoped>
.background_image {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 50%;
  box-shadow: inset 0 0 0 2000px rgba(17, 17, 17, 0.4);
  width: 100%;
  height: 600px;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
}
</style>
