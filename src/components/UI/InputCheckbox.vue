<script setup>
const props = defineProps({
  modelValue: Array,
  name: {
    type: String,
    default: '',
  },
  value: {
    type: String,
    default: '',
  },
  icon: {
    type: String,
    default: '',
  },
  label: {
    type: String,
    default: '',
  },
})
const emit = defineEmits(['update:modelValue'])

const toggle = () => {
  const newValue = props.modelValue.includes(props.value)
    ? props.modelValue.filter((v) => v !== props.value)
    : [...props.modelValue, props.value]
  emit('update:modelValue', newValue)
}
</script>

<template>
  <div class="form__item">
    <input
      type="checkbox"
      :name="name"
      :value="value"
      :id="value"
      :checked="modelValue.includes(value)"
      @change="toggle"
    />
    <label
      :for="value"
      :class="['form__item-label', `form__item-label--${icon}`]"
      >{{ label }}</label
    >
  </div>
</template>

<style scoped>
input[type='checkbox'] {
  display: none;
}

input[type='checkbox'] + label {
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

input[type='checkbox'] + label::before {
  content: '';
  width: 66px;
  height: 66px;
  border-radius: 100%;
  background-color: var(--primary-color-opacity15);
  background-position: center;
  background-repeat: no-repeat;
  background-size: 42px;
}

input[type='checkbox']:checked + label {
  border: 2px solid var(--primary-color);
  box-shadow: 0px 2px 11px rgba(69, 65, 164, 0.06),
    0px 4px 10px rgba(31, 37, 89, 0.07);
}

.form__item-label--development::before {
  background-image: url(@/assets/icons/development.svg);
}

.form__item-label--web_design::before {
  background-image: url(@/assets/icons/web-design.svg);
}

.form__item-label--marketing::before {
  background-image: url(@/assets/icons/marketing.svg);
}

.form__item-label--other::before {
  background-image: url(@/assets/icons/other.svg);
}
</style>
