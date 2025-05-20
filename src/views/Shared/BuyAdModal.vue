<template>
  <v-dialog v-model="modal" max-width="400px">
    <!-- Кнопка для открытия модального окна -->
    <template v-slot:activator="{ props }">
      <v-btn v-bind="props" color="success">BUY</v-btn>
    </template>

    <!-- Карточка с информацией о покупке -->
    <v-card class="pa-4">
      <v-card-title class="text-h5 text-center">
        Buy It
      </v-card-title>

      <v-card-text class="text-center">
        <p>{{ ad?.title }}</p>
        <p class="text-subtitle-1">Price: {{ ad?.price }}$</p>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      </v-card-text>

      <v-card-actions class="justify-end">
        <v-btn color="grey darken-1" @click="modal = false">Cancel</v-btn>
        <v-btn color="success" @click="buyAd">Buy It</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    ad: Object, // Ожидаем объект объявления
  },
  data() {
    return {
      modal: false, // Управление открытием модального окна
    };
  },
  methods: {
    buyAd() {
      console.log(`Buying: ${this.ad?.title}`);
      this.modal = false; // Закрываем модальное окно после покупки
    },
  },
};
</script>

<style scoped>
/* Дополнительные стили */
.v-card {
  border-radius: 10px;
}

.v-btn {
  text-transform: none;
}
</style>