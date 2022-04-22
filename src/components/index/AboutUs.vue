<template>
  <section class="bg-white border-b py-8">
    <div class="container max-w-5xl mx-auto m-8">
      <!-- <h2 class="my-2 text-5xl font-bold leading-tight text-center text-gray-800">Nuestra Cultura</h2> -->
      <div class="w-full mb-4">
        <div class="h-1 mx-auto bg-custom w-64 opacity-25 my-0 py-0 rounded-t"></div>
      </div>

      <div class="flex flex-wrap">
        <div class="w-5/6 sm:w-1/2 p-6">
          <h3 class="text-3xl text-gray-800 font-bold leading-none mb-3">Misión</h3>
          <p class="text-gray-600 mb-8">{{mision.description}}<br /><br />
          </p>
        </div>
        <div class="w-full sm:w-1/2 p-6 flex-shrink">
          <img class="w-5/6 mx-auto" :src="mision.img" alt="">
        </div>
      </div>


      <div class="flex flex-wrap flex-col-reverse sm:flex-row">
        <div class="w-full sm:w-1/2 p-6 mt-6">
          <img class="w-5/6 mx-auto" :src="vision.img" alt="">
        </div>
        <div class="w-full sm:w-1/2 p-6 mt-6">
          <div class="align-middle">
            <h3 class="text-3xl text-gray-800 font-bold leading-none mb-3">Visión</h3>
            <p class="text-gray-600 mb-8">{{vision.description}}<br /><br />
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>

export default({
  props:{
    mision: Object,
    vision: Object,
  },
  data(){
    return{
      a:""
    }
  }
})
</script>

<style scoped>
  .bg-custom{
    background: linear-gradient(90deg, rgba(9,166,243,1) 0%, rgba(88,239,236,1) 120%);
  }
</style>