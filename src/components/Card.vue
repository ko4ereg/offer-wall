<script setup>
const openCard = ref(false);
const tab = ref(1);

const props = defineProps({
  card: Object,
});

const getIcon = (icon) => {
  
  return new URL(`/src/assets/icons/${icon}`, import.meta.url).href;
};
</script>

<template>
  <v-dialog
    transition="dialog-bottom-transition"
    width="100%"
    height="100%"
    v-model="openCard"
    style="margin: 0"
    ><v-card elevation="3" class="overlay-card" width="100%" height="100%">
      <v-card-title>
        <div class="title">
          <v-img :src="getIcon(card.icon)"></v-img>
          <span>{{ card.title }}</span>
        </div>
        <v-icon @click="openCard = false" color="#B3B3B3"
          >mdi-close</v-icon
        ></v-card-title
      >
      <v-card-text>
        <v-tabs v-model="tab" selected-class="selectedTab">
          <v-tab :value="1">Условия</v-tab>
          <v-tab :value="2">Требования и документы</v-tab>
        </v-tabs>
        <v-tabs-window v-model="tab">
          <v-tabs-window-item style="height: 100%" :value="1">
            <div class="list-block">
              <div class="item">Сумма <span>от 3 000 до 30 000 ₽</span></div>
              <div class="item">Ставка в день <span>0,8%</span></div>
              <div class="item">
                Полная стоимость займа <span>292% годовых</span>
              </div>
              <div class="item">Срок <span>от 7 до 30 дней</span></div>
              <div class="item">Одобрение <span>74%</span></div>
              <div class="item">
                Время рассмотрения заявки <span>15 минут</span>
              </div>
            </div>
          </v-tabs-window-item>
          <v-tabs-window-item style="height: 100%" :value="2">
            <div class="list-block">
              <div class="item">Возраст <span>от 18 до 100</span></div>
              <div class="item">Документы <span>паспорт РФ</span></div>
            </div>
          </v-tabs-window-item>
        </v-tabs-window>
      </v-card-text>
    </v-card></v-dialog
  >
  <div class="card">
    <div class="info">
      <div class="title">
        <v-img :src="getIcon(card.icon)"></v-img>
        <span>{{ card.title }}</span>
      </div>
      <div class="offer">{{ card.offer }}</div>
      <div class="text bold">{{ card.textBold }}</div>
      <div class="text">{{ card.aproove }}</div>
    </div>
    <div class="buttons">
      <v-btn
        @click="openCard = true"
        size="x-small"
        style="border-radius: 8px; padding: 0"
        color="rgba(242, 242, 247, 1)"
        elevation="0"
        height="40px"
        width="40px"
      >
        <v-icon size="16" color="rgba(117, 117, 117, 1)"
          >mdi-information-outline</v-icon
        >
      </v-btn>
      <v-btn height="40px" elevation="0" color="#FC0" style="border-radius: 8px"
        >Получить</v-btn
      >
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  display: flex;
  padding: 12px;
  flex-direction: column;
  align-items: flex-start;
  gap: 12px;
  border-radius: 8px;
  background: rgba(255, 255, 255, 1);
  flex: 0 1 48%;
  .info {
    width: 100%;
    display: flex;
    height: 140px;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-start;
    gap: 8px;
    .title {
      display: flex;
      @include defaultText;
      font-size: $font-size-small;
      max-height: 40px;
      align-items: center;
      gap: 4px;

      .v-img {
        height: 40px;
        width: 40px;
      }
    }
    .offer {
      display: flex;
      padding: 0px 3px;
      width: 100%;
      justify-content: center;
      align-items: center;
      gap: 10px;
      border-radius: 4px;
      background: rgba(255, 59, 48, 0.2);
      color: #ff3b30;
      font-size: $font-size-x-small;
    }
    .text {
      @include defaultText;
    }

    .bold {
      font-weight: 600;
    }
  }
  .buttons {
    display: flex;
    align-items: flex-start;
    gap: 4px;
    align-self: stretch;

    .v-btn {
      display: flex;
      align-items: center;
      justify-content: center;
      text-transform: none;
      color: white !important;
      @include defaultText;
    }
  }
}

@media (max-width: 419px) {
  .card {
    flex: 0 1 48%;
    .info {
      .title {
        font-size: 15px;
        .v-img {
          height: 35px;
          width: 35px;
        }
      }
    }
    .buttons {
      .v-btn {
        padding: 0 9px;
        @include defaultText;
      }
    }
  }
}
@media (max-width: 384px) {
  .card {
    padding: 9px;
  }
}
@media (max-width: 374px) {
  .card {
    padding: 8px;
    .info {
      .offer {
        font-size: 11px;
      }
    }
    .buttons {
      .v-btn {
        padding: 0 12px;
        font-size: 14px;
      }
    }
  }
}

:deep(.v-overlay__content) {
  bottom: 0;
  margin: 0 !important;
  max-width: unset !important;
  max-height: unset !important;
}
.overlay-card {
  border-radius: 50px 50px 0 0 !important;

  padding: 44px 16px 8px;
  display: flex;
  flex-direction: column;
  gap: 24px;
  .v-card-title {
    display: flex;
    padding: 0;
    justify-content: space-between;

    .v-icon {
      cursor: pointer;
    }
    .title {
      font-weight: 400;
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 20px;
      line-height: 120%;
      .v-img {
        height: 48px;
        width: 48px;
      }
    }
  }

  .v-card-text {
    padding: 0 !important;
    .list-block {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      gap: 16px;
      align-self: stretch;
      padding-top: 24px;
      @include defaultText;
      .item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        align-self: stretch;
        span {
          font-weight: 600;
        }
      }
    }
  }
}

:deep(.v-tab) {
  @include defaultText;
  text-transform: none;
}

@media (max-width: 400px) {
  :deep(.v-tab) {
    font-size: 14px;
  }
}
</style>
