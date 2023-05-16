<template>
  <q-page class="q-pa-md">
    <q-btn
      color="primary"
      :label="counter"
      size="xl"
      class="full-width q-mb-md"
    />

    <div class="row text-center">
      <div class="col">
        <q-btn
          flat
          round
          color="negative"
          icon="remove"
          size="lg"
          @click="decreaseCounter"
        />
      </div>
      <div class="col">
        <q-btn
          flat
          round
          color=""
          icon="restart_alt"
          size="lg"
          @click="resetCounter"
        />
      </div>
      <div class="col">
        <q-btn
          flat
          round
          color="positive"
          icon="add"
          size="lg"
          @click="increaseCounter"
        />
      </div>
    </div>

    <q-btn
      flat
      round
      icon="power_settings_new"
      size="sm"
      class="absolute-bottom-right"
      @click="quitApp"
    />
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';

let counter = ref(0);

const increaseCounter = () => {
  counter.value++;
};

const decreaseCounter = () => {
  counter.value--;
};

const resetCounter = () => {
  counter.value = 0;
};

const quitApp = () => {
  window.myAPI.quitApp();
};
</script>
