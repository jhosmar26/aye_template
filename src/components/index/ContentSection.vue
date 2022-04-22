<template>
  <div class="bg-white border-b py-24">
    <h2 class="text-center text-4xl">PROYECTOS</h2>
    <div
      class="container max-w-5xl mx-auto mb-12"
      v-for="project,project_key in projects"
      :key="project_key"
    >
      <div v-if="project.images.length > 0">
        <h2 class="w-full mt-2 text-xl md:text-3xl font-bold leading-tight pl-6 text-black uppercase break-words" :key="key">{{project.title}}</h2>
        <VueSlickCarousel
          v-bind="carouselSettings"
          class="max-w-5xl mx-auto mt-3"
        >
          <div
            class="flex justify-center items-center h-64 md:h-96 px-3"
            v-for="image, imageKey in project.images"
            :key="imageKey"
            alt=""
          >
            <div
              class="w-full h-full bg-cover bg-center bg-no-repeat"
              :style="'background-image: url('+image+')'"
            >
            </div>
          </div>
        </VueSlickCarousel>
      </div>
    </div>
  </div>
</template>
<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import { createClient } from "@/plugins/contentful.js"

const client = createClient();

export default {
  name: 'ContentSection',
  components: {
    VueSlickCarousel
  },
  data(){
    return{
      contentfullData: [],
      projects: [],
      key:0,
      carouselSettings:{
        "dots":true,
        "centerMode":true,
        "slidesPerRow": 2,
        "responsive": [
          {
            "breakpoint": 640,
            "settings": {
              "slidesPerRow": 1,
            }
          },
        ]
      }
    }
  },
  created(){
    client.getEntries({
      content_type: "project"
    })
    .then((entries)=>{
      this.contentfullData = entries.items
      this.projects = this.contentfullData.map(el => {
        return {
          title: el.fields.title,
          images: el.fields.image.filter(imgEl => imgEl.fields?.file?.url)
          .map(el=> el.fields?.file?.url),
        };
      });
      console.log(this.projects)
    })
  }
}
</script>

<style>
.slick-arrow:before{
  color: black;
}
.slick-next{
  right: 25px;
}
.slick-prev{
  left: 25px;
  z-index: 999;
}
</style>