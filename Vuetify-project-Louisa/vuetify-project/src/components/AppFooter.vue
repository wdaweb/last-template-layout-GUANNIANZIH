<template>
  <!-- 如果加了 app 屬性會讓 footer 固定在畫面底部 -->
  <v-footer class="bg-deep">
    <v-container class="my-container">
      <v-row>
        <v-col cols="4" class="d-flex align-center justify-center">
          <img src="../assets/logo-girl-image().png" height="80">
        </v-col>

        <v-col cols="4">
          <div>
            <p>熱門訊息</p>
            <hr>
            <ul class="none-list-style no-bullets">
              <li
              v-for="news in popularNews"
              :key="news.href">
                <a :href="news.href" target="_blank" class="custom-link">
                  {{ news.title }}
                </a>
                <br>
                {{ news.date }}
              </li>
            </ul>
          </div>
        </v-col>

        <v-col cols="4">
          <div>
            <p>咖啡世界</p>
            <hr>
            <ul class="none-list-style no-bullets">
              <li
              v-for="coffee in coffeeWorld"
              :key="coffee.href">
              <a :href="coffee.href" target="_blank" class="custom-link">
                {{ coffee.title }}
              </a>
              <br>
              {{ coffee.date }}
              </li>
            </ul>
          </div>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12">
          <span>2020© Copyright 2024 - LOUISA COFFEE | </span>
          <a href="https://www.uof.tw/louisa/Login.aspx?ReturnUrl=%2flouisa%2f" target="_blank" class="custom-link">夥伴登入</a>
        </v-col>
      </v-row>
      <v-row>
        <v-col clos="12" class="d-flex align-center justify-center">
          <v-btn class="custom-btn"><a href="#" class="top-btn">TOP</a></v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script setup>
import { definePage } from 'vue-router/auto'

definePage({
  meta: {
    title: '路易莎咖啡 LOUISA COFFEE'
  }
})

const popularNews = [
  {
    title: '新品上市 | 清爽系西西里咖啡',
    icon: 'mdi-arrow-right',
    href: 'https://www.louisacoffee.co/news#341',
    date: 'Jun 161, 2024'
  },
  {
    title: '蔬食新選擇 美味登場',
    icon: 'mdi-arrow-right',
    href: 'https://www.louisacoffee.co/news#342',
    date: 'Jun 16, 2024'
  },
  {
    title: '超值活力早餐全新改版',
    icon: 'mdi-arrow-right',
    href: 'https://www.louisacoffee.co/news#340',
    date: 'Jun 15, 2024'
  }
]

const coffeeWorld = [
  {
    title: '「台灣⇄京都」橫跨千里 尋茶之旅',
    icon: 'mdi-arrow-right',
    href: 'https://www.louisacoffee.co/news#341',
    date: 'Apr 1, 2020'
  },
  {
    title: '京都宇治抹茶甜點職人來台技術交流',
    icon: 'mdi-arrow-right',
    href: 'https://www.louisacoffee.co/blog1show/34',
    date: 'Apr 1, 2020'
  },
  {
    title: '京都宇治茶職人來台技術交流',
    icon: 'mdi-arrow-right',
    href: 'https://www.louisacoffee.co/blog1show/35',
    date: 'Apr 1, 2020'
  }
]
</script>

<style scoped lang="scss">
  // container
  .my-container{
    width: 80%;
    margin: 0 auto;
    // padding: 0 64px;
  }
  // bg
  .bg-deep {
    font-size: 12px;
    color: white;
    background-color: rgb(46, 46, 46);
  }
  // list
  .none-list-style {
    list-style: none;
  }
  .no-bullets {
  list-style-type: none;
  padding: 0;
  }
    // a
  .custom-link {
    color: white;
    text-decoration: none;
  }
  .custom-link:visited {
    color: white;
    text-decoration: none;
  }
  .custom-link:hover {
    text-decoration: underline;
    text-decoration: none;
  }
  // TOP - btn
  .a-class {
    display: block;
  }
  .custom-btn{
    border-radius: 0;
    border: 1px solid white;
    background-color: rgb(46, 46, 46);
  }
  .top-btn {
    color: gray;
    text-decoration: none;
    background-color: rgb(46, 46, 46);
  }

</style>
