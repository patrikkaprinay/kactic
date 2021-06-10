<template>
  <div
    id="reviews"
    class="d-flex justify-content-center align-items-center flex-column"
  >
    <h2
      class="slideupMy"
      style="font-size: 3em; margin-bottom: 20px; color: white;"
    >
      Reviews
    </h2>
    <div class="reviews d-flex justify-content-center align-items-center">
      <div
        id="carouselExampleControls"
        class="carousel slide w-100 h-100 slideupMy"
        data-bs-ride="carousel"
      >
        <div class="carousel-inner w-75 h-100 mx-auto">
          <div
            class="carousel-item h-100 py-5"
            v-for="review in reviews"
            :key="review.id"
            :class="review.id == 1 ? 'active' : ''"
          >
            <div
              class="oneReview d-flex justify-content-center align-items-center flex-column p-3 mx-auto"
            >
              <div
                class="reviewTop d-flex justify-content-center align-items-center flex-column"
              >
                <img :src="'img/' + review.img" class="reviewImage" alt="" />
                <div
                  class="ms-2 d-flex justify-content-center align-items-center flex-column"
                >
                  <p class="m-0 fw-bold">{{ review.name }}</p>
                  <p class="m-0 company-pos" v-if="review.company">
                    {{ review.company }}
                  </p>
                  <div>
                    <i
                      class="bi bi-star-fill"
                      v-for="stars in review.stars"
                      :key="stars"
                    ></i>
                  </div>
                </div>
                <div>
                  <p class="m-0 mt-2">{{ review.text }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <button
          class="carousel-control-prev d-none d-sm-inline"
          type="button"
          data-bs-target="#carouselExampleControls"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next d-none d-sm-inline"
          type="button"
          data-bs-target="#carouselExampleControls"
          data-bs-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    reviews: {
      type: Object,
    },
  },
  setup() {
    return {};
  },
};
</script>

<style scoped>
#reviews {
  min-height: 60vh;
  background: rgb(236, 147, 46);
}

.company-pos {
  font-size: 0.8em;
  color: rgb(206, 120, 23);
}

.reviewImage {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  object-fit: cover;
  transition-duration: 0.4s;
}

.reviewImage:hover {
  filter: invert(71%) sepia(62%) saturate(1900%) hue-rotate(338deg)
    brightness(96%) contrast(93%);
}

.reviews {
  width: 65vw;
  height: 40vh;
  min-width: 500px;
}

.oneReview {
  background: white;
  border-radius: 5px;
  box-shadow: 3px 3px 5px rgba(0, 0, 0, 0.116);
  height: 100%;
  width: 85%;
}

@media (max-width: 730px) {
  .reviews {
    width: 90vw;
  }
}
</style>
