<template>
  <div
    class="collapse navbar-collapse w-auto h-auto h-100"
    id="sidenav-collapse-main"
  >
    <ul class="navbar-nav">
      <li class="nav-item">
         <router-link to="/dashboard-default" class="nav-link" :class="getRoute() === 'dashboard-default' ? 'active' : ''">
    <div
      class="icon icon-shape icon-sm text-center d-flex align-items-center justify-content-center"
    >
      <i class="ni ni-tv-2 text-primary text-sm opacity-10"></i>
    </div>
    <span
      class="nav-link-text ms-1"
      >Dashboard</span
    >
  </router-link>
      </li>
      <li class="nav-item">
         <router-link to="/tables" class="nav-link"   :class="getRoute() === 'tables' ? 'active' : ''">
    <div
      class="icon icon-shape icon-sm text-center d-flex align-items-center justify-content-center"
    >
       <i class="ni ni-calendar-grid-58 text-warning text-sm opacity-10"></i>
    </div>
    <span
      class="nav-link-text ms-1"
      >Tables</span
    >
  </router-link>
      </li>
      <li class="mt-3 nav-item">
        <h6
          class="text-xs ps-4 text-uppercase font-weight-bolder opacity-6 me-4"
        >
          ACCOUNT PAGES
        </h6>
      </li>
      <li class="nav-item">
        <router-link to="/profile" class="nav-link"   :class="getRoute() === 'profile' ? 'active' : ''">
    <div
      class="icon icon-shape icon-sm text-center d-flex align-items-center justify-content-center"
    >
       <i class="ni ni-single-02 text-dark text-sm opacity-10"></i>
    </div>
    <span
      class="nav-link-text ms-1"
      >Profile</span
    >
  </router-link>
      </li>
      <li class="nav-item">
        <router-link to="/signin" class="nav-link"    :class="getRoute() === 'signin' ? 'active' : ''">
    <div
      class="icon icon-shape icon-sm text-center d-flex align-items-center justify-content-center"
    >
      <i class="ni ni-single-copy-04 text-danger text-sm opacity-10"></i>
    </div>
    <span
      class="nav-link-text ms-1"
      >Sign In</span
    >
  </router-link>
      </li>
    </ul>
  </div>
  <div class="pt-3 mx-3 mt-3 sidenav-footer">
    <sidenav-card
      :class="cardBg"
      textPrimary="Need Help?"
      textSecondary="Please check our docs"
    />
  </div>
</template>
<script>
import SidenavCard from "./SidenavCard.vue";

export default {
  name: "SidenavList",
  props: {
    cardBg: String
  },
  data() {
    return {
      title: "Argon Dashboard 2",
      controls: "dashboardsExamples",
      isActive: "active"
    };
  },
  components: {
    SidenavCard
  },
  methods: {
    getRoute() {
      const routeArr = this.$route.path.split("/");
      return routeArr[1];
    }
  }
};
</script>
