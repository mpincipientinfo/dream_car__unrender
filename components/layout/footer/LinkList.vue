<template>
  <div>
    <div
      align-v="center"
      class="d-flex justify-content-center align-self-center"
    >
      <div class="list-group list-group-horizontal">
        <a
          href="/#"
          class="btn d-flex align-self-center link p-0"
          v-for="(link, index) in links"
          :key="index"
        >
          <div class="list-group-item list-item bg-transparent border-0 p-0">
            {{ link.title }}
          </div>
        </a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["prop"],
  computed: {
    links() {
      return this.prop;
    }
  }
};
</script>
<style scoped>
.link {
  font-family: Open Sans, sans-serif !important;
  font-weight: 600;
  color: #182540;
}
.list-item {
  padding: 0px 25px !important;
  font-size: 17px;
}
</style>
