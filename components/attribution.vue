<template>
    <!--Welcome One Start-->
    <section class="welcome-one">
      <div class="container" id="attribution">
        <div class="row">
          <div class="col-xl-6 col-lg-6">
            <div class="welcome-one__left">
              <div class="welcome-one__img-box">
                <img src="~images/resources/welcome-one-img-1.jpg" alt="" />
                <!-- <div class="welcome-one__img-box-2">
                  <img src="~images/resources/welcome-one-img-2.jpg" alt="" />
                </div> -->
                <h2 class="welcome-one__bottom-text"></h2>
                
              </div>
            </div>
          </div>
          <div class="col-xl-6 col-lg-6">
            <div class="welcome-one__right">
              <div class="section-title text-left">
                <span class="section-title__tagline">LA CMA-BENIN</span>
                <h2 class="section-title__title">
                  ATTRIBUTION
                </h2>
              </div>
              <p class="welcome-one__right-text">
                Lorem ipsum dolor sit amet, consectetur notted adipisicing elit
                sed do eiusmod tempor incididunt ut labore et simply free text
                dolore magna aliqua lonm andhn.
              </p>
              <p class="welcome-one__right-text">
                Lorem ipsum dolor sit amet, consectetur notted adipisicing elit
                sed do eiusmod tempor incididunt ut labore et simply free text
                dolore magna aliqua lonm andhn.
              </p>
              <p class="welcome-one__right-text">
                Lorem ipsum dolor sit amet, consectetur notted adipisicing elit
                sed do eiusmod tempor incididunt ut labore et simply free text
                dolore magna aliqua lonm andhn.
              </p>
              <p class="welcome-one__right-text">
                Lorem ipsum dolor sit amet, consectetur notted adipisicing elit
                sed do eiusmod tempor incididunt ut labore et simply free text
                dolore magna aliqua lonm andhn.
              </p>
              <!-- <div class="welcome-one__our-mission-and-story">
                <div class="welcome-one__mission-and-story-single">
                  <h3><i class="fas fa-arrow-circle-right"></i>Our Mission</h3>
                  <p class="welcome-one__our-mission-and-story-text">
                    Lorem ipsum dolor sit amet not is consectetur notted.
                  </p>
                </div>
                <div class="welcome-one__mission-and-story-single">
                  <h3><i class="fas fa-arrow-circle-right"></i>Our Story</h3>
                  <p class="welcome-one__our-mission-and-story-text">
                    Lorem ipsum dolor sit amet not is consectetur notted.
                  </p>
                </div>
              </div> -->
              <!-- <div class="welcome-one__progress">
                <div class="welcome-one__progress-single">
                  <h4 class="welcome-one__progress-title">Charity</h4>
                  
                </div>
                
              </div> -->
              <!-- <nuxt-link to="/about" class="welcome-one__btn thm-btn">
                <i class="fas fa-arrow-circle-right"></i>Learn More
              </nuxt-link> -->
            </div>
          </div>
        </div>
      </div>
    </section>
    <!--Welcome One End-->
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
  