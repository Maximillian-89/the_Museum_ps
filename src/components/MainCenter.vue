<template>
    <main>
        <div class="container-fluid">
            <div class="custom-container">
                <div class="main_head_container pt_100 pb_70">
                    <div class="row" id="first-row">
                        <div class="col-xl-4 col-lg-12">
                            <h2>TITLE</h2>
                        </div>
                    </div>
                    <div class="row" id="select-row">
                        <div class="col-xl-6 ">
                            <div class="first-select">
                                <h4>DATA</h4>
                                <div class="select-container">
                                    <div class="data-select">Tutte le date</div>
                                    <div><img src="@/assets/img/Vector.png" alt="arrowDown"></div>
                                </div>
                            </div>
                        </div>
                        <div class="col-xl-6">
                            <div class="second-select">
                                <h4>COSA</h4>
                                <div class="select-container">
                                    <div class="activity-select">Tutte le attività</div>
                                    <div><img src="@/assets/img/Vector.png" alt="arrowDown"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>          
                <div class="row" id="second-row">
                    <div v-for="(card, index) in allCards" class="col-xs-12 col-md-6" :key="index" @click="lightboxShow=true,lightboxActive = index">
                        <div class="card_img">
                            <img :src="card.img" :alt="card.alt">
                            <img :src="card.imgBg" :alt="card.alt">
                        </div>
                        <div class="card-data-time">
                            <h3>{{card.title}}</h3>
                            <p>{{card.date}}</p>
                        </div>
                    </div>
                </div>
                <!-- <div class="more-item"></div> -->
                <div class="text-center">
                    <button id="load-more" class="my-btn" @click="onLoadMore">{{ loadMore ? 'NASCONDI' : 'LOAD MORE' }}</button>
                </div>
            </div>
        </div>
        <LightboxGallery v-if="lightboxShow" :title="cards[lightboxActive].title" :text="cards[lightboxActive].text" :slides="cards[lightboxActive].slider" @closeLightbox="lightboxShow = false"/>
    </main>
</template>


<script>
import LightboxGallery from './LightboxGallery.vue'
export default {
    components: 
    { 
        LightboxGallery,
    },
    name: 'MainCenter',
    data() {
        return {
            lightboxShow: false,
            lightboxActive: 0,
            loadMore: false,
            cards: [
                {
                    img: require("@/assets/img/musei-img/cr_foto-1-mart_-_museo_di_arte.jpg"),
                    imgBg:require("@/assets/img/musei-img/Estonia_Tallinn_.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 01",
                    date: "Apr 17 - Nov 01, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/cr_foto-1-mart_-_museo_di_arte.jpg"),
                        require("@/assets/img/musei-img/Estonia_Tallinn_.jpg"),
                        require("@/assets/img/musei-img/France_Houses_Louvre.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/galleria-d-arte-moderna.jpg"),
                    imgBg:require("@/assets/img/musei-img/Galleria-degli-uffizi-Firenze.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 02",
                    date: "Lug 01 - Ott 25, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/galleria-d-arte-moderna.jpg"),
                        require("@/assets/img/musei-img/Galleria-degli-uffizi-Firenze.jpg"),
                        require("@/assets/img/musei-img/Galleria-Estense_ModenaFoto-Silvia-Gelli_110.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/Guida-easy-to-read-del-Museo-Popoli.jpg"),
                    imgBg:require("@/assets/img/musei-img/images.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 03",
                    date: "Set 15 - Nov 22, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/Guida-easy-to-read-del-Museo-Popoli.jpg"),
                        require("@/assets/img/musei-img/images.jpg"),
                        require("@/assets/img/musei-img/images123.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/IMG-20220228-WA0024.jpg"),
                    imgBg:require("@/assets/img/musei-img/MdT_percorso_locale-caldaia.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 04",
                    date: "Set 23 - Gen 17, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/IMG-20220228-WA0024.jpg"),
                        require("@/assets/img/musei-img/MdT_percorso_locale-caldaia.jpg"),
                        require("@/assets/img/musei-img/MdT_percorso_sala-tessuti-antichi.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/miami_wolfsoanian_museum_01_presentazione.jpg"),
                    imgBg:require("@/assets/img/musei-img/Model-.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 05",
                    date: "Set 15 - Nov 22, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/miami_wolfsoanian_museum_01_presentazione.jpg"),
                        require("@/assets/img/musei-img/Model-.jpg"),
                        require("@/assets/img/musei-img/Museo.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/Museo07.jpg"),
                    imgBg:require("@/assets/img/musei-img/Museo-Ara-Pacis.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 06",
                    date: "Set 23 - Gen 17, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/Museo07.jpg"),
                        require("@/assets/img/musei-img/Museo-Ara-Pacis.jpg"),
                        require("@/assets/img/musei-img/MUSEOBARRACCO.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/museo-dino-formaggio.jpg"),
                    imgBg:require("@/assets/img/musei-img/Museo-enzo-ferrari-in-emilia-romagna.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 07",
                    date: "Set 15 - Nov 22, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/museo-dino-formaggio.jpg"),
                        require("@/assets/img/musei-img/Museo-enzo-ferrari-in-emilia-romagna.jpg"),
                        require("@/assets/img/musei-img/Museo-Lechi.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/Ontwerp-zonder-titel4.png"),
                    imgBg:require("@/assets/img/musei-img/Spain_Fountains_National_Museum.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 08",
                    date: "Set 23 - Gen 17, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/Ontwerp-zonder-titel4.png"),
                        require("@/assets/img/musei-img/Spain_Fountains_National_Museum.jpg"),
                        require("@/assets/img/musei-img/Tecnologia-MAN.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/images123.jpg"),
                    imgBg:require("@/assets/img/musei-img/Estonia_Tallinn_.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 09",
                    date: "Set 15 - Nov 22, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/cr_foto-1-mart_-_museo_di_arte.jpg"),
                        require("@/assets/img/musei-img/Estonia_Tallinn_.jpg"),
                        require("@/assets/img/musei-img/France_Houses_Louvre.jpg"),
                    ]
                },
                {
                    img: require("@/assets/img/musei-img/images.jpg"),
                    imgBg:require("@/assets/img/musei-img/Estonia_Tallinn_.jpg"),
                    alt:"Foto sala del museo",
                    title: "Gallery 10",
                    date: "Set 23 - Gen 17, 2020",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur sed nisi incidunt vero optio obcaecati natus velit at quibusdam officiis repellat similique quisquam, iste, accusamus pariatur tenetur eligendi facere blanditiis.",
                    slider: [
                        require("@/assets/img/musei-img/cr_foto-1-mart_-_museo_di_arte.jpg"),
                        require("@/assets/img/musei-img/Estonia_Tallinn_.jpg"),
                        require("@/assets/img/musei-img/France_Houses_Louvre.jpg"),
                    ]
                }
            ]
        }
    },
    methods: {
        onLoadMore() {
            this.loadMore = !this.loadMore;
        }
    },
    computed: {
        allCards() {
            if(this.loadMore) {
                return [...this.cards, ...this.cards];
            }
            return this.cards;
        }
    }
}
</script>


