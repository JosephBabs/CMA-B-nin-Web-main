<template>
  <!--Why Choose Start-->
  <section class="why-choose" id="mission">
    <div
      class="why-choose-bg"
      :style="`background-image: url(${require(`~/assets/images/backgrounds/why-choose-bg.jpg`)})`"
    ></div>
    <div class="container">
      <div class="row">
        <div class="col-xl-8">
          <div class="why-choose__left">
            <div class="section-title text-left">
              <span class="section-title__tagline">LA CMA-BENIN</span>
              <h2 class="section-title__title">
                NOTRE <br />
                MISSION
              </h2>
            </div>
            <div class="" >
              <div class="">
                <p class="about-page__right-text">
                  La CMA-Bénin a pour mission la représentation, la promotion  du 
              secteur et la protection des intérêts des artisans beninois et des entreprises artisanales auprès 
              des collectivités locales, des instances nationales sous-régionales et internationales.
                </p>
                <h2 class="why-choose__left-signature">...</h2>
              </div>
              <div class="why-choose__left-list-box">
                <ul class="why-choose__left-list list-unstyled">
                  
                </ul>
              </div>
            </div>
          </div>
        </div>
        
      </div>
    </div>
  </section>
  <!--Why Choose End-->
</template>
<script>
import countTo from "vue-count-to";
import { ObserveVisibility } from "vue-observe-visibility";
export default {
  components: { countTo },
  directives: {
    ObserveVisibility,
  },
  data() {
    return {
      startBar: false,
      startCounter: false,
    };
  },
  methods: {
    getAmountPercent: function (goal, raised) {
      return parseInt((parseInt(raised, 10) / parseInt(goal, 10)) * 100, 10);
    },
    onVisibilityChange(isVisible) {
      if (isVisible) {
        this.startBar = true;
      }
    },
    onVisibilityCountChange(isVisible) {
      if (isVisible) {
        this.startCounter = true;
      }
    },
  },
};
</script>
