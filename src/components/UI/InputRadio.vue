<script setup>
const props = defineProps({
  modelValue: String,
  name: {
    type: String,
    required: true,
  },
  value: {
    type: String,
    default: '1',
  },
  label: {
    type: String,
    default: '',
  },
})

const emit = defineEmits(['update:modelValue'])
</script>

<template>
  <div class="form__item">
    <input
      type="radio"
      :name="name"
      :value="value"
      :id="value"
      :checked="modelValue == value"
      @change="emit('update:modelValue', value)"
    />
    <label :for="value" class="form__item-label">{{ label }}</label>
  </div>
</template>

<style scoped>
input[type='radio'] {
  display: none;
}

input[type='radio'] + label {
  cursor: pointer;
  background: var(--neutral-color-100);
  border: 1px solid var(--neutral-color-300);
  box-shadow: 0px 2px 6px rgba(19, 18, 66, 0.07);
  border-radius: 16px;
  padding: 24px;
  display: flex;
  align-items: center;
  gap: 12px;
  border: 2px solid transparent;
}

input[type='radio'] + label::before {
  content: '';
  width: 25px;
  height: 25px;
  border-radius: 100%;
  background: var(--neutral-color-100);
  border: 1px solid var(--neutral-color-400);
  box-shadow: inset 0px -3px 7px rgba(20, 20, 43, 0.08);
  flex-shrink: 0;
}

input[type='radio']:checked + label::before {
  content: '';
  background: var(--neutral-color-100);
  border: 7px solid var(--primary-color);
  box-shadow: inset 0px -3px 7px rgba(20, 20, 43, 0.08);
}

input[type='radio']:checked + label {
  border: 2px solid var(--primary-color);
  box-shadow: 0px 2px 11px rgba(69, 65, 164, 0.06),
    0px 4px 10px rgba(31, 37, 89, 0.07);
}
</style>
