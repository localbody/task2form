<script setup>
const props = defineProps({
  variant: {
    type: String,
    default: 'primary',
    validator: (value) => ['primary', 'secondary'],
  },
})

const emit = defineEmits(['click'])

const handleClick = (event) => {
  emit('emit', event)
}
</script>

<template>
  <button
    :class="['button', `button--${variant}`]"
    @click="handleClick"
  ></button>
</template>

<style scoped></style>
