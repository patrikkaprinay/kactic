<template>
  <div
    id="contact"
    class="d-flex justify-content-center align-items-center flex-column py-5 whitePart"
  >
    <h2 class="slideupMy" style="font-size: 3em; margin-bottom: 40px;">
      Contact us
    </h2>
    <div class="contactusForm slideupMy">
      <div class="mb-3">
        <input
          type="email"
          class="form-control rounded-pill"
          placeholder="Your e-mail"
          style=""
        />
      </div>
      <div class="mb-3">
        <input
          type="text"
          class="form-control rounded-pill"
          placeholder="Title"
          style=""
        />
      </div>
      <div class="mb-3">
        <textarea
          class="form-control"
          name=""
          id=""
          cols="30"
          rows="10"
          placeholder="In my oppinion you could..."
          style="border-radius: 20px; min-height: 250px;"
        ></textarea>
      </div>
      <div class="d-flex justify-content-center align-items-end flex-column">
        <button class="btn btn-secondary rounded-pill px-3 py-2 sendEmail">
          Send
        </button>
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
.contactusForm {
  width: 600px;
}

.contactusForm > div > input:focus,
.contactusForm > div > textarea:focus {
  box-shadow: 0 0 0 0.25rem rgb(236 147 46 / 50%);
  box-shadow: 0 0 0 0.25rem rgb(223 139 43 / 25%);
  border-color: rgb(236, 147, 46);
}

.sendEmail {
  background: rgb(236, 147, 46);
  border: none;
  transition-duration: 0.2s;
}
.sendEmail:hover {
  background: rgb(223, 139, 43);
}

.sendEmail:focus {
  box-shadow: 0 0 0 0.25rem rgb(236 147 46 / 50%);
  box-shadow: 0 0 0 0.25rem rgb(223 139 43 / 25%);
}

@media (max-width: 730px) {
  .contactusForm {
    width: 80%;
  }
}
</style>
