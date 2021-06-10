<template>
  <div
    id="subs"
    class="d-flex justify-content-center align-items-center flex-column whitePart"
  >
    <h2 class="slideupMy" style="font-size: 3em; margin-bottom: 40px;">
      Subscriptions
    </h2>
    <div
      class="container d-flex justify-content-center align-items-center w-75"
    >
      <div
        class="row d-flex justify-content-center align-items-center w-100 slideupMy"
      >
        <div
          class="col-lg-12 col-xl d-flex justify-content-end align-items-center flex-column oneSubs mb-lg-5"
          v-for="subscription in subscriptions"
          :key="subscription.id"
        >
          <!-- <div v-if="subscription.popular" class="bestdeal">Most popular</div> -->
          <div
            class="d-flex align-items-center flex-column innerSubs"
            :class="subscription.popular ? 'mostPopular' : ''"
          >
            <div class="d-flex align-items-center flex-column subsContent">
              <p class="subsName">{{ subscription.name }}</p>
              <div
                class="d-flex justify-content-center align-items-center flex-column w-100"
                style="height: 65%;"
              >
                <ul style="width: 80%">
                  <li v-for="feature in subscription.features" :key="feature">
                    {{ feature }}
                  </li>
                </ul>
              </div>
              <div
                class="d-flex justify-content-center align-items-center flex-column bottomSubs"
              >
                <p class="subsPrice">${{ subscription.price }}/month</p>
                <button
                  class="btn btn-success rounded-pill px-3 py-2 selectPlan"
                  style="font-size: 1.05em"
                >
                  Select plan
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <p
      class="m-0 mt-1 text-center"
      style="font-size: .7em; color: grey; width: 300px"
    >
      Cancel anytime in Settings, at least one day before the renewal of the
      subscription.
    </p>
  </div>
</template>

<script>
export default {
  props: {
    subscriptions: {
      type: Array,
    },
  },
  setup() {
    return {};
  },
};
</script>

<style scoped>
#subs {
  padding: 60px 0;
}

li {
  font-size: 1.2em;
}

.mostPopular {
  /* border: 8px solid rgb(230, 0, 0); */
  position: relative;
}

.mostPopular::after {
  content: 'Most Popular';
  position: absolute;
  top: -34px;
  right: 30px;
  padding: 5px 9px;
  background: rgb(230, 0, 0);
  color: white;
  border-top-right-radius: 10px;
  border-top-left-radius: 10px;
  z-index: 8;
  font-weight: bold;
}

.selectPlan {
  background: rgb(236, 147, 46);
  border: none;
  transition-duration: 0.2s;
}
.selectPlan:hover {
  background: rgb(223, 139, 43);
}

.selectPlan:focus {
  box-shadow: 0 0 0 0.25rem rgb(236 147 46 / 50%);
  box-shadow: 0 0 0 0.25rem rgb(223 139 43 / 25%);
}

.oneSubs {
  background: #ebebeb;
  border-radius: 12px;
  padding: 20px;
  margin: 10px;
  height: 500px;
  /* max-width: 330px; */
  position: relative;
  /* overflow: hidden; */
  box-shadow: 3px 3px 3px rgba(0, 0, 0, 0.13);
}

/* .bestdeal {
  position: absolute;
  top: 1.4em;
  left: -4.3em;
  font-size: 1.3em;
  color: white;
  background: rgb(230, 0, 0);
  padding: 10px 90px;
  z-index: 6;
  transform: rotate(-45deg);
} */

.subsName {
  font-size: 2em;
  font-weight: 500;
}

.subsContent {
  position: relative;
  height: 100%;
  width: 100%;
  padding: 15px 0;
}

.bottomSubs {
  position: absolute;
  bottom: 20px;
  padding: 0 10px;
}

.innerSubs {
  position: relative;
  /* min-height: 87%; */
  height: 100%;
  width: 100%;
  background: white;
  border-radius: 12px;
  z-index: 2;
}

.subsPrice {
  font-size: 1.5em;
  margin-bottom: 5px;
}

.subsIcon {
  position: absolute;
  top: -55px;
  background: white;
  padding: 20px 35px;
  padding-bottom: 50px;
  border-radius: 50%;
  z-index: -3;
}

@media (max-width: 1999px) {
  .oneSubs {
    max-width: 415px;
  }
}
</style>
