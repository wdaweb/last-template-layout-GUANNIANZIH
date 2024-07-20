[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/aMHx-K_k)
<br>

### 參考路易莎官方網站
<br>
https://www.louisacoffee.co/
<br>

### 使用套件: swiper, aos, gsap

<hr>

### 套件一、swiper
#### 使用在 index.vue 首頁輪播圖中
```
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/autoplay'
import { Autoplay } from 'swiper/modules'

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
```
<hr>

### 套件二、aos
#### 使用在 index.vue 首頁的最新消息照片滑入效果
```
import AOS from 'aos'
import 'aos/dist/aos.css'

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
```
<hr>

### 套件三、gsap
#### 使用在 index.vue 首頁
```
// import { gsap } from 'gsap'
// import { ScrollTrigger } from 'gsap-ScrollTrigger'

// gsap.registerPlugin(ScrollTrigger)

// onMounted(() => {
//   const tl = gsap.timeline({ repeat: -1 }) // 創建一個無限循環的時間軸
//   photos.value.forEach((photo, index) => {
//     const selector = `.photo:nth-child(${index + 1})`
//     tl.to(selector, { opacity: 1, duration: 2 }) // 漸顯
//       .to(selector, { opacity: 0, duration: 2 }, '+=2') // 保持顯示2秒，然後漸隱
//   })
// })
```
