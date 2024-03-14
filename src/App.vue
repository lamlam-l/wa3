<template>
  <main class="main">
    <Sidebar class="main_sidebar"/>
    <div class="main_content">
    </div>
  </main>
</template>

<script setup>
import Sidebar from "./components/sidebar.vue";
</script>

<style scoped>
.main {
  display: flex;
  flex-direction: row;
  height: 100vh;
}

.main_sidebar {
  flex-basis: 20%;
  min-width: 250px;
}

.main_content {
  flex: 1;
}
</style>
