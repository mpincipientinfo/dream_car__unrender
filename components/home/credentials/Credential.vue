<template>
  <div class="credential_card p-sm-4 p-3 text-center text-sm-left">
    <div>
      <img :src="imageUrl" class="image img-fluid rounded-circle" />
    </div>
    <div class="price">
      <p>{{ price }}</p>
    </div>
    <div class="title">
      <p>{{ title }}</p>
    </div>
    <div class="description">
      <p>{{ description }}</p>
    </div>
    <div class="subtitle">
      <p>{{ subtitle }}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: ["prop"],
  computed: {
    imageUrl() {
      return this.prop.image.url;
    },
    price() {
      return this.prop.price;
    },
    title() {
      return this.prop.title;
    },
    description() {
      return this.prop.description;
    },
    subtitle() {
      return this.prop.subtitle;
    }
  }
};
</script>
<style scoped>
.credential_card {
  box-shadow: 0 10px 40px 0 rgba(24, 37, 64, 0.1);
  border-radius: 5px;
}
.price {
  font-family: Lora, serif !important;
  font-size: 1.625rem;
  font-weight: 500;
  padding-top: 20px;
  color: #182540;
}
.description {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  padding-top: 30px;
  padding-bottom: 30px;
  color: #182540;
  line-height: 2;
}
.title {
  color: #acacac;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
.image {
  width: 140px;
  height: 140px;
  -o-object-fit: cover;
  object-fit: cover;
}
.subtitle {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  color: #e50612;
  font-weight: 600;
}
</style>
