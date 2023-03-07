<template>
    <div>
        <main>
            <section class="about-hero">
                <p class="faint-text">Who We Are</p>
                <h1 class="title">We're a community of designers and developers creating tools for the web.</h1>
            </section>
            <section class="essay">
                <p class="paragraph1">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
                    dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip
                    ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu
                    fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia
                    deserunt mollit anim id est laborum.

                    Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam
                    rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt
                    explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia
                    consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt.

                    Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia
                    non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad
                    minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea
                    commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil
                    molestiae consequatur.

                    At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum
                    deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non
                    provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga.
                </p>
                <div>
                    <img src="../assets/images/about-01.jpg" alt="">
                </div>
                <p>
                    Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est
                    eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas
                    assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum
                    necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae.
                </p>
                <div class="essay-img-flex">
                    <img src="../assets/images/about-02.jpg" alt="">
                    <img src="../assets/images/about-03.jpg" alt="">
                </div>
            </section>
            <section class="about-join">
                <h2 class="title">Want to join the team?</h2>
                <p class="text">We’re hiring. Work from anywhere.</p>
                <Button :text="'Job Openings'" :bgColor="'#ffffff2f'" :textColor="'#fff'"></Button>
            </section>
            <section class="about-investors">
                <h2 class="caption">Our Investors</h2>
                <p class="text">We've completed a $120 million Series B financing round.</p>
                <div class="investors-brand-flex">

                    <img src="../assets/images/trusted-company.png" alt="">
                    <img src="../assets/images/trusted-company.png" alt="">
                    <img src="../assets/images/trusted-company.png" alt="">
                    <img src="../assets/images/trusted-company.png" alt="">
                </div>
            </section>
        </main>
        <Footer></Footer>
    </div>
</template>

<script>
import Footer from '../components/Footer.vue';
import Button from '../components/Button.vue';

export default {
    components: { Footer, Button }
}
</script>

<style scoped>
section {
    padding: 50px 5%;
}

.title {
    font-size: 2.8rem;
    font-weight: 700;
    margin-bottom: 22px;
    line-height: 55px;
    text-align: center;
}

.text {
    line-height: 30px;
    opacity: 0.9;
    font-size: 1.3rem;
}

.faint-text {
    opacity: 0.5;
    margin-bottom: 15px;
}

.about-hero {
    padding: 140px 5% 40px;
    text-align: center;
}

.essay {
    font-size: 1.3rem;
    line-height: 30px;
}

.essay img {
    display: block;
    border-radius: 7px;
    margin: 50px 0;
}

.about-join {
    color: #fff;
    text-align: center;
    padding: 180px 15px;
    background: url('../assets/images/join-img.jpg');
    background-color: rgba(0, 0, 0, 0.801);
    background-size: cover;
    background-blend-mode: soft-light;
}

.about-join .text {
    margin-bottom: 30px;
}

.about-investors {
    text-align: center;
}


.investors-brand-flex {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    margin: 50px 0 20px;
  }
  
  .investors-brand-flex img {
    width: 140px;
    margin-bottom: 35px;
  }

.about-investors .caption {
    font-size: 2rem;
    margin-bottom: 20px;
}

@media screen and (min-width: 768px) {
    .about-hero {
        width: 80%;
        margin: auto;
    }
.paragraph1 {
    -webkit-column-count: 2;
    -moz-column-count: 2;
    column-count: 2;

    -webkit-column-gap: 40px;
    -moz-column-gap: 40px;
    column-gap: 40px;
}

.essay-img-flex {
    display: flex;
    justify-content: space-between;
}

.essay-img-flex>img {
    width: 48%;
}

.investors-brand-flex img {
    width: 250px;
    margin-bottom: 35px;
}

.investors-brand-flex {
    width: 80%;
    margin: 50px auto 20px
  }

  .investors-brand-flex img {
    width: 190px;
    margin-bottom: 50px;
  }
}

@media screen and (min-width: 1024px) {
    .about-hero {
        width: 60%;
        padding: 140px 20px;
    }

    .investors-brand-flex img {
        width: 170px;
        margin-top: 40px;
      }
}
</style>