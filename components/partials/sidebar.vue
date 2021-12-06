<template>
  <div class="main-sidebar">
    <aside id="sidebar-wrapper">
      <div class="sidebar-brand">
        <a href="index.html">ADM-BQC Dept.</a>
      </div>
      <div class="sidebar-brand sidebar-brand-sm">
        <a href="index.html">CA</a>
      </div>
      <ul class="sidebar-menu">
        <li v-for="(menu, i) in listMenu" :key="i">
          <nuxt-link class="nav-link" :to="menu.to">
            <i :class="menu.icon"></i>
            <span>{{ menu.name }}</span></nuxt-link
          >
        </li>
      </ul>
    </aside>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listMenu: [
        {
          name: "Dashboard",
          icon: "fas fa-home",
          to: "/",
          role: "[admin],[tutor]"
        },
        {
          name: "Semua Kelas",
          icon: "fas fa-igloo",
          to: "/semua-kelas"
        },
        {
          name: "Kelas Saya",
          icon: "far fa-bookmark",
          to: "/kelas-saya"
        },
        {
          name: "Layout",
          icon: "fas fa-pen",
          to: "/example/layout-clean"
        },
        {
          name: "Data Binding",
          icon: "fas fa-book",
          to: "/example/data-binding"
        },
        {
          name: "Methods",
          icon: "fas fa-plane",
          to: "/example/methods"
        },
        {
          name: "Computed",
          icon: "fas fa-laptop",
          to: "/example/computed"
        },
        {
          name: "Watcher",
          icon: "fas fa-clock",
          to: "/example/watcher"
        },
        {
          name: "Emit",
          icon: "fas fa-clone",
          to: "/example/emit"
        },
        {
          name: "Emit 2",
          icon: "fas fa-copy",
          to: "/example/emit-2"
        }
      ]
    };
  }
};
</script>
