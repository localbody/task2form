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

      <!-- step 1 -->
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

      <!-- step 2 -->
      <div class="form__content">
        <h1 class="form__title">Our services</h1>

        <h2 class="form__subtitle">
          Please select which service you are interested in.
        </h2>

        <div class="form__items">
          <div class="form__item">
            <input type="checkbox" name="" id="development" checked />
            <label
              for="development"
              class="form__item-label form__item-label--development"
              >Development</label
            >
          </div>
          <div class="form__item">
            <input type="checkbox" name="" id="web_design" />
            <label
              for="web_design"
              class="form__item-label form__item-label--web_design"
              >Web Design</label
            >
          </div>
          <div class="form__item">
            <input type="checkbox" name="" id="marketing" />
            <label
              for="marketing"
              class="form__item-label form__item-label--marketing"
              >Marketing</label
            >
          </div>
          <div class="form__item">
            <input type="checkbox" name="" id="other" />
            <label for="other" class="form__item-label form__item-label--other"
              >Other</label
            >
          </div>
        </div>
      </div>

      <!-- step 3 -->
      <div class="form__content">
        <h1 class="form__title">What’s your project budget?</h1>

        <h2 class="form__subtitle">
          Please select the project budget range you have in mind.
        </h2>

        <div class="form__items">
          <div class="form__item">
            <input type="radio" name="budget" id="budget1" checked />
            <label for="budget1" class="form__item-label"
              >$5.000 - $10.000</label
            >
          </div>
          <div class="form__item">
            <input type="radio" name="budget" id="budget2" />
            <label for="budget2" class="form__item-label"
              >$10.000 - $20.000</label
            >
          </div>
          <div class="form__item">
            <input type="radio" name="budget" id="budget3" />
            <label for="budget3" class="form__item-label"
              >$20.000 - $50.000</label
            >
          </div>
          <div class="form__item">
            <input type="radio" name="budget" id="budget4" />
            <label for="budget4" class="form__item-label">$50.000 +</label>
          </div>
        </div>
      </div>

      <!-- step 4 -->
      <div class="form__content">
        <img class="image-ok" src="./assets/images/ok.svg" alt="" />

        <h1 class="form__title center">Submit your quote request</h1>

        <h2 class="form__subtitle center">
          Please review all the information you previously typed in the past
          steps, and if all is okay, submit your message to receive a project
          quote in 24 - 48 hours.
        </h2>

        <button class="button button--primary button--submit center">
          Submit
        </button>
      </div>
    </div>
    <div class="buttons">
      <button class="button button--secondary">Previous step</button>
      <button class="button button--primary">Next step</button>
    </div>
  </div>
</template>

<style scoped></style>
