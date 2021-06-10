<template>
  <div>
    <nav
      class="navbar fixed-top navbar-expand-lg navbar-dark customNavbar scrolledToTop"
    >
      <div class="container">
        <a class="navbar-brand" href="#">kactic.</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#main"
                >Home</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" aria-current="page" href="#subs"
                >Subscriptions</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" aria-current="page" href="#reviews"
                >Reviews</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" aria-current="page" href="#contact"
                >Contact</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
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
.customNavbar {
  background: rgb(0, 0, 0);
  height: 65px;
  background: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0.18) 0%,
    rgba(0, 0, 0, 0) 100%
  );
  transition: 0.5s;
}

.navbar-brand {
  transition: 0.3s;
}
.scrolledToTop {
  height: 70px;
  font-size: 1.1em;
}
</style>
