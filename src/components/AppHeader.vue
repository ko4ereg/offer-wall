<script setup>
const drawer = ref(false);
const email = ref("");

watch(drawer, (val) => {
  document.body.style.overflow = val ? "hidden" : "";
});

const route = useRoute();
const page = computed(() => route.path);
onBeforeUnmount(() => {
  document.body.style.overflow = "";
});

const headerTitle = computed(() => {
  switch (page.value) {
    case "/licence":
      return "Список лицензий";
    case "/terms":
      return "Условия кредитования";
    case "/support":
      return "Обращение";
    case "/":
      return "Топ одобрений сегодня";
    default:
      return "";
  }
});

const modal = ref(false);

const form = ref(false);

const onSubmit = () => {
  console.log("submit");

  if (!form.value) return;
  modal.value = true;
};

const emailField = ref(null);
const resetValidation = async () => {
  if (emailField.value) {
    return emailField.value.resetValidation();
  }
};

const regEmail = (v) =>
  /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v.trim()) || "Введите корректный Email";
</script>

<template>
  <v-app-bar absolute app elevation="0" :height="48" location="top">
    <div class="main-container">
      <div class="d-flex align-center justify-space-between header">
        <div class="d-flex align-center" style="gap: 17px">
          <RouterLink to="/"> <Logo /></RouterLink>
          <div v-if="!drawer">
            {{ headerTitle }}
          </div>
        </div>
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
            Подпишитесь на уведомления <br />
            об обновлении рейтингов займов
          </div>
          <v-form
            validate-on="submit"
            v-model="form"
            @submit.prevent="onSubmit"
            class="w-100"
          >
            <v-text-field
              style="padding-bottom: 5px"
              ref="emailField"
              rounded="lg"
              @update:focused="resetValidation"
              validate-on="submit"
              :rules="[regEmail]"
              variant="solo"
              v-model="email"
              bg-color="#F5F5F5"
              placeholder="Введите ваш email"
            ></v-text-field>
            <v-btn
              elevation="0"
              type="submit"
              color="#FC0"
              style="border-radius: 8px"
              block
              >Подписаться</v-btn
            >
          </v-form>
        </div>
      </div>
    </div>
  </v-navigation-drawer>

  <v-dialog v-model="modal">
    <v-card elevation="3" class="overlay-card" width="100%" height="100%">
      <v-card-title>
        <v-icon
          style="position: absolute; top: 5px; right: 5px"
          @click="modal = false"
          color="#B3B3B3"
          >mdi-close</v-icon
        ></v-card-title
      >
      <v-card-text
        ><div class="d-flex align-center justify-center">
          Вы подписаны на уведомления
        </div></v-card-text
      ></v-card
    ></v-dialog
  >
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
    width: 100%;
    text-align: center;
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
