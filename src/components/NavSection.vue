<template>
  <nav id="header" class="bg-white w-full z-30 top-0">

    <div class="w-full container mx-auto flex flex-wrap items-center justify-between mt-0 py-2">

      <div class="pl-4">
        <img class="w-32" :src="logo" alt="">
      </div>

      <!-- <div class="block lg:hidden pr-4">
        <button @click.prevent="toggleDropDown" id="nav-toggle" class="flex items-center px-3 py-2 border rounded text-gray-500 border-gray-600 hover:text-gray-800 hover:border-teal-500 appearance-none focus:outline-none">
          <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>

      <div :class="mobileDropdownOpened ? '' : 'hidden'" class="w-full flex-grow lg:flex lg:items-center lg:w-auto lg:block mt-2 lg:mt-0 bg-white lg:bg-transparent text-black p-4 lg:p-0 z-20" id="nav-content">
        <ul class="list-reset lg:flex justify-end flex-1 items-center">
          <li class="mr-3">
            <a class="inline-block py-2 px-4 text-black font-bold no-underline" href="#">Active</a>
          </li>
          <li class="mr-3">
            <a class="inline-block text-black no-underline hover:text-gray-800 hover:text-underline py-2 px-4" href="#">link</a>
          </li>
          <li class="mr-3">
            <a class="inline-block text-black no-underline hover:text-gray-800 hover:text-underline py-2 px-4" href="#">link</a>
          </li>
        </ul>
        <button id="navAction" class="mx-auto lg:mx-0 hover:underline bg-white text-gray-800 font-bold rounded-full mt-4 lg:mt-0 py-4 px-8 shadow opacity-75">Action</button>
      </div> -->
    </div>
    <hr class="border-b border-gray-100 opacity-25 my-0 py-0" />
  </nav>
</template>
<script>
export default ({
  props: {
    logo: String,
  },
  data() {
    return{
      mobileDropdownOpened: false
    }
  },
  methods: {
    toggleDropDown() {
      this.mobileDropdownOpened = !this.mobileDropdownOpened
    },
  }
})
</script>
<style scoped>

.hero{
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 2rem;
}

.hero--title{
  font-size: clamp(1rem, 12vw, 6rem);
  width: min-content;
}
</style>
