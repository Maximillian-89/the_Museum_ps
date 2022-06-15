<template>
<div class="lightbox-gallery">
    <div class="container-fluid">
        <div class="row">
            <div class="col-9 col-md-6">
                <h2>{{title}}</h2>
                <p>{{text}}</p>
            </div>
            <div class="col-3 col-md-6">
                <div class="lightbox-gallery-close">
                    <button @click="$emit('closeLightbox')"><img src="@/assets/img/close_icon.png" alt="close button"></button>
                </div>
            </div>
        </div>
        <div class="slider">
            <!-- Slider main container -->
            <div ref="swiper" class="swiper">
                <!-- Additional required wrapper -->
                <div class="swiper-wrapper">
                    <!-- Slides -->
                    <div class="swiper-slide" v-for="(slide, index) in slides" :key="index">
                        <img :src="slide">
                    </div>
                </div>
                    <!-- If we need pagination -->
                    <!-- If we need navigation buttons -->
                    <!-- <div class="swiper-button-prev"></div>
                    <div class="swiper-button-next"></div> -->
            </div>
        </div>
        <div class="swiper-pagination"></div>
    </div>
</div>
</template>

<script>
import Swiper, { Navigation, Pagination, Autoplay } from 'swiper';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

export default {
    name: 'LightboxGallery',
    props: {
        slides: Array,
        title: String,
        text: String
    },
    mounted() {
        new Swiper(this.$refs.swiper, {
        // configure Swiper to use modules
        modules: [Navigation, Pagination, Autoplay],
        autoplay: {
            delay: 3000,
            disableOnInteraction: true,
        },
        // Optional parameters
        loop: true,

        slidesPerView: "auto",
        spaceBetween: 10,
        breakpoints: {
            768: {
                spaceBetween: 30,
            }
        },

        // If we need pagination
        pagination: {
            el: '.swiper-pagination',
        },

        // Navigation arrows
        navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev',
        },

        // And if we need scrollbar
        scrollbar: {
            el: '.swiper-scrollbar',
        },
        })
    },
}
</script>

<style lang="scss">
@import '@/assets/style/variables.scss';

.lightbox-gallery {
    --swiper-pagination-bullet-inactive-color: #fff;
    --swiper-pagination-color: #fff;
    --swiper-pagination-bullet-horizontal-gap: .625rem;

    background: $otherBgColor;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    max-width: 120rem;
    z-index: 1;
    padding: 7.5rem 0 5rem 7.5rem;
    
    @media screen and (min-width: 120rem) {
        left: calc((100% - 120rem) / 2);
    }

    @media screen and (max-width: 768px) {
        padding: 2rem 0 1rem 2rem;
    }

    h2 {
        color: #fff;
        margin-bottom: 2.5rem;
    }

    p {
        color: rgba(255,255,255,0.5);
    }

    .slider {
        margin-top: 5rem;
    }

    &-close {
        text-align: right;
    }

    .swiper-slide {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 75%;

        img {
            width: 100%;
            max-height: 55vh;
            object-fit: cover;
        }
    }
    .swiper-pagination {
        position: relative;
        text-align: left;
        padding: 1.875rem 0;
    }
    .swiper-pagination-bullet {
        border-radius: 0!important;
        transform: rotate(45deg);
        padding: .3125rem;
    }

    .lightbox-gallery-close {
        button {
            background: transparent;
            border: none;

            img {
                max-width: 100%;
            }
        }
    }
}
</style>