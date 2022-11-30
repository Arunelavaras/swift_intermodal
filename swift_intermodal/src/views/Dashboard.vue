<template>
    <h1>The sidebar is {{ collapsed ? 'closed' : 'open' }}</h1>
    <button @click="toggleSidebar">Toggle Sidebar</button>
  </template>
  
  <script lang="ts">
  import { collapsed, toggleSidebar } from '@/components/sidebar/state'
import { defineComponent } from 'vue';
export default defineComponent ({
    name:'DashboardNew',
    setup() {
      return { collapsed, toggleSidebar }
    }
  })
  </script>
  