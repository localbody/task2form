<script setup>
import { ref } from 'vue'
import BaseButton from '@/components/UI/BaseButton.vue'
import InputText from '@/components/UI/InputText.vue'
import InputCheckbox from '@/components/UI/InputCheckbox.vue'
import InputRadio from '@/components/UI/InputRadio.vue'
import ProgressItem from '@/components/UI/ProgressItem.vue'

const countSteps = 4
const currentStep = ref(1)

const formsData = ref({
  name: '',
  email: '',
  phone: '',
  company: '',
  services: [],
  budget: '1',
})

const onClickSubmit = (event) => {
  localStorage.setItem('formsData', JSON.stringify(formsData.value))
}

const onClickNextStep = (event) => {
  if (currentStep.value < 4) currentStep.value++
}

const onClickPreviousStep = (event) => {
  if (currentStep.value > 1) currentStep.value--
}
</script>

<template>
  <div class="container">
    <div class="form">
      <div class="form__progress progress">
        <ProgressItem
          v-for="step in countSteps"
          :currentStep="currentStep"
          :step="step"
        />
      </div>

      <hr class="form__divider" />

      <div class="form__steps">
        <!-- step 1 -->
        <div v-show="currentStep == 1" class="form__content">
          <h1 class="form__title">Contact details</h1>

          <h2 class="form__subtitle">
            Lorem ipsum dolor sit amet consectetur adipisc.
          </h2>

          <div class="form__items">
            <InputText
              v-model="formsData.name"
              label="Name"
              icon="name"
              placeholder="John Carter"
            />

            <InputText
              v-model="formsData.email"
              label="Email"
              icon="email"
              placeholder="Email address"
            />
            <InputText
              v-model="formsData.phone"
              label="Phone Number"
              icon="phone"
              placeholder="(123) 456 - 7890"
            />
            <InputText
              v-model="formsData.company"
              label="Company"
              icon="company"
              placeholder="Company name"
            />
          </div>
        </div>

        <!-- step 2 -->
        <div v-show="currentStep == 2" class="form__content">
          <h1 class="form__title">Our services</h1>

          <h2 class="form__subtitle">
            Please select which service you are interested in.
          </h2>

          <div class="form__items">
            <InputCheckbox
              v-model="formsData.services"
              name="services"
              value="development"
              icon="development"
              label="Development"
            />
            <InputCheckbox
              v-model="formsData.services"
              name="services"
              value="web_design"
              icon="web_design"
              label="Web Design"
            />
            <InputCheckbox
              v-model="formsData.services"
              name="services"
              value="marketing"
              icon="marketing"
              label="Marketing"
            />
            <InputCheckbox
              v-model="formsData.services"
              name="services"
              value="other"
              icon="other"
              label="Other"
            />
          </div>
        </div>

        <!-- step 3 -->
        <div v-show="currentStep == 3" class="form__content">
          <h1 class="form__title">What’s your project budget?</h1>

          <h2 class="form__subtitle">
            Please select the project budget range you have in mind.
          </h2>

          <div class="form__items">
            <InputRadio
              v-model="formsData.budget"
              name="budget"
              value="1"
              label="$5.000 - $10.000"
            />
            <InputRadio
              v-model="formsData.budget"
              name="budget"
              value="2"
              label="$10.000 - $20.000"
            />
            <InputRadio
              v-model="formsData.budget"
              name="budget"
              value="3"
              label="$20.000 - $50.000"
            />
            <InputRadio
              v-model="formsData.budget"
              name="budget"
              value="4"
              label="$50.000 +"
            />
          </div>
        </div>

        <!-- step 4 -->
        <div v-show="currentStep == 4" class="form__content">
          <img class="image-ok" src="./assets/images/ok.svg" alt="" />

          <h1 class="form__title center">Submit your quote request</h1>

          <h2 class="form__subtitle center">
            Please review all the information you previously typed in the past
            steps, and if all is okay, submit your message to receive a project
            quote in 24 - 48 hours.
          </h2>

          <div class="wrapper-center">
            <BaseButton @click="onClickSubmit">Submit</BaseButton>
          </div>
        </div>
      </div>
    </div>
    <div class="buttons">
      <BaseButton
        v-show="currentStep > 1"
        variant="secondary"
        @click="onClickPreviousStep"
        >Previous step</BaseButton
      >
      <BaseButton
        style="margin-left: auto"
        v-show="currentStep < 4"
        @click="onClickNextStep"
        >Next step</BaseButton
      >
    </div>
  </div>
</template>

<style scoped>
.container {
  background-color: #f7f7fb;
  display: grid;
  place-content: center;
  padding-block: 200px;
  height: 100vh;
}

@media (max-width: 720px) {
  .container {
    padding: 16px;
  }
}

.form {
  background-color: white;
  border: 1px solid #eff0f7;
  box-shadow: 0px 5px 16px rgba(8, 15, 52, 0.06);
  border-radius: 34px;
  width: fit-content;
  height: fit-content;
  margin-bottom: 32px;
  padding: 32px 52px 80px 52px;
  max-width: 700px;
}

@media (max-width: 720px) {
  .form {
    padding: 16px;
    display: grid;
    grid-template-columns: 70px 1px 1fr;
    column-gap: 10px;
  }
}

.progress {
  padding: 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 18px;
}

@media (max-width: 720px) {
  .progress {
    flex-direction: column;
    justify-content: center;
    padding-inline: 0;
    max-width: 75px;
  }
}

.form__divider {
  border: none;
  height: 1px;
  background-color: var(--neutral-color-400);
  margin: 0;
}

@media (max-width: 720px) {
  .form__divider {
    width: 1px;
    height: 100%;
  }
}

.form__steps {
  padding-inline: 16px;
}

.form__content {
  margin-top: 64px;
}

.form__title {
  font-size: 24px;
  font-weight: bold;
  line-height: 35px;
  color: var(--neutral-color-800);
}

.form__subtitle {
  font-weight: 400;
  font-size: 18px;
  line-height: 30px;
  color: var(--neutral-color-600);
}

.form__items {
  margin-top: 40px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 28px;
  row-gap: 44px;
}

@media (max-width: 720px) {
  .form__items {
    grid-template-columns: 1fr;
  }
}

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

.buttons {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

@media (max-width: 400px) {
  .buttons {
    display: grid;
    grid-template-columns: 1fr;
    gap: 16px;
  }
}
</style>
