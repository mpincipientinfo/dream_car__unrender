<template>
  <div>
    <Main
      :legalLinksProp="legalLinks"
      :pageLinksProp="pageLinks"
      :imgUrlProp="imgUrl"
      :titleProp="title"
    />
    <Socials />
    <!-- copyright -->
    <div class="copyright text-center pt-2 pb-2">
      <h6 class="my-1 copyright_text">
        ©copyright 2021 M2-wunschauto . All Rights Reserved
      </h6>
    </div>
  </div>
</template>
<script>
import Main from "./Main";
import Socials from "./socials";
export default {
  props: ["prop"],
  components: {
    Socials,
    Main
  },
  computed: {
    imgUrl() {
      return this.prop.image.url;
    },
    title() {
      return this.prop.title;
    },
    pageLinks() {
      return this.prop.page_links;
    },
    legalLinks() {
      return this.prop.legal_links;
    }
  }
};
</script>
<style scoped>
.copyright_text {
  font-family: Open Sans, sans-serif !important;
  font-size: 0.875rem;
  font-weight: lighter;
  color: #fff;
}
.copyright {
  background-color: #182540;
}
</style>
