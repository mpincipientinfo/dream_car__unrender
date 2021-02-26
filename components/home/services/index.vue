<template>
  <div>
    <div v-for="(service, index, count) in services" :key="index">
      <Service :count="count" :service="service" />
    </div>
  </div>
</template>
<script>
import Service from "./Service";
export default {
  props: ["sectionServices"],
  components: {
    Service
  },
  computed: {
    services() {
      return this.sectionServices;
    }
  }
};
</script>
