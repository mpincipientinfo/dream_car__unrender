<template>
  <div
    class="benefit_parent d-flex flex-column align-items-center justify-content-center"
  >
    <h3 class="subtitle mb-1">{{ subtitle }}</h3>
    <h2 class="title pt-4 pb-6">{{ title }}</h2>
    <b-container class="bv-example-row">
      <b-row>
        <b-col v-for="(benefit, index) in benefits" :key="index">
          <Benefit :data="benefit" :index="index + 1" />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import Benefit from "./Benefit";
export default {
  props: ["prop"],
  components: {
    Benefit
  },
  computed: {
    title() {
      return this.prop.title;
    },
    subtitle() {
      return this.prop.subtitle;
    },
    benefits() {
      return this.prop.vorteile;
    }
  }
};
</script>
<style scoped>
.benefit_parent {
  background-color: #182540;
  color: #fff;
}
.subtitle {
  font-size: 1.125rem;
  font-weight: 600;
  padding-top: 140px;
  font-family: "Mulish", sans-serif;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  padding-bottom: 60px;
}
</style>
