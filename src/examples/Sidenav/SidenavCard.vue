<template>
  <div
    v-show="this.$store.state.layout !== 'landing'"
    class="card card-plain shadow-none"
    id="sidenavCard"
  >
    <div class="p-3 card-body text-center w-100 pt-0">
      <img
        class="w-50 mx-auto"
        src="@/assets/img/illustrations/icon-documentation.svg"
        alt="sidebar_illustration"
      />
      <h6 class="mb-0 text-dark up">Need Help ?</h6>
     
      <p class="text-xs font-weight-bold">Please check our docs</p>
    </div>
    <a
      href="https://www.creative-tim.com/product/vue-argon-dashboard-pro"
      target="_blank"
      class="mb-3 btn btn-success btn-sm w-100"
      >Upgrade to pro</a
    >
  </div>
</template>
<script>
import img from "../../assets/img/illustrations/icon-documentation.svg";

export default {
  name: "sidenav-card",
  props: ["textPrimary", "textSecondary", "iconClass"],
  data() {
    return {
      img
    };
  }
};
</script>
