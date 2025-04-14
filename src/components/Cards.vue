<script setup></script>

<template>
  <Categories />
  <div class="main-container">
    <Card v-for="n in 7" />
  </div>
</template>

<style lang="scss" scoped>
.main-container {
  padding: 8px 16px 16px;
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}
@media (max-width: 420px) {
  .main-container {
    gap: 5px;
  }
}
</style>
