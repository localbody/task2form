<script setup>
const props = defineProps({
  step: {
    type: Number,
    default: 1,
  },
  currentStep: {
    type: Number,
    required: true,
  },
})
</script>

<template>
  <div
    class="progress__item"
    :class="{
      'progress__item--complete': currentStep > step,
      'progress__item--active': currentStep == step,
    }"
  >
    <span class="progress__item-index">{{ step }}</span>
    <div class="progress__item-bar"></div>
  </div>
</template>

<style scoped>
.progress__item {
  display: flex;
  align-items: center;
  gap: 18px;
}

@media (max-width: 720px) {
  .progress__item {
    flex-direction: column;
    /* height: 100%; */
  }
}

.progress__item-bar {
  background-color: var(--neutral-color-300);
  border-radius: 40px;
  width: 98px;
  height: 6px;
  display: block;
}

@media (max-width: 720px) {
  .progress__item-bar {
    transform: rotate(90deg);
    margin-top: 21px;
    margin-bottom: 21px;
  }
}

.progress__item:last-child .progress__item-bar {
  display: none;
}

.progress__item-index {
  width: 34px;
  height: 34px;
  color: var(--neutral-color-600);
  background-color: var(--neutral-color-300);
  border-radius: 100%;
  font-size: 16px;
  display: grid;
  place-content: center;
}

.progress__item--active .progress__item-index,
.progress__item--complete .progress__item-index {
  background-color: var(--primary-color);
  color: var(--neutral-color-100);
}

.progress__item--active .progress__item-bar::before,
.progress__item--complete .progress__item-bar::before {
  content: '';
  display: block;
  width: 50%;
  height: 100%;
  border-radius: 40px;
  background-color: var(--primary-color);
}

.progress__item--complete .progress__item-bar::before {
  width: 100%;
}
</style>
