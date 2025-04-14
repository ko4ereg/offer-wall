<template>
  <AppHeader></AppHeader>
  <v-main>
    <div class="main">
      <router-view />
    </div>
  </v-main>

  <AppFooter />
</template>

<script setup>
//
</script>
<style lang="scss" scoped>
.main {
  background-color: rgba(245, 245, 245, 1);
  height: 100%;
}
</style>
