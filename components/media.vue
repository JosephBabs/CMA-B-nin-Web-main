<template>
    <div class="col-xl-4">
          <!-- <div class="why-choose__right">
            <div class="why-choose__urgent">
              <h3 class="why-choose__urgent-title">
                Raise Fund for Save Animals
              </h3>
              <p class="why-choose__urgent-text">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit sed do
                eiusmod tempor incididunt.
              </p>
              <div class="why-choose__progress">
                <div class="bar">
                  <div
                    v-observe-visibility="onVisibilityChange"
                    class="bar-inner count-bar counted"
                    :data-percent="`${getAmountPercent(30000, 25270)}%`"
                    :style="`${
                      startBar
                        ? `width: ${getAmountPercent(30000, 25270)}%`
                        : ``
                    }`"
                  >
                    <div
                      class="count-text"
                      v-observe-visibility="onVisibilityCountChange"
                    >
                      <countTo
                        :startVal="0"
                        :endVal="
                          startCounter ? getAmountPercent(30000, 25270) : 0
                        "
                        :duration="3000"
                      ></countTo
                      >%
                    </div>
                  </div>
                </div>
                <div class="why-choose__goals">
                  <p><span>$25,270</span> Raised</p>
                  <p><span>$30,000</span> Goal</p>
                </div>
              </div>
              <a href="#" class="why-choose__right-btn"
                ><i class="fa fa-heart"></i>Donate</a
              >
              <div class="why-choose__right-category">
                <span>Medical</span>
              </div>
            </div>
          </div> -->
        </div>
</template>