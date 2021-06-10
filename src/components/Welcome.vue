<template>
  <div
    id="main"
    class="main d-flex justify-content-center align-items-center flex-column"
  >
    <div class="row w-100">
      <div
        class="col-12 col-md-7 d-flex justify-content-center align-items-center flex-column"
      >
        <div
          class="d-flex justify-content-center align-items-center flex-column w-50"
        >
          <h2 class="mainText">kactic.</h2>
          <p class="mainDescr">
            kactic is an <b>open-source</b>, widely supported mobile-first
            language that is very adaptive and can be used almost on any device.
          </p>
          <a
            href="#subs"
            class="btn btn-dark rounded-pill px-3 py-2 mt-3"
            style="font-size: 1.2em"
            >Learn more</a
          >
        </div>
      </div>
      <div
        class="col-12 col-md-3 d-none d-sm-flex justify-content-center align-items-center flex-column"
      >
        <img
          src="img/character2.png"
          alt=""
          style="width: 270px; -webkit-transform: scaleX(-1);
                    transform: scaleX(-1);"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    return {};
  },
};
</script>

<style scoped>
.main {
  padding-top: 40px;
  width: 100vw;
  height: 100vh;
  background: rgb(236, 147, 46);
}

.mainText {
  font-size: 6em;
  color: white;
  position: relative;
  overflow: hidden;
}

.mainText::before {
  content: '';
  position: absolute;
  inset: 0;
  background: rgb(236, 147, 46);
  width: 100%;
  height: 100%;
  animation: 0.6s ease 0.8s typewriter forwards;
}

@media (max-width: 400px) {
  .mainText::before {
    content: initial;
  }
}

.mainDescr {
  text-align: center;
  color: white;
}

@keyframes typewriter {
  to {
    left: 100%;
  }
}
</style>
