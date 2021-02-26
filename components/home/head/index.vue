<template>
  <div>
    <div
      class="background_image"
      :style="{ backgroundImage: `url(${backgroundImageUrl})` }"
    >
      <div
        class="d-flex flex-column align-items-center justify-content-center h-100"
      >
        <b-img :src="imageUrl"></b-img>
        <h1 class="text-light title">
          <i>
            {{ title }}
          </i>
        </h1>
        <h2 class="subtitle text-light">{{ subtitle }}</h2>
        <b-row class="w-100 pt-4">
          <b-col
            lg="6"
            md="12"
            class="pt-4 justify-content-lg-end justify-content-center d-flex"
          >
            <a href="#" class="btn-red btn">{{ button1 }}</a>
          </b-col>
          <b-col
            lg="6"
            md="12"
            class="pt-4 justify-content-lg-start justify-content-center d-md-flex d-none"
          >
            <a href="#" class="btn-blue btn">{{ button2 }}</a>
          </b-col>
        </b-row>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["prop"],
  computed: {
    backgroundImageUrl() {
      return this.prop.background_image.url;
    },
    imageUrl() {
      return this.prop.image.url;
    },
    title() {
      return this.prop.title;
    },
    subtitle() {
      return this.prop.subtitle;
    },
    button1() {
      return this.prop.button_1;
    },
    button2() {
      return this.prop.button_2;
    }
  }
};
</script>
<style scoped>
.background_image {
  height: 800px;
}
.title {
  font-family: Open Sans, sans-serif !important;
  font-size: 2.3125rem;
  padding-top: 27px;
}
.subtitle {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
</style>
