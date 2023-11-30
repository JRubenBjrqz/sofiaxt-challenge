<script lang="ts">
import Sidebar from '../components/Sidebar.vue';

export default {
  components: { 
    Sidebar 
  },
  name: 'App',
  created () {
    document.title = "Inicio";
  }
}
</script>

<template>
    <Sidebar/>
</template>

<style scoped>
</style>