<template>
  <div>
    <div v-if="notEmptyObject(pageData)">
      <Head :prop="pageData.section_head" />
      <Credentials :prop="pageData.section_referenzen" />
      <Benefits :prop="pageData.section_vorteile" />
      <Services :prop="pageData.section_services" />
      <Contact :prop="pageData.section_contact" />
    </div>
  </div>
</template>

<script>
//Import mixin
import global from "../mixins/global";
import Vue from "vue";
Vue.mixin(global);
//constants
import params from "@/config/params.js";
//sections
import Head from "@/components/home/head";
import Benefits from "@/components/home/benefits";
import Services from "@/components/home/services";
import Contact from "@/components/home/contact";
import Credentials from "@/components/home/credentials";

export default {
  components: {
    Head,
    Benefits,
    Services,
    Contact,
    Credentials
  },
  head() {
    return {
      title: params.title
    };
  },
  data() {
    return {
      pageData: {}
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const { data } = await this.$axios.get(
        params.baseUrl + "/payload/home.json"
      );
      this.pageData = data;
    }
  }
};
</script>
