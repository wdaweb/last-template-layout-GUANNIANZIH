<template>
  <!-- v-container-drawer 手機板導航 -->
  <v-navigation-drawer v-if="mobile" v-model="drawer">
    <v-list nav>
      <template v-for="item in navItems" :key="item.to">
        <v-list-item
        :to="item.to"
        :title="item.text"
        >
        </v-list-item>
      </template>
    </v-list>
  </v-navigation-drawer>
<!-- v-app-bar 電腦版導航列 -->
  <v-app-bar>
    <v-container class="d-flex align-center">
      <a href="/">
        <img src="../assets/logo-dark.png" class="logo">
      </a>
      <v-spacer />
      <!-- mobile 漢堡選單 -->
      <!-- 顯示一個應用欄導航圖標，當點擊會打開側邊 drawer -->
      <template v-if="mobile">
        <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      </template>
      <!-- 如果沒有點擊，顯示電腦版選單 -->
      <template v-else>
        <template v-for="item in navItems" :key="item.to">
          <v-btn :to="item.to">
            {{ item.text }}
          </v-btn>
        </template>
      </template>
    </v-container>
  </v-app-bar>
  <v-main>
    <router-view></router-view>
  </v-main>

  <AppFooter />
</template>

<script setup>
// ref 處理響應式、computed 處理計算屬性
import { ref, computed } from 'vue'
// Vuetify 提供的一個 Composition API，用來檢查當前設備的顯示屬性
import { useDisplay } from 'vuetify'
import AppFooter from '@/components/AppFooter.vue'

const { mobile } = useDisplay()
// 綁定 v-model="drawer"
const drawer = ref(false)

// 導航列
const navItems = computed(() => {
  return [
    // When use the show? add icon,
    { to: '/', text: '首頁' },
    { to: '/stores', text: '門市查詢' },
    { to: '/news', text: '最新消息' },
    { to: '/investors', text: '投資人專區' },
    { to: '/product', text: '商品介紹' },
    { to: '/coffee', text: '咖啡世界' },
    { to: '/about', text: '關於我們' },
    { to: '/contact', text: '聯絡我們' }
  ]
})
</script>

<style scoped>
.logo{
height: 20px;
}

</style>
