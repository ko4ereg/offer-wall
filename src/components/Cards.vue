<script setup>
const cards = ref([
  {
    title: "Быстроденьги",
    icon: "bistro.png",
    time: 4,

    textBold: "от 3 000 до 30 000 ₽",
    offer: "Одобрение 74%",
  },
  {
    title: "Срочно Деньги",
    icon: "srochno.png",
    time: 16,
    textBold: "от 3 000 до 100 000 ₽",
    offer: "Одобрение 58%",
  },
  {
    title: "CreditPlus",
    icon: "plus.png",
    time: 2,
    textBold: "от 3 000 до 30 000 ₽",
    offer: "Одобрение 74%",
  },
  {
    title: "Boostra",
    icon: "boostra.png",
    time: 7,
    textBold: "от 3 000 до 15 000 ₽",
    offer: "Одобрение 82%",
  },
  {
    title: "Эквазайм",
    icon: "ekva.png",
    time: 12,
    textBold: "от 3 000 до 100 000 ₽",
    offer: "Одобрение 58%",
  },
  {
    title: "Finters",
    icon: "finters.png",
    time: 1,
    textBold: "от 3 000 до 30 000 ₽",
    offer: "Займи Займ у",
  },
  {
    title: "Вэббанкир",
    icon: "bankir.png",
    time: 15,
    textBold: "от 3 000 до 30 000 ₽",
    offer: "Одобрение 58%",
  },
  {
    title: "Joymoney",
    icon: "joy.png",
    time: 5,
    textBold: "от 3 000 до 15 000 ₽",
    offer: "Одобрение 74%",
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
