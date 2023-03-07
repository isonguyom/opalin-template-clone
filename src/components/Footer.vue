<template>
    <footer class="Footer" :class="{ footer_white: isWhite }">
        <section class="footer-wrapper">
            <div class="footer-about">
                <p class="footer-caption">Opalin ®</p>
                <p class="footer-text">We're a completely remote company, working across twenty countries with over 20,000
                    customers.</p>
            </div>
            <div class="footer-links-flex">
                <div class="footer-links-card" v-for="link, key in footerLinks" :key="key">
                    <p class="footer-caption">{{ link.title }}</p>
                    <a class="footer-link" v-for="item, index in link.links" :href="item.href">{{ item.text }}</a>
                </div>
            </div>
        </section>
        <section class="footer-copyright">HTML Template by UI/UX Assets - © 2018, all rights reserved.</section>
    </footer>
</template>

<script>
export default {
    props: ['isWhite'],
    data() {
        return {
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

<style scoped>
.Footer {
    background: transparent;
}

.footer-wrapper {
    text-align: center;
    padding: 50px 5% 20px;
}

.footer-wrapper .footer-caption {
    font-weight: 700;
    margin-bottom: 10px;
    text-transform: capitalize;
}

.footer-text,
.footer-link {
    opacity: 0.9;
    line-height: 25px;
}

.footer-wrapper .footer-about {
    width: 90%;
    margin: 0 auto;
}

.footer-links-flex {
    margin-top: 50px;
}

.footer-links-card {
    margin-bottom: 60px;
}

.footer-links-card:last-child {
    margin-bottom: 0;
}

.footer-link {
    text-transform: capitalize;
    text-decoration: none;
    display: block;
    width: fit-content;
    color: #110F24;
    margin: auto;
}

.footer-link:hover {
    opacity: 1;
    color: #575BDE;
}

.footer-copyright {
    text-align: center;
    opacity: 0.5;
    font-size: 0.8rem;
    padding: 50px 5%;
}

.Footer.footer_white .footer-wrapper,
.Footer.footer_white .footer-wrapper .footer-link {
    color: #fff;
}

@media screen and (min-width: 992px) {
    .footer-wrapper {
        display: flex;
        justify-content: space-between;
        padding-top: 100px;
    }

    .footer-wrapper .footer-about {
        width: 38%;
        text-align: left;
        margin-left: 0;
    }

    .footer-wrapper .footer-links-flex {
        width: 58%;
        display: flex;
        justify-content: space-between;
        text-align: left;
        margin-top: 0;
    }

    .footer-link {
        margin-left: 0;
    }

    .footer-wrapper .footer-links-flex .footer-links-card {
        width: 33%;
    }
}
</style>