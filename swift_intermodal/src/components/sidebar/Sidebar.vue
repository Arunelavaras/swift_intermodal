<script lang="ts">
import SidebarLink from './SidebarLink.vue'
import { collapsed, toggleSidebar, sidebarWidth } from './state'


export default  ({
    name:'sidebarNew',
  props: {},
  components: { SidebarLink},
  setup() {
    return { collapsed, toggleSidebar, sidebarWidth }
  }
})
</script>

<template>
 
  <div class="sidebar" :style="{ width: sidebarWidth }">
    <h1>
      <span v-if="collapsed">
        <div>S</div>
        <div>T</div>
      </span>
      <span v-else>
        <div class="logo">
            <img src="../../assets/images/static_swift.svg" alt="" width="175" />
        </div>
      </span>
    </h1>

    <SidebarLink to="/" icon="fas fa-home">Home</SidebarLink>
    <SidebarLink to="/dashboard" icon="fas fa-columns">Dashboard</SidebarLink>
    <SidebarLink to="/analytics" icon="fas fa-chart-bar">Analytics</SidebarLink>
    <SidebarLink to="/friends" icon="fas fa-users">Friends</SidebarLink>
    <SidebarLink to="/image" icon="fas fa-image">Images</SidebarLink>

    <span
      class="collapse-icon"
      :class="{ 'rotate-180': collapsed }"
      @click="toggleSidebar"
    >
      <i class="fas fa-angle-double-left" />
    </span>
  </div>
</template>

<style>
:root {
  /* --sidebar-bg-color: #2f855a;
  --sidebar-item-hover: #38a169;
  --sidebar-item-active: #276749; */
  --sidebar-bg-color: #18468D;
  --sidebar-item-hover: #EAAA21;
  --sidebar-item-active: #DD9804;
}
</style>

<style scoped>
.sidebar{
  color: white;
  background-color: var(--sidebar-bg-color);
  float: left;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  bottom: 0;
  padding: 0.5em;

  transition: 0.3s ease;

  display: flex;
  flex-direction: column;
}

.sidebar h1 {
  height: 3.5em;
}

.collapse-icon {
  position: absolute;
  bottom: 0;
  padding: 0.75em;

  color: rgba(255, 255, 255, 0.7);

  transition: 0.2s linear;
}
.link[data-v-f923887a] {
    height:35px;
}
.rotate-180 {
  transform: rotate(180deg);
  transition: 0.2s linear;
}
</style>
