<script setup>
const props = defineProps({
  modelValue: String,

  label: {
    type: String,
    default: '',
  },

  icon: {
    type: String,
    default: '',
  },

  placeholder: {
    type: String,
    default: '',
  },

  isPhone: {
    type: Boolean,
    default: false,
  },

  error: {
    type: String,
    default: '',
  },
})

const emit = defineEmits(['update:modelValue'])
</script>

<template>
  <div class="form__item">
    <label class="form__item-label">{{ label }}</label>
    <div
      :class="[
        'form__item-input',
        `form__item-input--${icon}`,
        { 'form__item-input--phone': isPhone },
      ]"
    >
      <input
        type="text"
        :placeholder="placeholder"
        :value="modelValue"
        @input="emit('update:modelValue', $event.target.value)"
      />
      <span v-if="error" class="form__item-error">{{ error }}</span>
    </div>
  </div>
</template>

<style scoped>
.form__item {
  display: grid;
  row-gap: 18px;
  width: 100%;
}

.form__item-label {
  font-size: 18px;
  font-weight: 500;
  line-height: 20px;
  color: var(--neutral-color-800);
}

.form__item-error {
  position: absolute;
  bottom: -18px;
  left: 0;
  color: tomato;
  font-size: 13px;
}

.form__item-input {
  background-color: var(--neutral-color-100);
  border: 1px solid var(--neutral-color-300);
  box-shadow: 0px 2px 6px rgba(19, 18, 66, 0.07);
  border-radius: 46px;
  padding: 22px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
}

.form__item-input input[type='text'] {
  border: none;
  color: var(--neutral-color-600);
  font-size: 18px;
  line-height: 20px;
  width: 100%;
}

.form__item-input--phone::before {
  content: '+';
  font-size: 18px;
}

.form__item-input::after {
  content: '';
  width: 28px;
  height: 28px;
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
}

.form__item-input--name::after {
  background-image: url(@/assets/icons/name.svg);
}

.form__item-input--email::after {
  background-image: url(@/assets/icons/mail.svg);
}

.form__item-input--phone::after {
  background-image: url(@/assets/icons/phone.svg);
}

.form__item-input--company::after {
  background-image: url(@/assets/icons/company.svg);
}
</style>
