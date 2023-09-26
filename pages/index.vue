<script setup>
  
useHead({
  title: 'Home',
  script: [
    { src: "https://identity.netlify.com/v1/netlify-identity-widget.js" },
  ]
});

</script>
<script>

export default {
  data() {
    return {
      videos: [
        'IMG_1095-2.mp4',
        'Green-Smoke.mp4',
        'DetroitLove.mp4',
        'BehindthescenesofCarlCraigsSynthesizerEnsemble-1.mp4',
      ],
      selectedVideo: null,
    };
  },
  methods: {
    pickRandomVideo() {
      const randomIndex = Math.floor(Math.random() * this.videos.length);
      this.selectedVideo = this.videos[randomIndex];
      // You can also use this.$refs.videoPlayer.play() to automatically play the selected video.
    },
  },
  mounted() {
    this.pickRandomVideo();
  },
};
</script>
<template>
  <main class="mx-auto max-w-4xl space-y-6">
    <div class="flex p-8 mx-auto my-auto w-full h-full grid grid-flow-col">
        <div class="text-left col-span-6">    

        </div>

        <div class="bg-transparent p-1  text-right font-thin col-span-1 hover:bg-blaack hover:text-black-800">

        </div>

        <div class="flex bg-transparent place-content-right col-span-1">
            <transition name="nav">
              
            </transition>
          </div>
    </div>
              
  
     <div class="flex gap-14 align-center grid grid-flow-col h-full w-full p-64">
            
      <div class="flex bg-white min-h-full min-w-full">
      <video v-if="selectedVideo" ref="videoPlayer" class="min-w-full min-h-full" playsinline autoplay muted loop>
            <source :src="selectedVideo" type="video/mp4">
            Your browser does not support the video tag.
          </video>
          <!----    
    <video playsinline autoplay muted loop :poster="poster_URL in VideoItems" :key="1" id="bgvid" class="-z-30">
      <source :src="src_URL in VideoItems" :key="0"  type="video/mp4">
    </video>
    ---->
      <div class="container flex gap-14 align-center grid grid-flow-col h-full w-full p-64">

              <div class="logo">
                  <a class="link" href=""><div class="flex w-full mx-auto my-auto "><img src="~/assets/images/c2800wht.png" /></div></a>
              </div>
              <div class="logo">
                  <a class="link" href=""><div class="flex w-full mx-auto my-auto"><img src="~/assets/images/planet-e-logo-wh.png" /></div></a>
              </div>
              <div class="logo">
                  <a class="link" href=""><div class="p-10 flex w-full mx-auto my-auto "><img src="~/assets/images/detroit_love_website_header.png" /></div></a>
              </div>
              <div class="logo">
                  <a class="link" href="/"><div class="flex  w-full mx-auto my-auto"><img width="300" src="~/assets/images/CCART-wh.png" /></div></a>
              </div>
   
    
          </div>
          </div>
      </div>
    </main>
  </template>
  <style scoped>
  .container{
      /*background-image: url('~/assets/images/robot_webpage-wh-op-20.png');*/
      background-repeat:no-repeat;
      background-position: center;
      max-width:none;
      height: 100%;
      width: 100vw;
      transition: opacity 0.3s ease-in;
      object-fit: cover;
      position:fixed;
     top:0;
    left: 0;
  }

  video {
    object-fit:cover;

    position: fixed;
    top: 0;
    left: 0;
  }
  .logo{
      @apply flex w-full h-full gap-14 my-auto mx-auto place-content-center object-cover animate-pulse;
      vertical-align: middle;
    
  }
  .link{
      @apply flex min-h-full mx-auto min-w-full my-auto object-cover;
  }
  .logo:hover{
      @apply object-cover place-content-center -translate-y-1 animate-none;
  }
  .logo img{
      vertical-align: middle;
  }
  </style>


