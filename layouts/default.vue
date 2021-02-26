<template>
  <div>
    <div v-if="notEmptyObject(data)">
      <Header :prop="data.section_navbar" />
      <Nuxt />
      <Footer :prop="data.section_footer" />
    </div>
  </div>
</template>
<script>
import params from "@/config/params.js";
import Header from "@/components/layout/header";
import Footer from "@/components/layout/footer";
export default {
  components: {
    Header,
    Footer
  },
  data() {
    return {
      data: {}
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const { data } = await this.$axios.get(
        params.baseUrl + "/payload/shared.json"
      );
      this.data = data;
    }
  }
};
</script>
