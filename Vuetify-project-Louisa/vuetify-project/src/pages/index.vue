<template>
    <v-container fluid class="my-v-container">
        <!-- part 01 -->
        <v-responsive class="align-center mx-auto">

            <!-- Swiper container -->
            <Swiper
                :modules="[Autoplay]"
                :autoplay="{ delay: 3000 }"
                loop= true
                class="mySwiper"
                >
                <!-- Swiper slides -->
                <SwiperSlide v-for="(photo, index) in photos" :key="index">
                    <v-img :src="photo.url" class="w-100"></v-img>
                </SwiperSlide>
            </Swiper>
        </v-responsive>
        <!-- news -->
        <block-news />
        <!-- part 02 -->
        <v-container class="my-v-container-part-02" fluid>
            <v-row class="my-row">
                <v-col class="my-col d-inline-block" cols="12" sm="6" md="4" lg="4"  data-aos="slide-right" data-aos-delay="1000">
                    <a href="https://www.louisacoffee.co/news" class="d-block w-100 h-100 text-center" >
                        <v-img src='@/assets/20210126_022346-image().jpg' class="my-img">
                          <div class="text-overlay">
                            最新消息
                            <br>
                            Latest News
                          </div>
                        </v-img>
                    </a>
                </v-col>
                <v-col class="my-col d-inline-block" cols="12" sm="6" md="4" lg="4" data-aos="fade-down" data-aos-delay="1000">
                    <a href="https://www.louisacoffee.co/visit " class="d-block w-100 h-100 text-center">
                        <v-img src='@/assets/20210126_023416-image().jpg' class="my-img">
                          <div class="text-overlay">
                            門市查詢
                            <br>
                            Store Location
                          </div>
                        </v-img>
                    </a>
                </v-col>
                <v-col class="my-col d-inline-block" cols="12" sm="6" md="4" lg="4" data-aos="slide-left" data-aos-delay="1000">
                    <a href="http://www.louisacafe.com/product s" class="d-block w-100 h-100 text-center">
                        <v-img src='@/assets/20230105_013657-image().jpg' class="my-img">
                          <div class="text-overlay">
                            商品專區及訂單下載
                            <br>
                            Product & Purchase Order
                          </div>
                        </v-img>
                    </a>
                </v-col>
                <v-col class="my-col d-inline-block" cols="12" sm="6" md="4" lg="4" data-aos="slide-right" data-aos-delay="1000">
                    <a href="https://www.louisacoffee.co/conta ct-info" class="d-block w-100 h-100 text-center">
                        <v-img src='@/assets/20210126_022842-image().jpg' class="my-img">
                          <div class="text-overlay">
                            聯絡我們
                            <br>
                            Contact Us
                          </div>
                        </v-img>
                    </a>
                </v-col>
                <v-col class="my-col d-inline-block" cols="12" sm="6" md="4" lg="4" data-aos="fade-up" data-aos-delay="1000">
                    <a href="https://www.louisacoffee.co/produ cts_list/6" class="d-block w-100 h-100 text-center">
                        <v-img src='@/assets/20210126_022717-image().jpg' class="my-img">
                          <div class="text-overlay">
                            糕點
                            <br>
                            Pastry
                          </div>
                        </v-img>
                    </a>
                </v-col>
                <v-col class="my-col d-inline-block" cols="12" sm="6" md="4" lg="4" data-aos="slide-left" data-aos-delay="1000">
                    <a href="https://www.louisacoffee.co/produ cts_list/13" class="d-block w-100 h-100 text-center">
                        <v-img src='@/assets/20210126_022410-image().jpg' class="my-img">
                          <div class="text-overlay">
                            輕食
                            <br>
                            Light Meal
                          </div>
                        </v-img>
                    </a>
                </v-col>
            </v-row>
        </v-container>

        <!-- part2-debug -->
        <!-- <template>
          <v-container class="my-v-container-part-02" fluid>
              <v-row class="my-row" v-for="(photo, index) in getRows()" :key="index">
                <v-col v-for="(item, colIndex) in photo" :key="colIndex" class="my-col" cols="12" md="4">
                  <a :href="item.link">
                    <v-img :src="item.url" class="my-img">
                      <template v-slot:default>
                        <div class="text-overlay">
                          {{ item.title }}
                          <br>
                          {{ item.subtitle }}
                        </div>
                      </template>
                    </v-img>
                  </a>
                </v-col>
              </v-row>
          </v-container>
        </template> -->

    </v-container>
</template>

