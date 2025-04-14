<script setup></script>

<template>
  <div class="card">
    <div class="info">
      <div class="title">
        <v-img src="@/assets/icons/bistro.png"></v-img>
        <span>Быстроденьги</span>
      </div>
      <div class="offer">Первый займ бесплатно</div>
      <div class="text bold">3 000 - 30 000 ₽</div>
      <div class="text">Одобрение 74%</div>
    </div>
    <div class="buttons">
      <v-btn
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
  }
}
</style>
