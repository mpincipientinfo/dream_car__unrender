<template>
  <div class="pt-5 mt-5 pb-5 mb-5">
    <div class="d-flex flex-column">
      <div class="home__logo text-center">
        <div class="text-center">
          <div class="mb-3">
            <img alt="" class="img-fluid lazyLoad isLoaded" :src="imgUrl" />
          </div>
          <div>
            <img src="@/assets/images/logoline.f940fa9.png" alt="Image" />
          </div>
          <p class="title mt-3 pt-1 mb-3">{{ title }}</p>
          <!-- page links -->
          <LinkList :prop="pageLinks" class="text-uppercase" />
          <!--legal links -->
          <LinkList :prop="legalLinks" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import LinkList from "./LinkList";
export default {
  props: ["legalLinksProp", "pageLinksProp", "imgUrlProp", "titleProp"],
  components: {
    LinkList
  },
  computed: {
    legalLinks() {
      return this.legalLinksProp;
    },
    pageLinks() {
      return this.pageLinksProp;
    },
    imgUrl() {
      return this.imgUrlProp;
    },
    title() {
      return this.titleProp;
    }
  }
};
</script>
<style scoped>
.title {
  color: #182540;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
</style>
