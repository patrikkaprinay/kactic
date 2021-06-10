<template>
  <div
    id="footer"
    class="d-flex justify-content-center align-items-center flex-column"
  >
    <div
      class="row d-flex justify-content-center align-items-center w-50 h-100 m-0"
    >
      <div
        class="col-md-12 col-lg d-flex justify-content-center align-items-center"
      >
        <img src="img/logo2.png" class="logo" alt="" />
        <p class="ms-3 m-0 footerLogo">kactic.</p>
      </div>
      <div
        class="col-md-12 col-lg d-flex justify-content-center align-items-center flex-column"
        style="border-left: 2px solid #ffffff21"
      >
        <p class="m-0 mb-3" style="font-size: 2em">Documents</p>
        <ul class="footerList">
          <li><a href="#">FAQ</a></li>
          <li><a href="#">Terms of service</a></li>
          <li><a href="#">Terms & Conditions</a></li>
        </ul>
      </div>
      <div class="col-md-12 col-lg d-flex align-items-center flex-column">
        <p class="m-0 mb-3" style="font-size: 2em">Socials</p>
        <ul class="footerList socialList">
          <!-- <li><a href="#">Instagram</a></li>
          <li><a href="#">Facebook</a></li>
          <li><a href="#">YouTube</a></li> -->
          <li>
            <a href="#"
              ><img
                src="img/socials/instagram.png"
                style="width: 25px; filter: invert(1)"
                alt=""
            /></a>
          </li>
          <li>
            <a href="#"
              ><img
                src="img/socials/facebook.png"
                style="width: 25px; filter: invert(1)"
                alt=""
            /></a>
          </li>
          <li>
            <a href="#"
              ><img
                src="img/socials/twitter.png"
                style="width: 25px; filter: invert(1)"
                alt=""
            /></a>
          </li>
        </ul>
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
#footer {
  min-height: 13em;
  padding: 20px 0;
  background: rgb(206, 120, 23);
  color: rgb(246, 246, 246);
}

.socialList {
  min-height: 70px;
}

.socialList li {
  display: inline-block;
}

.socialList li:not(:last-child) {
  margin-right: 15px;
}

.footerList {
  list-style: none;
  margin: 0;
  padding: 0;
}

.footerList > li > a {
  text-decoration: none;
  color: rgb(246, 246, 246);
}

.footerLogo {
  font-size: 3em;
  color: white;
}

.logo {
  width: 50px;
}
</style>
