<script setup lang="ts">
import { LuckyWheel } from '@lucky-canvas/vue';

const blocks = [{ padding: '13px', background: '#617df2' }];
const prizes = [
  { fonts: [{ text: '0', top: '10%' }], background: '#e9e8fe' },
  { fonts: [{ text: '1', top: '10%' }], background: '#b8c5f2' },
  { fonts: [{ text: '2', top: '10%' }], background: '#e9e8fe' },
  { fonts: [{ text: '3', top: '10%' }], background: '#b8c5f2' },
  { fonts: [{ text: '4', top: '10%' }], background: '#e9e8fe' },
  { fonts: [{ text: '5', top: '10%' }], background: '#b8c5f2' }
];
const buttons = [
  {
    radius: '35%',
    background: '#8a9bf3',
    pointer: true,
    fonts: [{ text: 'START', top: '-10px' }]
  }
];

const luckyWheel = ref<InstanceType<typeof LuckyWheel> | null>(null);

function handleStart() {
  if (!luckyWheel.value) {
    return;
  }
  luckyWheel.value.play();
  setTimeout(() => {
    luckyWheel.value?.stop(0);
  }, 3000);
}

function handleEnd(prize: any) {
  console.log(prize);
}
</script>

<template>
  <div>
    <ClientOnly>
      <LuckyWheel
        ref="luckyWheel"
        width="300px"
        height="300px"
        :prizes="prizes"
        :blocks="blocks"
        :buttons="buttons"
        @start="handleStart"
        @end="handleEnd"
      ></LuckyWheel>
    </ClientOnly>
  </div>
</template>

<style scoped></style>
