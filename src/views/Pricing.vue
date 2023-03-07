<template>
    <div>
        <main>
            <section class="pricing-hero">
                <h1 class="title">Find the perfect plan for your business.</h1>
                <div class="card-wrapper">
                    <div class="text-container" v-for="plan, key in plans" :key="key" :class="{ bg_blue: plan.bgBlue }">
                        <p class="faint-text">{{ plan.planFor }}</p>
                        <h2>{{ plan.price }} <small class="faint-text" :class="{ month_hide: plan.hideMnth }">/MO</small>
                        </h2>
                        <p class="text">{{ plan.details }}</p>
                        <ul class="hero-list">
                            <li v-for="item, index in plan.features" :key="index">{{ item }}</li>
                        </ul>
                        <Button :text="plan.btnText" :bgColor="'#F6F6F9'" :btnWidth="'100'"></Button>
                    </div>
                </div>
            </section>
            <section class="price-feature">
                <div class="feature-text">
                    <h2 class="title">Packed With Epic Features</h2>
                    <p class="text">So you can focus on your most important work.</p>
                </div>
            </section>
            <section class="price-tools">
                <div class="price-tool-card" v-for="item, key in tools" :key="key">
                    <div class="tool-icon-container"><svg-icon width="3em" height="3em" type="mdi" :path="item.icon"></svg-icon>
                    </div>
                    <p class="caption">{{ item.caption }}</p>
                    <p class="text">{{ item.text }}</p>
                </div>
            </section>
            <section class="price-grow">
                <div class="price-grow-card">
                    <h2 class="title">Grow your startup the right way.</h2>
                    <p class="text">Don't waste another minute.</p>
                    <Button :text="'sign up for free'" :bgColor="'#575BDE'" :textColor="'#fff'"></Button>
                </div>
            </section>
        </main>
        <Footer></Footer>
    </div>
</template>

<script>
import Button from '../components/Button.vue';
import Footer from '../components/Footer.vue';
import SvgIcon from '@jamescoyle/vue-icon'
import { mdiFormatLineStyle, mdiFormatTextbox, mdiCheckBold, mdiWifiCheck, mdiCodeTags, mdiCog, mdiViewDashboard, mdiBookOpen } from '@mdi/js'


export default {
    components: { Button, Footer, SvgIcon },
    data() {
        return {
            plans: [
                {
                    planFor: 'Free forever',
                    price: 'Free',
                    details: 'Ut enim ad minima veniam, quis nostrum exercitationem.',
                    features: ['At vero eos et accusamus', 'Odio dignissimos ducimus', 'Blanditiis praesentium'],
                    btnText: 'Sign Up For Free',
                    bgBlue: false,
                    hideMnth: true
                },
                {
                    planFor: 'For Teams',
                    price: '$20',
                    details: 'Nemo enim ipsam voluptatem quia voluptas sit.',
                    features: ['At vero eos et accusamus', 'Odio dignissimos ducimus', 'Blanditiis praesentium'],
                    btnText: 'Start 14-Day Trial',
                    bgBlue: false,
                    hideMnth: false
                },
                {
                    planFor: 'For Enterprises',
                    price: '$140',
                    details: 'Sunt in culpa qui officia deserunt mollit anim id est laborum.',
                    features: ['At vero eos et accusamus', 'Odio dignissimos ducimus', 'Blanditiis praesentium'],
                    btnText: 'Start 14-Day Trial',
                    bgBlue: true,
                    hideMnth: false
                },
            ],

            tools: [
                { icon: mdiFormatTextbox, caption: 'Minimal Design', text: 'Sed ut perspiciatis unde omnis iste natus.' },
                { icon: mdiWifiCheck, caption: 'Rocket Fast', text: 'Sed ut perspiciatis unde omnis iste natus.' },
                { icon: mdiFormatLineStyle, caption: 'Framework', text: 'Sed ut perspiciatis unde omnis iste natus.' },
                { icon: mdiBookOpen, caption: 'Style Guide', text: 'Sed ut perspiciatis unde omnis iste natus.' },
                { icon: mdiCodeTags, caption: 'CSS + SASS', text: 'Sed ut perspiciatis unde omnis iste natus.' },
                { icon: mdiCog, caption: 'Customizable', text: 'Sed ut perspiciatis unde omnis iste natus.' },
                { icon: mdiViewDashboard, caption: 'Modular Design', text: 'Sed ut perspiciatis unde omnis iste natus.' },
                { icon: mdiCheckBold, caption: 'HTML5 Valid', text: 'Sed ut perspiciatis unde omnis iste natus.' }
            ]
        }
    }
}
</script>

<style scoped>
section {
    padding: 50px 5%;
}
.title {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 22px;
    line-height: 55px;
    text-align: center;
}

.text {
    line-height: 30px;
    opacity: 0.9;
    font-size: 1.2rem;
}

.pricing-hero {
    padding: 130px 5% 40px;
}

.card-wrapper {
    margin-top: 40px;
}

.text-container {
    padding: 25px;
    background-color: #fff;
    box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.062), -1px -1px 3px rgba(0, 0, 0, 0.103);
    border-radius: 7px;
    margin-bottom: 30px;
    line-height: 25px;
}


.text-container .faint-text {
    opacity: 0.5;
}

small.faint-text {
    font-size: 0.8rem;
    margin-left: 3px;
}

small.faint-text.month_hide {
    display: none;
}

.text-container h2 {
    font-size: 2.8rem;
    margin: 30px 0 20px;
    font-weight: 500;
}


.text-container ul {
    margin: 20px 20px 30px;
}

.text-container.bg_blue {
    background-color: #1D1A3D;
    color: #fff;
}

.text-container.bg_blue button {
    background-color: #575BDE !important;
    color: #fff;
}

.text-container.bg_blue p.faint-text {
    opacity: 0.9;
}

.price-feature {
    text-align: center;
}

.feature-text {
    color: #fff;
    padding: 180px 20px;
    border-radius: 5px;
    background: url('../assets/images/epic-img.jpg');
    background-size: cover;
    background-color: rgba(0, 0, 0, 0.507);
    background-blend-mode: soft-light;
}


.price-tools {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.tool-icon-container {
    width: 100px;
    height: 100px;
    background-color: #F1F1F3;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    margin: 0 auto 20px;
  }

.price-tools .price-tool-card {
    width: 43%;
    text-align: center;
    margin-bottom: 40px;
}

.price-tools .caption {
    font-weight: 600;
    margin-bottom: 10px;
}

.price-tools .text {
    font-size: 1.1rem;
    opacity: 0.7;
}

.price-grow .price-grow-card {
    width: 80%;
    text-align: center;
    margin: auto;
}

.price-grow-card .text {
    margin: 20px 0;
}

@media screen and (min-width: 768px) {
    .card-wrapper {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }

    .text-container {
        width: 48%;
    }

    .text-container:last-child {
        width: 100%;
    }

    .price-tools .price-tool-card {
        width: 49%;
    }
}

@media screen and (min-width: 1024px) {
    .title {
        font-size: 3rem;
    }

    .pricing-hero .title {
        padding: 60px 0;
    }

    .text-container,
    .text-container:last-child {
        width: 30%;
    }

    .price-tools .price-tool-card {
        width: 22%;
    }
}
</style>