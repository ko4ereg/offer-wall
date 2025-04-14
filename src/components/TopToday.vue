<script setup></script>
<template>
  <div class="top">
    <div class="top-title">Топ одобрений сегодня</div>
    <div class="icons">
      <v-img height="40px" width="40px" src="@/assets/icons/bankir.png"></v-img>

      <v-img height="40px" width="40px" src="@/assets/icons/bistro.png"></v-img>

      <v-img
        height="40px"
        width="40px"
        src="@/assets/icons/boostra.png"
      ></v-img>

      <v-img height="40px" width="40px" src="@/assets/icons/ekva.png"></v-img>

      <v-img
        height="40px"
        width="40px"
        src="@/assets/icons/finters.png"
      ></v-img>

      <v-img height="40px" width="40px" src="@/assets/icons/joy.png"></v-img>

      <v-img
        height="40px"
        width="40px"
        src="@/assets/icons/srochno.png"
      ></v-img>

      <v-img
        height="40px"
        width="40px"
        src="@/assets/icons/srochno.png"
      ></v-img>

      <v-img
        height="40px"
        width="40px"
        src="@/assets/icons/srochno.png"
      ></v-img>

      <v-img
        height="40px"
        width="40px"
        src="@/assets/icons/srochno.png"
      ></v-img>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.top {
  padding: 16px 0;
  @include defaultText;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 12px;

  .top-title {
    padding: 0 16px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
  }
  .icons {
    display: flex;
    align-items: center;
    gap: 12px;
    overflow: auto;
    padding: 0 16px;
    max-width: 100%;
  }
}
</style>
