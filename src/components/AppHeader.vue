<script setup>
const drawer = ref(false);
const email = ref("");

watch(drawer, (val) => {
  document.body.style.overflow = val ? "hidden" : "";
});

onBeforeUnmount(() => {
  document.body.style.overflow = "";
});
</script>

<template>
  <v-app-bar absolute app elevation="0" :height="48" location="top">
    <div class="main-container">
      <div class="d-flex align-center justify-space-between header">
        <RouterLink to="/"> <Logo /></RouterLink>
        <v-icon @click="drawer = !drawer">{{
          drawer ? "mdi-close" : "mdi-menu"
        }}</v-icon>
      </div>
    </div>
  </v-app-bar>
  <v-navigation-drawer
    location="top"
    border="none"
    mobile
    v-model="drawer"
    temporary
  >
    <div class="main-container">
      <div class="d-flex flex-column drawer">
        <div class="list d-flex flex-column">
          <RouterLink to="/">Главная</RouterLink>
          <RouterLink to="/licence">Список лицензий</RouterLink>
          <RouterLink to="/terms">Условия кредитования</RouterLink>
          <RouterLink to="/support">Написать обращение</RouterLink>
        </div>

        <v-divider
          color="rgba(202, 196, 208, 1)"
          thickness="1px"
          width="100%"
        ></v-divider>

        <div class="list d-flex flex-column">
          <div class="subscribe">
            Подпишитесь на уведомления об обновлении рейтингов займов
          </div>
          <v-form class="w-100">
            <v-text-field
              variant="solo"
              v-model="email"
              bg-color="#F5F5F5"
              placeholder="Введите ваш email"
            ></v-text-field>
            <v-btn elevation="0" color="#FC0" style="border-radius: 8px" block
              >Подписаться</v-btn
            >
          </v-form>
        </div>
      </div>
    </div>
  </v-navigation-drawer>
</template>

<style scoped lang="scss">
.v-navigation-drawer {
  height: 100% !important;
  transform: translateY(-100%) !important;
  top: 0 !important;
}

.v-navigation-drawer--active {
  transform: translateY(0%) !important;
  top: 48px !important;
}

.drawer {
  padding-top: 16px;
  gap: 32px;
}
.list {
  gap: 16px;
  align-items: flex-start;
  a {
    color: inherit;
  }

  .subscribe {
    display: flex;
    align-items: center;
    justify-content: center;
    @include defaultText;
  }
  .v-btn {
    text-transform: none;
    color: white !important;
    @include defaultText;
  }
}
:deep(.v-field--variant-solo),
.v-field--variant-solo-filled {
  box-shadow: none !important;
}
</style>
