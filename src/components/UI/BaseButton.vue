<script setup>
const props = defineProps({
  variant: {
    type: String,
    default: 'primary',
    validator: (value) => ['primary', 'secondary'].includes(value),
  },
})

const emit = defineEmits(['click'])

const handleClick = (event) => {
  emit('click', event)
}
</script>

<template>
  <button :class="['button', `button--${variant}`]" @click="handleClick">
    <slot></slot>
  </button>
</template>

<style scoped>
.button {
  display: block;
  cursor: pointer;
  width: fit-content;
  padding: 20px 40px;
  font-size: 18px;
  line-height: 20px;
  border-radius: 56px;
}

@media (max-width: 400px) {
  .button {
    width: 100%;
  }
}

.button--primary {
  border: none;
  font-weight: bold;
  box-shadow: 0px 3px 12px rgba(74, 58, 255, 0.18);
  color: var(--neutral-color-100);
  background: var(--primary-color);
}

.button--secondary {
  background-color: var(--neutral-color-100);
  font-weight: normal;
  color: var(--primary-color);
  border: 1px solid var(--primary-color);
}
</style>
