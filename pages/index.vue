<template>
  <div>
    <Head v-if="data.section_head" :data="data.section_head" />
    <Credentials
      v-if="data.section_referenzen"
      :sectionReferenzen="data.section_referenzen"
    />
    <Benefits
      v-if="data.section_vorteile"
      :sectionVorteile="data.section_vorteile"
    />
    <Services
      v-if="data.section_services"
      :sectionServices="data.section_services"
    />
    <Contact
      v-if="data.section_contact"
      :sectionContact="data.section_contact"
    />
  </div>
</template>

<script>
import params from "@/config/params.js";
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
      data: {}
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const { data } = await this.$axios.get(
        params.baseUrl + "/payload/home.json"
      );
      this.data = data;
    }
  }
};
</script>
