<template>
  <div>
    <a :href="href" class="social_meta" :target="target">
      <img :src="require(`@/assets/images/${image}`)" />
      <p class="mt-3">{{ text }}</p>
    </a>
  </div>
</template>
<script>
export default {
  props: ["prop"],
  computed: {
    target() {
      return this.prop.target;
    },
    href() {
      return this.prop.href;
    },
    image() {
      return this.prop.image;
    },
    text() {
      return this.prop.text;
    }
  }
};
</script>
<style scoped>
.social_meta:hover,
.social_meta {
  color: #030508;
  text-decoration: none;
}
</style>
