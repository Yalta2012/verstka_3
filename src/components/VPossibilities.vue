
<script setup>

import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination} from 'swiper/modules';
import '@/../node_modules/swiper/swiper-bundle.min.css';

const cards = [
    {
        src: "/chat_logo.svg",
        title: "Общение с классом",
        text: "Видеосвязь<br>Чат с классом",
        color: "possibilities__card__blue"
    },

    {
        src: "/monitor_logo.svg",
        title: "Проведение занятий",
        text: "Презентация файлов <br> Демонстрация экрана",
        color: "possibilities__card__orange"
    },

    {
        src: "/menu_logo.svg",
        title: "Посещаемость",
        text: "Автоматическое <br>отслеживание<br> присутствующих",
        color: "possibilities__card__blue"
    },

    {
        src: "/reload_logo.svg",
        title: "История занятий",
        text: "Материалы урока",
        color: "possibilities__card__orange"
    }
]

</script>

<template>
    <!--
    <swiper  
    :modules="modules"
    :slides-per-view="3"
    :space-between="50"
    
    :pagination="{ clickable: true }"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
>
        <swiper-slide>Slide 1</swiper-slide>
        <swiper-slide>Slide 2</swiper-slide>
        <swiper-slide>Slide 3</swiper-slide>
        <swiper-slide>Slide 1</swiper-slide>
        <swiper-slide>Slide 2</swiper-slide>
        <swiper-slide>Slide 3</swiper-slide>
        
    </swiper>
-->
    <section class="possibilities">
        <div class="container">
            <div class="possibilities__header">
                <h3>Возможности</h3>
            </div>
            <swiper :modules="[Pagination]" :space-between="30"  :pagination="{ el: '.possibilities__swiper-pagination',clickable: true }"
                :breakpoints="{
                0: { slidesPerView: 1 },
                560: { slidesPerView: 2 },
                992: { slidesPerView: 3 },
                1200: { slidesPerView: 4 }
            }" 
                >

                <swiper-slide v-for="(item,index) in cards" :key="index">
                    <div class="possibilities__swiper-slide">
                        <div class="possibilities__card" :class="item.color">
                            <img :src="item.src" alt="" class="possibilities__logo">
                            <h4>{{item.title}}</h4>
                            <p v-html="item.text"></p>
                        </div>
                    </div>
                </swiper-slide>
                <div class="possibilities__swiper-pagination swiper-pagination"></div>
            </swiper>
        </div>
    </section>
    <!--
    <section class="possibilities">
        <div class="container">
            <div class="possibilities__header">
                <h3>Возможности</h3>
            </div>
            <div class="possibilities__swiper-block">
                <div class="possibilities__swiper swiper">
                    <div class="possibilities__swiper-wrapper swiper-wrapper">
                        <div class="possibilities__swiper-slide swiper-slide">
                            <div class="possibilities__card possibilities__card__blue">
                                <img :src="item.src" alt="" class="possibilities__logo">
                                <h4>{{item.title}}</h4>
                                <p>Видеосвязь <br />Чат с классом
                                </p>
                            </div>
                        </div>
                        
                        <div class="possibilities__swiper-slide swiper-slide">
                            <div class="possibilities__card possibilities__card__orange">
                                <img src="/monitor_logo.svg" alt="" class="possibilities__logo">
                                <h4>Проведение занятий</h4>
                                <p>Презентация файлов <br />Демонстрация экрана</p>
                            </div>
                        </div>

                        <div class="possibilities__swiper-slide swiper-slide">
                            <div class="possibilities__card possibilities__card__blue">
                                <img src="/menu_logo.svg" alt="" class="possibilities__logo">
                                <h4>Посещаемость</h4>
                                <p>Автоматическое <br /> отслеживание <br /> присутствующих</p>

                            </div>
                        </div>
                        <div class="possibilities__swiper-slide swiper-slide">
                            <div class="possibilities__card possibilities__card__orange">
                                <img src="/reload_logo.svg" alt="" class="possibilities__logo">
                                <h4>История занятий</h4>
                                <p>Материалы урока</p>
                            </div>
                        </div>
                        
                    </div>
                    
                    <div class="swiper-pagination"></div>
                </div>

            </div>
        </div>

    </section>-->
</template>