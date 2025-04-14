<script setup>
const name = ref("");
const email = ref("");
const message = ref("");

const form = ref(false);

const required = (v) => !!v || "Это поле обязательно для заполнения";

const onSubmit = () => {
  submitSuccess.value = true;
  if (!form.value) return;
};

const submitSuccess = ref(false);
</script>

<template>
  <div class="main-container">
    <template v-if="!submitSuccess">
      <div class="title">Заполните форму для обращения</div>
      <v-form
        validate-on="submit"
        @submit="onSubmit"
        v-model="form"
        class="w-100"
      >
        <v-text-field
          validate-on="lazy input"
          variant="solo"
          :rules="[required]"
          v-model="name"
          bg-color="#F5F5F5"
          placeholder="ФИО"
        ></v-text-field>
        <v-text-field
          validate-on="lazy input"
          :rules="[required]"
          variant="solo"
          v-model="email"
          bg-color="#F5F5F5"
          placeholder="Email"
        ></v-text-field>
        <v-text-field
          validate-on="lazy input"
          variant="solo"
          :rules="[required]"
          v-model="message"
          bg-color="#F5F5F5"
          placeholder="Сообщение"
        ></v-text-field>
        <v-btn
          type="submit"
          height="40px"
          elevation="0"
          color="#FC0"
          style="border-radius: 8px; margin-top: 16px"
          block
          >Отправить</v-btn
        >
      </v-form>
    </template>
    <template v-else>
      <div class="success">
        <div class="success-title">Обращение отправлено</div>
        <div class="text">
          Спасибо за вашу обратную связь, она помогает нам становиться лучше
        </div>
      </div>
    </template>
  </div>
</template>

<style lang="scss" scoped>
.main-container {
  background-color: white;
  padding: 16px;
  display: flex;
  min-height: calc(100vh - 48px);
  flex-direction: column;
  gap: 32px;
  .title {
    text-align: center;
    @include defaultText;
  }

  .v-form {
    display: flex;
    flex-direction: column;
    gap: 16px;
    :deep(.v-field--variant-solo),
    .v-field--variant-solo-filled {
      box-shadow: none !important;
    }
    .v-btn {
      text-transform: none;
      color: white !important;
      @include defaultText;
    }
  }
  .success {
    display: flex;

    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 8px;
    flex: 1 0 0;
    align-self: stretch;
    min-height: calc(100vh - 48px);
    .success-title {
      @include defaultText;
      font-size: 20px;
      line-height: 120%;
    }
    .text {
      text-align: center;
      @include defaultText;
    }
  }
}
</style>
