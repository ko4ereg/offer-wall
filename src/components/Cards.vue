<script setup>
const cards = ref([
  {
    title: "Быстроденьги",
    icon: "bistro.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 74%",
  },
  {
    title: "Срочно Деньги",
    icon: "srochno.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 100 000 ₽",
    aproove: "Одобрение 58%",
  },
  {
    title: "CreditPlus",
    icon: "plus.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 74%",
  },
  {
    title: "Boostra",
    icon: "boostra.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 82%",
  },
  {
    title: "Эквазайм",
    icon: "ekva.png",
    offer: "Первый займ бесплатно",
    textBold: "3 000 - 15 000 ₽",
    aproove: "Одобрение 58%",
  },
  {
    title: "Finters",
    icon: "finters.png",
    offer: "Займи Займ у Займера Онлайн",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 74%",
  },
  {
    title: "Вэббанкир",
    icon: "bankir.png",
    offer: "Займи Займ у Займера Онлайн",
    textBold: "3 000 - 30 000 ₽",
    aproove: "Одобрение 58%",
  },
  {
    title: "Joymoney",
    icon: "joy.png",
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
