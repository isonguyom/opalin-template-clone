<template>
    <nav :class="{ light_color: color }">
        <div class="logo-container" :class="{ active_menu: menubarIsActive }">
            <router-link :to="{ name: 'home' }" class="nav-logo">
                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="24" height="24"
                    viewBox="0 0 24 24">
                    <path
                        d="M7.335 1.023l2.462.434a1 1 0 0 1 .811 1.159L8.004 17.388a2 2 0 0 1-2.317 1.622l-3.94-.694a1 1 0 0 1-.81-1.159L3.28 3.862a3.5 3.5 0 0 1 4.054-2.839zm7.039 3.272l7.878 1.39a1 1 0 0 1 .812 1.158l-1.997 11.325a5.5 5.5 0 0 1-6.372 4.461l-4.431-.78a1 1 0 0 1-.812-1.16l2.605-14.771a2 2 0 0 1 2.317-1.623z"
                        fill="currentColor"></path>
                </svg> <span>Opalin</span>
            </router-link>
            <div class="menu-toggler" @click="toggleMenubar">
                <svg-icon type="mdi" :path="hamburgerPath" v-if="!menubarIsActive"></svg-icon>
                <svg-icon type="mdi" :path="closePath" v-else></svg-icon>
            </div>
        </div>
        <div class="menu-container" :class="{ active_menu: menubarIsActive }">
            <ul class="main-menu">
                <li><router-link :to="{ name: 'home' }" class="menu-item" @click="toggleMenubar">Home</router-link></li>
                <li><router-link :to="{ name: 'pricing' }" class="menu-item" @click="toggleMenubar">Pricing</router-link>
                </li>
                <li><router-link :to="{ name: 'about' }" class="menu-item" @click="toggleMenubar">About</router-link></li>
            </ul>
            <ul class="sub-menu">
                <li><button @click="$emit('open-login')">log in</button></li>
                <li><button class="menu-btn" @click="$emit('open-signup')">sign up</button></li>
            </ul>
        </div>
    </nav>
</template>

<script>
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiMenu, mdiClose } from '@mdi/js';


export default {
    components: { SvgIcon },
    emits: ['open-login', 'open-signup'],
    props: ['color'],
    data() {
        return {
            menubarIsActive: false,
            hamburgerPath: mdiMenu,
            closePath: mdiClose
        }
    },

    methods: {
        toggleMenubar() {
            this.menubarIsActive = !this.menubarIsActive
        }
    }
}
</script>

<style scoped>
nav {
    padding: 15px 0;
    width: 100%;
    position: absolute;
}

.logo-container {
    padding: 0 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 100;
}

nav .nav-logo {
    font-family: 'PT Serif', serif;
    text-decoration: none;
    font-size: 1.5rem;
    color: #110F24;
}

nav.light_color .logo-container,
nav.light_color .nav-logo {
    color: #fff;
}

nav.light_color .logo-container {
    color: #fff;
}

.nav-logo span {
    font-weight: 600;
}

.menu-toggler {
    cursor: pointer;
    width: fit-content;
}

.menu-container {
    padding: 50px 5%;
    background-color: #05050B;
    position: fixed;
    top: 0;
    width: 100%;
    height: 100vh;
    z-index: 10;
    display: none;
}

.logo-container.active_menu {
    position: fixed;
    width: 100%;
}


.logo-container.active_menu,
.logo-container.active_menu .nav-logo {
    color: #fff;
}

.menu-container.active_menu {
    display: block;
}

nav ul {
    list-style: none;
    text-align: center;
}

nav ul li a {
    text-decoration: none;
    font-weight: 500;
    font-size: 1.4rem;
    color: #fff;
    padding: 20px 0;
    display: block;
    text-transform: capitalize;
}

nav ul li button {
    border: 0;
    cursor: pointer;
    font-weight: 500;
    font-size: 1.4rem;
    color: #fff;
    padding: 20px 0;
    background: transparent;
    text-transform: capitalize;
}

nav ul li button.menu-btn {
    background: rgba(128, 128, 128, 0.171);
    border-radius: 60px;
    padding: 14px 15px;
    width: 100%;
}

nav a:hover {
    opacity: 0.8;
}

nav ul li button:hover {
    opacity: 0.8;
}

.logo-container.active_menu .nav-logo:hover,
.menu-container.active_menu a:hover,
.menu-container.active_menu button:hover {
    color: #fff;
}


@media screen and (min-width: 768px) {
    nav {
        background-color: transparent;
        padding: 20px 0;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: absolute;
    }

    .logo-container {
        padding: 0 3%;
        width: fit-content;
    }

    .menu-toggler {
        display: none;
    }

    .menu-container {
        height: fit-content;
        background: transparent;
        padding: 0;
        display: flex;
        position: absolute;
        justify-content: space-between;
        align-items: center;
        padding-left: 150px;
        top: 6px;
    }

    .menu-container.active_menu {
        display: flex;
    }

    .logo-container.active_menu {
        position: relative;
        width: fit-content;
    }

    .logo-container.active_menu,
    .logo-container.active_menu .nav-logo {
        color: #110F24;
    }

    .logo-container.active_menu .nav-logo:hover,
    .menu-container.active_menu a:hover {
        color: #575BDE;
    }

    ul li {
        display: inline-block;
        padding: 0 10px;
    }

    nav ul li a {
        font-size: 1rem;
        font-weight: 600;
        color: #110F24;
    }

    nav ul li button {
        font-size: 1rem;
        font-weight: 600;
        color: #110F24;
    }

    nav.light_color .logo-container,
    nav.light_color .nav-logo {
        color: #fff !important;
    }

    nav.light_color ul li a {
        color: #fff;
    }

    nav.light_color ul li button {
        color: #fff;
    }

    nav ul li button.menu-btn {
        padding: 10px 15px;
    }

    nav a:hover,
    nav button:hover {
        color: #575BDE !important;
    }

    nav.light_color a:hover,
    nav.light_color ul li button:hover {
        color: #fff !important;
        opacity: 0.9;
    }
}

@media screen and (min-width: 992px) {
    .menu-container {
        padding-left: 180px;
    }
}
</style>