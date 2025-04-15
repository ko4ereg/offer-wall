<script setup>
const categories = ref([
  {
    label: "Все займы",
    isSelected: false,
  },
  {
    label: "Займ на карту",
    isSelected: true,
  },
  {
    label: "Займ 0%",
    isSelected: false,
  },
  {
    label: "Онлайн",
    isSelected: false,
  },
  {
    label: "Все МФО",
    isSelected: false,
  },
  {
    label: "До зарплаты",
    isSelected: false,
  },
  {
    label: "Без процентов",
    isSelected: false,
  },
  {
    label: "Первый без процентов",
    isSelected: false,
  },
  {
    label: "Через Госуслуги",
    isSelected: false,
  },
]);

const selected = ref(0);

const select = (index) => {
  selected.value = index;
};


</script>
<template>
  <div class="categories">
    <div class="categories-scroll">
      <div
        @click="select(index)"
        class="category"
        :class="{ active: selected === index }"
        v-for="(item, index) in categories"
      >
        {{ item.label }}
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.categories {
  .categories-scroll {
    padding: 8px 5px;
    @include defaultText;
    display: flex;
    align-items: center;
    gap: 8px;
    overflow: auto;
    .category {
      display: flex;
      padding: 6px 12px;
      justify-content: center;
      align-items: center;
      gap: 8px;
      height: 32px;
      cursor: pointer;
      font-size: $font-size-small;
      transition: 0.2s ease-out;
      white-space: nowrap;
      border-radius: 8px;
    }

    .active {
      border-radius: 8px;
      background: rgb(146, 212, 91);
    }
  }
}
</style>
