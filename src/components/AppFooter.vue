<script setup></script>
<template>
  <v-footer>
    <div class="main-container">
      <div class="text">
        Мы используем файлы cookie, чтобы предоставить пользователям больше
        возможностей при посещении сайта ЗаймГуру.ру. Условия использования
        <RouterLink to="/" target="_blank">смотрите здесь</RouterLink>.
      </div>
      <div class="text">
        Сервис не занимается деятельностью по предоставлению банковских услуг и
        выдаче займов. Содержание сайта не является рекомендацией или офертой,
        вся информация носит ознакомительный характер. При использовании
        материалов гиперссылка на ZaimGuru.ru обязательна.
      </div>
      <div class="text">
        ИП Иванов Ю.М. ИНН: 397425637163. ОГРНИП: 287362545367208. Свидетельство
        на товарный знак № 163476 от 18.08.2024.
      </div>
      <div class="text">
        <RouterLink to="/" target="_blank"
          >Политика конфиденциальности</RouterLink
        >
      </div>
      <div class="text">
        <RouterLink to="/" target="_blank"
          >Пользовательское соглашение</RouterLink
        >
      </div>
      <div class="text">© ЗаймГуру, 2024-2025</div>
    </div>
  </v-footer>
</template>

<style scoped lang="scss">
.main-container {
  padding: 32px 16px;
  background-color: rgba(255, 255, 255, 1);
  display: flex;
  flex-direction: column;
  gap: 8px;
  align-items: center;
  @include footerText;
}
</style>
