<script setup>
const cards = ref([
  {
    title: "Быстроденьги",
    icon: "src/assets/icons/bistro.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 74%",
  },
  {
    title: "Срочно Деньги",
    icon: "src/assets/icons/srochno.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 100 000 ₽",
    aproove: "Одобрение 58%",
  },
  {
    title: "CreditPlus",
    icon: "src/assets/icons/plus.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 74%",
  },
  {
    title: "Boostra",
    icon: "src/assets/icons/boostra.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 82%",
  },
  {
    title: "Эквазайм",
    icon: "src/assets/icons/ekva.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 15 000 ₽",
    aproove: "Одобрение 58%",
  },
  {
    title: "Finters",
    icon: "src/assets/icons/finters.png",
    offer: "Займи Займ у Займера Онлайн",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 74%",
  },
  {
    title: "Вэббанкир",
    icon: "src/assets/icons/bankir.png",
    offer: "Займи Займ у Займера Онлайн",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 58%",
  },
  {
    title: "Joymoney",
    icon: "src/assets/icons/joy.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 74%",
  },
]);
</script>

<template>
  <Categories />
  <div class="main-container">
    <Card :card="card" v-for="card in cards" />
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
