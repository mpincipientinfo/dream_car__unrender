<template>
  <div>
    <Header v-if="data.section_navbar" :sectionNavbar="data.section_navbar" />
    <Nuxt />
    <Footer v-if="data.section_footer" :sectionFooter="data.section_footer" />
  </div>
</template>
<script>
import params from "@/config/params.js";
import Header from "@/components/layout/header";
import Footer from "@/components/layout/footer";
export default {
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      data: {},
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const { data } = await this.$axios.get(
        params.baseUrl + "/payload/shared.json"
      );
      this.data = data;
    },
  },
};
</script>
