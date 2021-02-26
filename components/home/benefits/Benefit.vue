<template>
  <div>
    <div
      class="d-flex align-items-center justify-content-center justify-content-md-start"
    >
      <h4 class="count">{{ count }}</h4>
      <div class="ml-2">
        <b-img :src="imageUrl"></b-img>
      </div>
    </div>
    <h6 class="title pt-4">{{ title }}</h6>
    <p class="description pt-4">{{ description }}</p>
  </div>
</template>
<script>
export default {
  props: ["data", "index"],
  computed: {
    count() {
      return this.index;
    },
    imageUrl() {
      return this.data.image.url;
    },
    title() {
      return this.data.title;
    },
    description() {
      return this.data.description;
    }
  }
};
</script>
<style scoped>
.title {
  font-size: 26px;
  font-weight: 500;
  color: #fff;
  padding-top: 20px !important;
  line-height: 39px;
  font-family: Lora, serif !important;
}
.count {
  font-family: Open Sans, sans-serif !important;
  font-size: 5rem;
  font-weight: 600;
  color: hsla(0, 0%, 100%, 0.16);
}
.description {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  color: #fff;
  line-height: 2;
  padding-top: 26px;
}
</style>
