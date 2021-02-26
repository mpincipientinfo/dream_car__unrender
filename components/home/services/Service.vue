<template>
  <b-row class="m-0">
    <!-- For first record: display image in right, for second record: display image in left & continue same pattern -->
    <!-- image in right -->
    <b-col lg="6" class="d-none d-md-block p-0 " v-if="index % 2 != 0">
      <img :src="imageUrl" class="w-100 fluid image h-100" />
    </b-col>
    <b-col
      lg="6"
      sm="12"
      class="p-0 padd_left_12_per pt-3 mt-5 col-sm-12 col-lg-6"
    >
      <h2 class="pb-3 mb-1 title">{{ title }}</h2>
      <div v-for="(list, index) in list" :key="index">
        <b-img src="@/assets/images/tick.e546d3c.svg" class="float-left">
        </b-img>
        <p class="list_title pb-3">{{ list.title }}</p>
      </div>
      <div
        class=" mb-2  d-flex flex-sm-row justify-content-center justify-content-sm-start flex-column w-100"
      >
        <div class="align-self-center">
          <a href="#" class="btn-red button btn btn-red-expand">
            {{ button }}
          </a>
        </div>
        <div
          class="d-flex align-items-start flex-column bd-highlight "
          v-if="price"
        >
          <div class="p-2 bd-highlight">
            <div class="price_tag">
              <b-img src="@/assets/images/price_tag.jpeg"></b-img>
              <p class="price_tag_text">PRIES</p>
            </div>
            <h5 class="price">
              {{ price }}
            </h5>
          </div>
        </div>
      </div>
    </b-col>
    <!-- image in left -->
    <b-col lg="6" class="d-none d-md-block p-0" v-if="index % 2 == 0">
      <img :src="imageUrl" class="w-100 fluid h-100" />
    </b-col>
  </b-row>
</template>
<script>
export default {
  props: ["count", "service"],
  computed: {
    imageUrl() {
      return this.service.image.url;
    },
    title() {
      return this.service.title;
    },
    list() {
      return this.service.list;
    },
    button() {
      return this.service.button;
    },
    price() {
      return this.service.price;
    },
    index() {
      return this.count;
    }
  }
};
</script>
<style scoped>
.padd_left_12_per {
  padding-left: 10% !important;
}
.list_title {
  font-family: "Lora", serif;
  font-size: 1.0625rem;
  color: #182540;
  padding-left: 41px;
}
.image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
  object-fit: cover;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  color: #182540;
  font-weight: 500;
}
.price_tag {
  position: relative;
}
.price_tag_text {
  position: absolute;
  top: 1px;
  left: 10px;
  color: #fff;
  letter-spacing: 7px;
  font-family: Open Sans, sans-serif !important;
  font-size: 0.875rem;
}
.price {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  font-weight: 500;
  color: #182540;
}
</style>
