<script setup lang="ts">
import NavigationItem from './NavigationItem.vue'
import DrawerNav from '../DrawerNav.vue'
// const toggleDrawer = () => {
// console.log('here')
//   // drawer.value = !drawer.value
// }
function toggleDrawer(){
  console.log('ehrer')
}
</script>
<template>
  <nav class="fixed w-full z-20 top-0 start-0 border-b border-gray-200 dark:border-gray-600">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
      <a href="#" class="flex items-center space-x-3 rtl:space-x-reverse">
        <svg
          style="margin-top: 5px"
          width="100"
          height="20"
          viewBox="0 0 250 70"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M0.0681819 35.0909V30.5455L36.6591 11.9091V19.1818L8.59091 32.7045L8.81818 32.25V33.3864L8.59091 32.9318L36.6591 46.4545V53.7273L0.0681819 35.0909ZM189.876 0.0909052L171.126 69.75H164.99L183.74 0.0909052H189.876ZM236.347 40.5455L199.756 59.1818V51.9091L227.824 38.3864L227.597 38.8409V37.7045L227.824 38.1591L199.756 24.6364V17.3636L236.347 36V40.5455Z"
            fill="#35495E"
          />
          <path
            d="M51.7798 61V2.81818H58.8253V28.7273H89.848V2.81818H96.8935V61H89.848V34.9773H58.8253V61H51.7798ZM110.999 61V2.81818H118.044V28.7273H149.067V2.81818H156.112V61H149.067V34.9773H118.044V61H110.999Z"
            fill="#42B883"
          />
        </svg>
      </a>
      <div class="flex md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse">
        <button
          class="relative inline-flex items-center justify-center p-0.5 mb-2 me-2 overflow-hidden text-sm font-medium text-gray-900 rounded-lg group bg-gradient-to-br from-green-400 to-blue-600 group-hover:from-green-400 group-hover:to-blue-600 hover:text-white dark:text-white focus:ring-4 focus:outline-none focus:ring-green-200 dark:focus:ring-green-800"
        >
          <span
            class="relative px-5 py-2.5 transition-all ease-in duration-75 bg-white dark:bg-gray-900 rounded-md group-hover:bg-opacity-0"
          >
            Let's Talk
          </span>
        </button>

        <!-- drawer init and toggle -->
        <div>
          <button
            @toggleDrawer="toggleDrawer"
            type="button"
            class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
          >
          
            <svg
              class="w-5 h-5"
              aria-hidden="true"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 17 14"
            >
              <path
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M1 1h15M1 7h15M1 13h15"
              />
            </svg>
          </button>

          <!-- Use the Drawer component -->
          <DrawerNav />
        </div>
      </div>
      <NavigationItem />
    </div>
  </nav>
</template>
