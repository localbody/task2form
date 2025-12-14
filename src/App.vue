<script setup></script>

<template>
  <div class="container">
    <div class="form">
      <div class="form__progress progress">
        <div class="progress__item progress__item--complete">
          <span class="progress__item-index">1</span>
          <div class="progress__item-bar"></div>
        </div>
        <div class="progress__item progress__item--active">
          <span class="progress__item-index">2</span>
          <div class="progress__item-bar"></div>
        </div>
        <div class="progress__item">
          <span class="progress__item-index">3</span>
          <div class="progress__item-bar"></div>
        </div>
        <div class="progress__item">
          <span class="progress__item-index">4</span>
          <div class="progress__item-bar"></div>
        </div>
      </div>

      <hr class="form__divider" />

      <div class="form__content">
        <h1 class="form__title">Contact details</h1>

        <h2 class="form__subtitle">
          Lorem ipsum dolor sit amet consectetur adipisc.
        </h2>

        <div class="form__items">
          <div class="form__item">
            <label class="form__item-label">Name</label>
            <div class="form__item-input form__item-input--name">
              <input type="text" placeholder="John Carter" />
            </div>
          </div>
          <div class="form__item">
            <label class="form__item-label">Email</label>
            <div class="form__item-input form__item-input--email">
              <input type="text" placeholder="Email address" />
            </div>
          </div>
          <div class="form__item">
            <label class="form__item-label">Phone Number</label>
            <div class="form__item-input form__item-input--phone">
              <input type="text" placeholder="(123) 456 - 7890" />
            </div>
          </div>
          <div class="form__item">
            <label class="form__item-label">Company</label>
            <div class="form__item-input form__item-input--company">
              <input type="text" placeholder="Company name" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <button class="button">Next step</button>
  </div>
</template>

<style scoped></style>
