<template>
  <div id="app">
    <div class="leading-normal tracking-normal gradient">
      <NavSection :logo="logo"/>
      <HeroSection/>
      <AboutUs :mision="mision" :vision="vision"/>
      <ContentSection/>
      <MailMeComponent :contactEmail="contactEmail" :contactNumber="contactNumber"/>
      <FooterComponent :contactEmail="contactEmail" :logo="logo"/>
    </div>
  </div>
</template>

<script>
import NavSection from "./components/NavSection.vue"
import HeroSection from './components/index/HeroSection.vue'
import ContentSection from './components/index/ContentSection.vue'
import AboutUs from './components/index/AboutUs.vue'
import MailMeComponent from './components/index/MailMeComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
import { createClient } from "@/plugins/contentful.js"

const client = createClient();

export default {
  name: 'App',
  components: {
    NavSection,
    HeroSection,
    ContentSection,
    AboutUs,
    FooterComponent,
    MailMeComponent,
  },
  data(){
    return{
      logo: "",
      contactEmail: "",
      contactNumber: "",
      mision:{},
      vision:{}
    }
  },
  created (){
    const cur = this;
    client.getEntry('2htMdoEYqy2iJtAoTSAA9V').then(function (entry) {
      cur.logo = entry.fields.logo.fields.file.url
      cur.contactEmail = entry.fields.contactEmail
      cur.contactNumber = entry.fields.contactNumber
    })
    client.getAsset('6FTLToB6nmtP0nRR3iE3tx')
      .then((asset) => {
        const mision = {};
        mision.description = asset.fields.description;
        mision.img = asset.fields.file.url;
        cur.mision = mision;
      })
      .catch(console.error);
    client.getAsset('6x14UyoVacy6zRdAhuOqYm')
      .then((asset) => {
        const vision = {};
        vision.description = asset.fields.description;
        vision.img = asset.fields.file.url;
        cur.vision = vision
      })
      .catch(console.error);
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@500&display=swap');

html {
  scroll-behavior: smooth !important;
}
body{
  margin: 0;
}

#app{
  background: linear-gradient(90deg, rgba(9,166,243,1) 0%, rgba(88,239,236,1) 120%);
  font-family: 'Ubuntu', sans-serif;
}
</style>
