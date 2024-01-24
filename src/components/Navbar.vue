<template>
    <div class="relative top-0 z-20 flex flex-col items-center justify-between flex-shrink-0 w-full px-6 py-3 text-white bg-blue-200 md:px-20 sm:flex-row sm:sticky">
        <!-- Logo -->
        <div class="flex items-center justify-between w-full px-3 sm:w-fit ">
          <RouterLink to="/" class="w-40 aspect-auto">
            <img src="@/assets/logo.png" alt="" class="">
  
          </RouterLink>
  
          <!-- 手機選單按鈕 -->
          <button type="button" 
          class="w-8 h-8 ml-auto sm:hidden"
          @click="toggleMenu">
            <heroicons-outline-menu class="w-5 h-5" />
          </button>
        </div>
  
        <div class="flex items-center justify-center gap-10">
          <!-- 主要選單 -->
          <div 
          class="sm:flex sm:flex-col sm:justify-between"
          :class="showMenu ? '' : 'hidden'">
            <ul class="flex flex-col sm:flex-row">
              <li v-for="item in menuItems" :key="item.to">
                <RouterLink :to="item.to" 
                class="flex items-center px-3 py-3 lg:text-lg sm:px-5 whitespace-nowrap"
                :class="isActive(item.to) ? 'text-white' : 'text-blue-500  hover:text-white'">
                  {{ item.text }}
                </RouterLink>
              </li>
            </ul>
          </div>
        </div>
    </div>
  </template>
  
  <script>
  import { computed, ref } from "vue";
  import { useRoute, useRouter } from 'vue-router';
  
  export default {
    setup() {
      const route = useRoute()
      const router = useRouter()
  
      const showMenu = ref(false)
      // 在 setup 內操作 value 需加上「.value」
      const toggleMenu = () => showMenu.value = !showMenu.value
  
      // 「主選單按鈕」功能
      const menuItems = [
        { to: '/', text: '表一' },
        { to: '/list_1', text: '表二' },
        { to: '/list_2', text: '表三' },
      ]
  
      // 建立變數 activeItem 判斷哪個選項和當前匹配
      // 若有子項目時，可用 startsWith 判斷是否在前一個路徑下
      const activeItem = computed(() => 
        [...menuItems]
          .reverse()
          .find(item => route.path.startsWith(item.to))
      )
  
      // 判斷當前路徑目標的 to 是否等於 activeItem 的 to
      const isActive = to => to === activeItem.value.to
  
      return { showMenu, toggleMenu, menuItems, isActive }
    }
  }
  </script>
  
  