<template>
  <footer class="bg-white">
    <div class="container mx-auto  px-8">

      <div class="w-full flex flex-col md:flex-row py-6">

        <div class="flex-1 mb-6 text-black">

          <div class="w-36 font-bold text-xl lg:text-2xl">
            <a class="flex items-center" href="/">
              <img class="w-20" :src="logo"/> CONSTRUCCIONES
            </a>
          </div>
        </div>
        <div class="flex-1"></div>
        <div class="flex-1 hidden">
          <p class="uppercase text-gray-500 md:mb-6">Links</p>
          <ul class="list-reset mb-6">
            <li class="mt-2 inline-block mr-2 md:block md:mr-0">
              <a href="#" class="no-underline hover:underline text-gray-800 hover:text-orange-500">FAQ</a>
            </li>
            <li class="mt-2 inline-block mr-2 md:block md:mr-0">
              <a href="#" class="no-underline hover:underline text-gray-800 hover:text-orange-500">Help</a>
            </li>
            <li class="mt-2 inline-block mr-2 md:block md:mr-0">
              <a href="#" class="no-underline hover:underline text-gray-800 hover:text-orange-500">Support</a>
            </li>
          </ul>
        </div>
        <div class="flex-1">
          <p class="uppercase text-gray-500 md:mb-4">Contáctenos</p>
          <div class="mb-6 flex flex-col items-start">
            Si tiene alguna pregunta que hacernos no dude en contactarnos que gustosamente lo atenderemos, para ello haga clic en el siguiente botón:
            <a
              :href="'mailto:' + contactEmail"
              class="inline-block mx-auto lg:mx-0 hover:underline bg-custom text-white font-bold rounded-full my-6 py-4 px-8 shadow-lg cursor-pointer"
            >
              Envíanos un mail
            </a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default ({
  props: {
    logo: String,
    contactEmail: String,
  },
  data() {
    return{}
  },
})
</script>
<style>
  .bg-custom{
    background: linear-gradient(90deg, rgba(9,166,243,1) 0%, rgba(88,239,236,1) 120%);
  }
</style>