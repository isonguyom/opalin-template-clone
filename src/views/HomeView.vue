<script>
import Button from '../components/Button.vue';
import Footer from '../components/Footer.vue';
import SvgIcon from '@jamescoyle/vue-icon'
import { mdiFormatLineStyle, mdiFormatTextbox, mdiCheckBold, mdiWifiCheck } from '@mdi/js'

export default {
  components: {
    Button,
    Footer,
    SvgIcon
  },

  data() {
    return {
      timeline: [
        { caption: 'Research', text: 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.' },
        { caption: 'Ideation', text: 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur mollit.' },
        { caption: 'Development', text: 'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.' },
        { caption: 'Launch', text: 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.' },
      ],
      steps: [
        { id: 1, caption: 'Download', text: 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.', bgBlue: false },
        { id: 2, caption: 'Customize', text: 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur mollit.', bgBlue: false },
        { id: 3, caption: 'Upload', text: 'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.', bgBlue: false },
        { id: 4, caption: 'Done!', text: 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.', bgBlue: true }
      ],

      tools: [
        { icon: mdiFormatTextbox, caption: 'Minimal Design' },
        { icon: mdiWifiCheck, caption: 'Rocket Fast' },
        { icon: mdiFormatLineStyle, caption: 'Framework' },
        { icon: mdiCheckBold, caption: 'HTML5 Valid' }
      ],

      footerLinks: [
        {
          title: 'Info', links: [
            { href: '#', text: 'Getting Started' },
            { href: '#', text: 'Resources' },
            { href: '#', text: 'Design' },
            { href: '#', text: 'Tutorials' },
            { href: '#', text: 'Pricing' },
          ]
        },
        {
          title: 'Support', links: [
            { href: '#', text: 'Documentation' },
            { href: '#', text: 'Requirements' },
            { href: '#', text: 'License' },
            { href: '#', text: 'Updates' },
            { href: '#', text: 'Contact' },
          ]
        },
        {
          title: 'Contact', links: [
            { href: '#', text: 'Twitter' },
            { href: '#', text: 'Facebook' },
            { href: '#', text: 'Instagram' },
            { href: '#', text: 'Medium' },
          ]
        },
      ]
    }
  }
}
</script>

<template>
  <main>
    <div class="hero-container">
      <section class="home-hero hero1">
        <div>
          <h1 class="title title1">Opalin HTML Template</h1>
          <p class="text">A minimal and responsive HTML5 landing page built on lightweight, clean and customizable code.
          </p>
          <Button :text="'get started'" :bgColor="'#575BDE'" :textColor="'#fff'"></Button>
        </div>
        <div>
          <img class="hero-img" src="../assets/images/hero-illustration.png" alt="">
        </div>
      </section>
      <section class="home-hero hero2">
        <div>
          <h2 class="title">Custom Framework</h2>
          <p class="text">Everything is neatly organized in Sass and has been heavily focused on performances.</p>
        </div>
        <div>
          <img class="hero-img" src="../assets/images/editor.png" alt="">
        </div>
      </section>
      <section class="home-hero hero3">
        <div>
          <h2 class="title">Designed In Sketch</h2>
          <p class="text">100% of this HTML template, including all modules and components have been designed in Sketch.
          </p>
        </div>
        <div>
          <img class="hero-img" src="../assets/images/sketch.png" alt="">
        </div>
      </section>
    </div>
    <section class="home-product">
      <h1 class="title title1">Present Your Product</h1>
      <p class="text">
        Opalin helps you present your business in a wide variety of ways. Display full-width images, divide
        content in a
        single or multiple columns, anything to make your product or service stand out!
      </p>
      <img class="hero-img" src="../assets/images/opalin-dashboard.png" alt="">
    </section>
    <section class="home-customer">
      <h1 class="title">Over 20,000 Paying Customers</h1>
      <p class="text">Thousands of the most successful companies rely on our service.</p>
      <div class="customer-logo-wrapper">
        <img src="../assets/images/trusted-company-dark.png" alt="">
        <img src="../assets/images/trusted-company-dark.png" alt="">
        <img src="../assets/images/trusted-company-dark.png" alt="">
        <img src="../assets/images/trusted-company-dark.png" alt="">
      </div>
      <img class="customers-img" src="../assets/images/customers.jpg" alt="">
    </section>
    <section class="home-timeline">
      <h1 class="title title1">Timeline</h1>
      <p class="text">The best stories are told from start to finish, that's why we keep track of history.</p>
      <ul class="timeline-wrapper">
        <li class="timeline-item" v-for="item, key in timeline" :key="key">
          <p class="caption">{{ item.caption }}</p>
          <p>{{ item.text }}</p>
        </li>
      </ul>
    </section>
    <section class="home-quote">
      <div class="home-quote-text">
        <p>Danielle Mayer, business owner, says:</p>
        <h3>
          "Support is fantastic. Nothing but great results!"
        </h3>
      </div>
      <div class="home-quote-img">
      </div>
    </section>
    <section class="home-setup">
      <h1 class="title title1">5-Minute Setup</h1>
      <p class="text">At vero eos et accusamus et iusto odio dignissimos ducimus.</p>
      <div class="setup-steps-wrapper">
        <div class="setup-steps" v-for="item, key in steps" :key="key" :class="{ bg_blue: item.bgBlue }">
          <p class="step-label">Step {{ item.id }}</p>
          <p class="step-caption">{{ item.caption }}</p>
          <p class="step-text">{{ item.text }}
          </p>
        </div>
      </div>
      <p class="demo-text">
        If you need any help, make sure to
        <a class="demo-link" href="">book a demo.</a>
      </p>
    </section>
    <div class="bottom-container">
      <section class="home-grow">
        <h1 class="title">Grow your startup the right way.</h1>
        <p class="text">Our tools are packed with epic features. So you can focus on your most important work.</p>
        <div class="home-tool-wrapper">
          <div class="home-tool" v-for="tool, key in tools" :key="key">
            <div class="tool-icon-container"><svg-icon width="3em" height="3em" type="mdi" :path="tool.icon"></svg-icon>
            </div>
            <p class="tool-caption">{{ tool.caption }}</p>
          </div>
        </div>
        <div class="home-ready">
          <div class="ready-text">
            <h3 class="title">Ready to get started?</h3>
            <p class="text">Start your free 15-day trial today.</p>
          </div>
          <div class="ready-btn-wrapper">
            <Button :text="'create an account'" :bgColor="'#575BDE'" :textColor="'#fff'" :btnWidth="'100'"></Button>
          </div>
        </div>
      </section>
      <Footer :is-white="true"></Footer>
    </div>
  </main>
</template>


<style scoped>
section {
  padding: 30px 5%;
}

.title {
  font-size: 1.7rem;
  font-weight: 600;
  text-transform: capitalize;
  margin-bottom: 15px;
  text-align: center;
  line-height: 50px;
}

.title1 {
  font-size: 2.6rem;
  line-height: 50px;
  margin-bottom: 18px;
}

.text {
  font-size: 1.2rem;
  line-height: 25px;
  margin-bottom: 20px;
  text-align: center;
}

.hero-container {
  background-color: #0E0C1C;
  padding-bottom: 30px;
  color: #fff;
  text-align: center;
  line-height: 33px;
  background: url('../assets/images/hero-bg.svg');
  background-size: cover;
}

.home-hero {
  padding: 25px 5%;
}

.hero1 {
  padding-top: 140px;
}

.hero1 .text {
  font-size: 1.5rem;
  margin-bottom: 30px;
}

.hero-img {
  display: block;
  margin-top: 45px;
}

.home-product {
  text-align: center;
  padding: 50px 5% 50px;
}

.home-product .hero-img {
  margin: auto;
  top: 20px;
  z-index: 2;
  border-radius: 7px;
}

.home-customer {
  padding: 80px 5% 40px;
  background-color: #0E0C1C;
  color: #fff;
  top: -70px;
}

.customer-logo-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  margin: 50px 0 20px;
}

.customer-logo-wrapper img {
  width: 140px;
  margin-bottom: 35px;
}

.customers-img {
  border-radius: 10px;
}

.home-timeline {
  padding: 0 5%;
}

.timeline-wrapper {
  list-style: none;
}

.timeline-item {
  padding: 10px 20px;
  line-height: 25px;
  border-left: 1px solid rgb(170, 170, 170);
}

li::before {
  content: "•";
  color: #575BDE;
  top: 30px;
  width: 1em;
  font-size: 1.5rem;
  margin-left: -1.14em;
  background-color: #fff;
  padding: 0.1px;
}

.timeline-item .caption {
  font-weight: 600;
  font-size: 1.3rem;
  margin-bottom: 10px;
}

.home-quote {
  text-align: center;
  font-size: 1.2rem;
  padding: 30px 0;
}

.home-quote-text {
  margin: auto;
  padding: 100px 5%;
}

.home-quote h3 {
  font-weight: 600;
  margin-top: 20px;
  font-size: 1.8rem;
}

.home-quote-img {
  background: url('../assets/images/quote-img.jpg');
  width: 100%;
  height: 300px;
  background-size: cover;
}

.home-setup {
  padding-bottom: 50px;
}

.setup-steps-wrapper {
  margin: 60px 0;
}

.setup-steps-wrapper .setup-steps {
  line-height: 25px;
  padding: 20px;
  margin-bottom: 35px;
  border-radius: 10px;
  background-color: #fff;
  box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.062), -1px -1px 3px rgba(0, 0, 0, 0.103);
}


.setup-steps-wrapper .setup-steps.bg_blue {
  background-color: #1D1A3D;
  color: #fff;
}

.setup-steps-wrapper .step-label {
  opacity: 0.7;
}

.setup-steps-wrapper .step-caption {
  font-weight: 600;
  margin: 20px 0;
  font-size: 1.5rem;
}


.demo-text {
  opacity: 0.7;
  text-align: center;
}

.demo-link {
  text-decoration: none;
  color: #575BDE;
}

.demo-link:hover {
  color: #4F4D5D;
}

.bottom-container {
  padding-top: 30px;
  color: white;
  background: rgb(24, 219, 182);
  background: linear-gradient(111deg, rgba(24, 219, 182, 1) 0%, rgba(39, 182, 193, 1) 52%, rgba(78, 113, 217, 1) 100%);
}

.home-tool-wrapper {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  margin: 50px 0 0;
  text-align: center;
}

.home-tool-wrapper .home-tool {
  width: 48%;
  margin-bottom: 60px;
}

.tool-icon-container {
  width: 100px;
  height: 100px;
  background-color: #ffffff11;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  margin: 0 auto 20px;
}

.tool-icon-container .tool-icon {
  font-size: 2rem;
}

.tool-caption {
  font-weight: 600;

}

.home-grow {
  padding-bottom: 0;
}

.home-ready {
  background-color: #1D1A3D;
  color: #fff;
  text-align: center;
  padding: 30px 30px;
  border-radius: 8px;
}

.home-ready .text {
  margin-bottom: 20px;
}

@media screen and (min-width: 768px) {
  .title {
    font-size: 2.3rem;
  }

  .title1 {
    font-size: 3rem;
    line-height: 70px;
  }

  .text {
    line-height: 35px;
    margin-bottom: 0;
    width: 80%;
  }

  .home-hero {
    display: flex;
    text-align: left;
    justify-content: space-between;
    align-items: center;
    padding-top: 100px;
  }

  .home-hero img {
    border-radius: 7px;
  }

  .home-hero>div {
    width: 48%;
  }

  .home-hero.hero1 {
    min-height: 100vh;
    font-size: 3.8rem;
  }

  .home-hero.hero1 .title1 {
    text-align: left;
  }

  .home-hero .text {
    text-align: left;
    font-size: 1.5rem;
  }

  .hero2 .title {
    text-align: left;
  }

  .hero3 {
    flex-direction: row-reverse;
  }

  .hero3 .title {
    text-align: left;
  }

  .home-product .text,
  .home-customer .text,
  .home-timeline .text,
  .home-setup .text {
    margin: auto;
  }

  .customer-logo-wrapper {
    width: 80%;
    margin: 50px auto 20px
  }

  .customer-logo-wrapper img {
    width: 190px;
    margin-bottom: 50px;
  }

  .home-quote {
    display: flex;
    align-items: center;
    padding: 50px 0;
  }

  .home-quote-img {
    height: 500px;
  }


  .setup-steps-wrapper {
    display: flex;
    justify-content: space-between;
    align-content: space-between;
    flex-wrap: wrap;
  }

  .setup-steps-wrapper .setup-steps {
    width: 48%;
    margin-bottom: 20px;
  }

  .home-grow .text {
    margin: auto;
  }

  .home-ready {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .home-ready .ready-text {
    text-align: left;
    width: 50%;
  }

  .home-ready .title {
    text-align: left;
    line-height: 45px;
    margin-bottom: 5px;
  }

  .home-ready .text {
    margin-left: 0;
    margin-bottom: 0;
    text-align: left;
    line-height: 25px;

  }

  .ready-btn-wrapper {
    width: 48%;
  }

  .home-about .about-text {
    width: 90%;
    margin: auto;
  }

}

@media screen and (min-width: 1024px) {
  .home-product .text {
    width: 60%;
  }


  .home-product .hero-img {
    top: 20px;
  }

  .home-customer {
    padding: 170px 5% 40px;
    top: -100px;
  }


  .customer-logo-wrapper img {
    width: 170px;
    margin-bottom: 50px;
  }

  .home-quote-text {
    width: 43%;
  }

  .home-quote-img {
    height: 500px;
    width: 50%;
  }


  .timeline-wrapper {
    display: flex;
    justify-content: space-between;
    margin-top: 70px;
  }

  .timeline-item {
    border: 0;
    border-top: 1px solid rgb(170, 170, 170);
  }

  li::before {
    top: -25px;
    left: 20px;

  }

  .setup-steps-wrapper .setup-steps {
    width: 22%;
    font-size: 1.2rem;
    line-height: 30px;
  }

  .home-tool-wrapper .home-tool {
    width: 23%;
  }

  .ready-btn-wrapper {
    width: 33%;
  }
}
</style>