<script setup>
import { definePage } from 'vue-router/auto'
import { ref } from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'
// import { gsap } from 'gsap'
// import { ScrollTrigger } from 'gsap-ScrollTrigger'

import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/autoplay'
import { Autoplay } from 'swiper/modules'

// gsap.registerPlugin(ScrollTrigger)

AOS.init({
  once: true
})

definePage({
  meta: {
    title: '路易莎咖啡 LOUISA COFFEE'
  }
})

const photos = ref([
  { url: new URL('@/assets/20240611_072503-image(750x_).jpg', import.meta.url).href },
  { url: new URL('@/assets/20240612_055403-image(750x_).jpg', import.meta.url).href },
  { url: new URL('@/assets/20240625_085912-image(750x_).jpg', import.meta.url).href },
  { url: new URL('@/assets/20240606_075255-image(750x_).jpg', import.meta.url).href }
])

// const newsPhotos = ref([
//   {
//     url: new URL('@/assets/20210126_022346-image().jpg', import.meta.url).href,
//     title: '最新消息',
//     subtitle: 'Latest News',
//     link: 'https://www.louisacoffee.co/news'
//   },
//   {
//     url: new URL('@/assets/20210126_023416-image().jpg', import.meta.url).href,
//     title: '門市查詢',
//     subtitle: 'Store Location',
//     link: 'https://www.louisacoffee.co/visit'
//   },
//   {
//     url: new URL('@/assets/20230105_013657-image().jpg', import.meta.url).href,
//     title: '商品專區及訂單下載',
//     subtitle: 'Product & Purchase Order',
//     link: 'http://www.louisacafe.com/products'
//   },
//   {
//     url: new URL('@/assets/20210126_022842-image().jpg', import.meta.url).href,
//     title: '聯絡我們',
//     subtitle: 'Contact Us',
//     link: 'https://www.louisacoffee.co/contact-info'
//   },
//   {
//     url: new URL('@/assets/20210126_022717-image().jpg', import.meta.url).href,
//     title: '糕點',
//     subtitle: 'Pastry',
//     link: 'https://www.louisacoffee.co/products_list/6'
//   },
//   {
//     url: new URL('@/assets/20210126_022410-image().jpg', import.meta.url).href,
//     title: '輕食',
//     subtitle: 'Light Meal',
//     link: 'https://www.louisacoffee.co/products_list/13'
//   }
// ])

// console.log(newsPhotos.value.map(photo => photo.url))

// const getRows = () => {
//   const rows = []
//   for (let i = 0; i < newsPhotos.value.length; i += 3) {
//     rows.push(newsPhotos.value.slice(i, i + 3))
//   }
//   return rows
// }

// onMounted(() => {
//   const tl = gsap.timeline({ repeat: -1 }) // 創建一個無限循環的時間軸
//   photos.value.forEach((photo, index) => {
//     const selector = `.photo:nth-child(${index + 1})`
//     tl.to(selector, { opacity: 1, duration: 2 }) // 漸顯
//       .to(selector, { opacity: 0, duration: 2 }, '+=2') // 保持顯示2秒，然後漸隱
//   })
// })

</script>

<style scoped lang="scss">
html, body, #app{
  height: 100%;
  margin: 0;
  padding: 0;
}

.my-v-container{
  padding: 0;
  margin: 0;
  // background-color: red;
}

.v-responsive {
  position: relative;
}

.my-v-container-part-02{
  width: 1170px;
  height: 860px;
  padding: 0;
  margin: auto;
  margin-bottom: 600px;
  // display: flex;
  // justify-content: center;
  // align-items: center;
  // background-color: red;
}

.my-row {
  margin: 0px;
  padding: 0;
}

.my-col {
  padding: 0;
  margin: 0;
  // display: inline-block;
  // vertical-align: top;
  // text-align: center;
  // padding: 0 !important;
  // margin: 0 !important;
}

a {
  color: white;
  text-decoration: none;
  text-align: center;
  font-size: 16px;
}

// .my-img-wrapper {
//   display: block;
//   position: relative;
//   width: 100%;
//   height: 100%;
// }

.my-img {
  // width: 390px;
  height: auto;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction:row;
  justify-content:flex-end;
  align-items:end;
  transition: background-color 0.3s ease;
}

.my-img-wrapper:hover .my-img {
  background-color: rgba(0, 0, 0, 0.5);
}

.text-overlay {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  color: white;
  background: rgba(0, 0, 0, 0.5);
  padding: 10px;
  width: 100%;
  text-align: center;
}

</style>
