<template>
  <b-container class="py-5 my-5">
    <div
      class="d-flex flex-column align-items-center justify-content-center h-100"
    >
      <h1 class="title">{{ title }}</h1>

      <p class="subtitle my-55 pb-4 pt-3 mt-2 mb-3">{{ subtitle }}</p>
    </div>
    <div class="carousel-wrapper">
      <div v-if="credentials">
        <client-only>
          <splide :options="options">
            <splide-slide
              v-for="(credential, index) in credentials"
              :key="index"
            >
              <div class="credential_card p-sm-4 p-3 text-center text-sm-left">
                <div>
                  <img
                    :src="credential.image.url"
                    class="card_image img-fluid rounded-circle lazyLoad isLoaded"
                  />
                </div>
                <div class="price">
                  <p>{{ credential.price }}</p>
                </div>
                <div class="model">
                  <p>{{ credential.title }}</p>
                </div>
                <div class="description">
                  <p>{{ credential.description }}</p>
                </div>
                <div class="card_subtitle">
                  <p>{{ credential.subtitle }}</p>
                </div>
              </div>
            </splide-slide>
          </splide>
        </client-only>
      </div>
    </div>
  </b-container>
</template>
<script>
export default {
  props: ["sectionCredentialsDataProp"],
  data() {
    return {
      title: this.sectionCredentialsDataProp.title,
      subtitle: this.sectionCredentialsDataProp.subtitle,
      credentials: this.sectionCredentialsDataProp.credentials,
      options: {
        infinite: true,
        type: "loop",
        perPage: 3,
        dots: false,
        perMove: 1,
        pagination: false,
        width: "100%"
      }
    };
  },
  watch: {
    sectionCredentialsDataProp: {
      deep: true,
      handler(newVal, oldVal) {
        this.title = newVal.title;
        this.subtitle = newVal.subtitle;
        this.credentials = newVal.referenzen;
      }
    }
  }
};
</script>
<style scoped>
.price {
  font-family: Lora, serif !important;
  font-size: 1.625rem;
  font-weight: 500;
  padding-top: 20px;
  color: #182540;
}
.description {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  padding-top: 30px;
  padding-bottom: 30px;
  color: #182540;
  line-height: 2;
}
.credential_card {
  box-shadow: 0 10px 40px 0 rgba(24, 37, 64, 0.1);
  border-radius: 5px;
}
.my-55 {
  margin-right: 55px;
  margin-left: 55px;
}
.model {
  color: #acacac;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  font-weight: 500;
  color: #182540;
}
.subtitle {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  font-weight: 600;
  color: #182540;
  text-align: center;
}
.card_image {
  width: 140px;
  height: 140px;
  -o-object-fit: cover;
  object-fit: cover;
}
.card_subtitle {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  color: #e50612;
  font-weight: 600;
}
</style>
<style>
.splide__track {
  margin-right: 55px;
  margin-left: 55px;
}
.splide {
  margin: auto;
}
.splide__arrow {
  border-radius: initial !important;
  background-color: #e1e1e1;
}
</style>
