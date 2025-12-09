<script setup></script>

<template>
  <div class="form">
    <div class="progress">
      <div class="progress__item">1</div>
      <div class="progress__item">2</div>
      <div class="progress__item">3</div>
      <div class="progress__item">4</div>
    </div>
    <hr />
    <h1 class="form__title">Contact details</h1>

    <h2 class="form__subtitle">
      Lorem ipsum dolor sit amet consectetur adipisc.
    </h2>

    <div class="form__items">
      <div class="form__item">
        <label class="form__item-label">Name</label>
        <input
          type="text"
          class="form__item-input form__item-input--name"
          placeholder="John Carter"
        />
      </div>
      <div class="form__item">
        <label class="form__item-label">Email</label>
        <input
          type="text"
          class="form__item-input form__item-input--email"
          placeholder="Email address"
        />
      </div>
      <div class="form__item">
        <label class="form__item-label">Phone Number</label>
        <input
          type="text"
          class="form__item-input form__item-input--phone"
          placeholder="(123) 456 - 7890"
        />
      </div>
      <div class="form__item">
        <label class="form__item-label">Company</label>
        <input
          type="text"
          class="form__item-input form__item-input--company"
          placeholder="Company name"
        />
      </div>
    </div>
  </div>
  <button>Next Step</button>
</template>

<style scoped></style>