<style lang="scss" scoped>
@import '@/assets/style/variables.scss';
    main {
        background: $mainBgColor;
    }

    .main_head_container {
        display: flex;
        align-items: center;
    }

    #first-row {
        display: flex;
        align-items: center;
        flex-grow: 1;

        h2 {
            font-weight: 500;
            font-size: 3rem;
            line-height: 3.5rem;
            letter-spacing: -0.04em;
        }
    }

    #select-row {
        flex-grow: 5;
        align-items: center;
    }

    .first-select, .second-select {
        display: flex;
        align-items: center;
        justify-content: flex-end;

        h4 {
            font-weight: 400;
            font-size: 2rem;
            line-height: 2.625rem;
            letter-spacing: -0.04em;
            padding-right: 1.125rem;
        }
    }

    .second-select {
        align-items: center;
        justify-content: flex-end;
    }

    .select-container{
            border-bottom: .0625rem solid $selectColor;
            display: flex;
            align-items: center;
            cursor: pointer;

            .data-select, .activity-select {
                font-weight: 400;
                font-size: 1.375rem;
                line-height: 1.9375rem;
                padding-right: 5.3125rem;
            }
        }

    .col-xs-12.col-md-6 {
        margin-bottom: 7.5rem;
    }
    .card_img {
        position: relative;
        img {
            width: 100%;
            transition: transform 0.3s, opacity 0.4s;

            &:first-child {
                position: absolute;
                z-index: 1;
            }
            &:last-child {
                transform: rotate(5deg);
                opacity: 0;
            }
        }
        &:hover {
            img {
                &:first-child {
                    transform: rotate(5deg);
                }
                &:last-child {
                    transform: rotate(0deg);
                    opacity: 1;
                }
            }
        }
    }

    .card-data-time {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: .9375rem 0 1.5625rem 0;

        h3 {
            font-weight: 500;
            font-size: 2rem;
            line-height: 2.625rem;
            letter-spacing: -0.04em;
        }

        p {
            font-weight: 400;
            font-size: 1.625rem;
            line-height: 2.25rem;
            color: $typoMainColor;
        }
    }

    .card-data-time p {
        font-size: .8125rem;
    }

    .second-row .col {
        flex: 1 0 50%!important;
    }

    .my-btn {
        border: none;
        background: transparent;
        font-weight: 600;
        border-bottom: .125rem solid black;
    }

    .text-center {
        text-align: center;
        padding-bottom: 6.25rem;

        button {
            font-weight: 600;
            font-size: 1.75rem;
            line-height: 2.25rem;
            letter-spacing: -0.02em;
        }
    }

@import '@/assets/style/mediaQueryCenter.scss';
</style>