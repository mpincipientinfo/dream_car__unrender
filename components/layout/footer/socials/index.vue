<template>
  <div class="social_parent pb-5 pt-4">
    <div class="container mt-5">
      <b-row>
        <div
          class="col-lg-4 text-center"
          v-for="(social, index) in socials"
          :key="index"
        >
          <Social :prop="social" />
        </div>
      </b-row>
    </div>
  </div>
</template>
<script>
import Social from "./Social";
export default {
  components: { Social },
  data() {
    return {
      socials: [
        {
          href: "tel:+436763893322",
          text: "0676 38 93 322",
          image: "phone-call.png",
          target: ""
        },
        {
          href: "mailto:office@m2-wunschauto.at",
          text: "office@m2-wunschauto.at",
          image: "email.png",
          target: ""
        },
        {
          href: "https://www.instagram.com/m2.wunschauto/",
          text: "Instagram",
          image: "instagram.png",
          target: "_blank"
        }
      ]
    };
  }
};
</script>
<style scoped>
.social_parent {
  background: #f8f9fa;
}
</style>
