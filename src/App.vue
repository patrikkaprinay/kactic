<template>
  <Navbar />
  <Welcome />
  <Subscriptions :subscriptions="subscriptions" />
  <Reviews :reviews="reviews" />
  <Contact />
  <Footer />
</template>

<script>
import Welcome from '@/components/Welcome.vue';
import Navbar from '@/components/Navbar.vue';
import Subscriptions from '@/components/Subscriptions.vue';
import Reviews from '@/components/Reviews.vue';
import Footer from '@/components/Footer.vue';
import Contact from '@/components/Contact.vue';

import { reactive, toRefs } from 'vue';
import { subscriptions, reviews } from '@/data.js';

export default {
  created() {
    window.addEventListener('scroll', this.handleScroll);
  },
  unmounted() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      //Elements we want to animate
      let animate = document.querySelectorAll('.slideupMy');

      //Our navbar
      let navbar = document.querySelector('.customNavbar');

      //Getting elements on which we have to darken the navbar
      let whiteParts = document.querySelectorAll('.whitePart');

      for (let i = 0; i < animate.length; i++) {
        if (animate[i].offsetTop - 650 <= window.scrollY) {
          animate[i].classList.add('slideupMyAnimation');
        }
      }

      if (window.scrollY <= 10) {
        if (!navbar.classList.contains('scrolledToTop'))
          navbar.classList.add('scrolledToTop');
      }
      if (window.scrollY > 10) {
        if (navbar.classList.contains('scrolledToTop'))
          navbar.classList.remove('scrolledToTop');
      }

      for (let i = 0; i < whiteParts.length; i++) {
        if (whiteParts[i].offsetTop - 25 <= window.scrollY) {
          navbar.classList.add('navbar-light');
          navbar.classList.remove('navbar-dark');
        }
        if (whiteParts[i].offsetTop - 25 > window.scrollY) {
          navbar.classList.add('navbar-dark');
          navbar.classList.remove('navbar-light');
        }
      }

      let pixelsBefore = 280;
      let navLinks = document.querySelectorAll('.nav-link');
      let main = document.querySelector('#main');
      let subs = document.querySelector('#subs');
      let reviews = document.querySelector('#reviews');
      let contact = document.querySelector('#contact');
      let idArray = [main, subs, reviews, contact];
      idArray.forEach((el1) => {
        if (window.scrollY > el1.offsetTop + el1.offsetHeight - pixelsBefore) {
          navLinks.forEach((elNav) => {
            if (elNav.href.includes(el1.id)) {
              elNav.classList.remove('active');
            }
          });
        } else if (window.scrollY >= el1.offsetTop - pixelsBefore) {
          navLinks.forEach((elNav) => {
            if (elNav.href.includes(el1.id)) {
              elNav.classList.add('active');
            }
          });
        } else if (window.scrollY < el1.offsetTop - pixelsBefore) {
          navLinks.forEach((elNav) => {
            if (elNav.href.includes(el1.id)) {
              elNav.classList.remove('active');
            }
          });
        }
      });
    },
  },
  name: 'App',
  components: {
    Welcome,
    Navbar,
    Subscriptions,
    Reviews,
    Footer,
    Contact,
  },
  mounted() {
    document.title = 'kactic. — The most lightweight programming language';
  },
  setup() {
    const state = reactive({
      subscriptions: subscriptions,
    });
    return {
      ...toRefs(state),
      reviews,
    };
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  background: #fdfdfd;
}

body::-webkit-scrollbar {
  width: 8px; /* width of the entire scrollbar */
}

body::-webkit-scrollbar-track {
  background: rgb(214, 214, 214); /* color of the tracking area */
}

body::-webkit-scrollbar-thumb {
  background-color: rgb(228, 131, 20); /* color of the scroll thumb */
  border-radius: 20px; /* roundness of the scroll thumb */
  /* border: 3px solid orange; */ /* creates padding around scroll thumb */
}

body {
  overflow-x: hidden;
}

.slideupMy {
  opacity: 0;
}

.slideupMyAnimation {
  position: relative;
  animation: 0.6s ease-in slideUp forwards;
}

::-moz-selection {
  background: rgb(180, 105, 20);
  color: white;
}
::selection {
  background: rgb(219, 133, 35);
  color: white;
}

@keyframes slideUp {
  0% {
    bottom: -30px;
  }
  100% {
    bottom: 0;
    opacity: 100%;
  }
}
</style>
