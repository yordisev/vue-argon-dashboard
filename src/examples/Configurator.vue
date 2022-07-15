<template>
  <div class="fixed-plugin">
    <a
      class="px-3 py-2 fixed-plugin-button text-dark position-fixed"
      @click="toggle"
    >
      <i class="py-2 fa fa-cog"></i>
    </a>
    <div class="shadow-lg card">
      <div class="pt-3 pb-0 bg-transparent card-header">
        <div
          class="float-start"
        >
          <h5 class="mt-3 mb-0">Argon Configurator</h5>
          <p>See our dashboard options.</p>
        </div>
        <div
          class="mt-4 float-end"
          @click="toggle"
        >
          <button class="p-0 btn btn-link text-dark fixed-plugin-close-button">
            <i class="fa fa-close"></i>
          </button>
        </div>
        <!-- End Toggle Button -->
      </div>
      <hr class="my-1 horizontal dark" />
      <div class="pt-0 card-body pt-sm-3">
        <!-- Sidebar Backgrounds -->
        <div>
          <h6 class="mb-0">Sidebar Colors</h6>
        </div>
        <a href="#" class="switch-trigger background-color">
          <div
            class="my-2 badge-colors text-start"
          >
            <span
              class="badge filter bg-gradient-primary active"
              data-color="primary"
              @click="sidebarColor('primary')"
            ></span>
            <span
              class="badge filter bg-gradient-dark"
              data-color="dark"
              @click="sidebarColor('dark')"
            ></span>
            <span
              class="badge filter bg-gradient-info"
              data-color="info"
              @click="sidebarColor('info')"
            ></span>
            <span
              class="badge filter bg-gradient-success"
              data-color="success"
              @click="sidebarColor('success')"
            ></span>
            <span
              class="badge filter bg-gradient-warning"
              data-color="warning"
              @click="sidebarColor('warning')"
            ></span>
            <span
              class="badge filter bg-gradient-danger"
              data-color="danger"
              @click="sidebarColor('danger')"
            ></span>
          </div>
        </a>

      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  name: "configurator",
  props: ["toggle"],
  methods: {
    ...mapMutations(["navbarMinimize", "navbarFixed"]),
    sidebarColor(color = "success") {
      document.querySelector("#sidenav-main").setAttribute("data-color", color);
      this.$store.state.mcolor = `card-background-mask-${color}`;
    },
    sidenavTypeOnResize() {
      let white = document.querySelector("#btn-white");
      if (window.innerWidth < 1200) {
        white.classList.add("disabled");
      } else {
        white.classList.remove("disabled");
      }
    }
  },
  computed: {
    sidenavResponsive() {
      return this.sidenavTypeOnResize;
    }
  },
  beforeMount() {
    this.$store.state.isTransparent = "bg-transparent";
    window.addEventListener("resize", this.sidenavTypeOnResize);
    window.addEventListener("load", this.sidenavTypeOnResize);
  }
};
</script>
